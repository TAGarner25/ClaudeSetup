---
title: Claude Code Hooks
description: Reference guide to Claude Code hooks — lifecycle events, configuration, matchers, I/O contract, and practical examples.
created: 2026-04-16
updated: 2026-04-16
topics: [claude-code, hooks, automation, settings]
---

# Claude Code Hooks

Hooks are **user-defined shell commands (or HTTP/prompt/agent calls) that Claude Code runs automatically at specific points in its lifecycle**. They give you deterministic control over behavior — the harness executes them, so they always fire rather than depending on the model choosing to run them.

Use hooks to:

- Auto-format or lint files after Claude edits them
- Block edits or commands that touch sensitive files
- Send desktop / Slack / email notifications when Claude needs you
- Inject project context at session start or after compaction
- Audit tool use and config changes
- Auto-approve specific permission prompts

> Hooks run as **your user** with **your credentials**. A misconfigured hook can delete files, exfiltrate data, or break your environment. Always review a hook before installing it — especially ones copied from the internet.

---

## Table of contents

- [How hooks work](#how-hooks-work)
- [Hook events](#hook-events)
- [Configuring a hook](#configuring-a-hook)
- [Matchers](#matchers)
- [Input / output contract](#input--output-contract)
- [Hook types](#hook-types)
- [Examples](#examples)
- [Troubleshooting](#troubleshooting)
- [Security](#security)
- [Additional resources](#additional-resources)

---

## How hooks work

1. An event fires in Claude Code (e.g. Claude is about to call `Bash`).
2. The harness looks up every hook registered for that event whose `matcher` matches.
3. Each hook is run in parallel. Matching hooks with identical commands are deduplicated.
4. The hook receives event data as **JSON on stdin**.
5. The hook returns a result via **exit code + stdout/stderr** (or a JSON response body for HTTP hooks).
6. Claude Code aggregates the results — for decisions, the **most restrictive** answer wins (`deny` beats `ask` beats `allow`).

Hooks are **not** skills, plugins, or slash commands. They are a configuration concept: entries in a `settings.json` file.

---

## Hook events

| Event | When it fires | Can block? |
|-------|---------------|------------|
| `SessionStart` | Session begins or resumes | No |
| `SessionEnd` | Session terminates | No |
| `UserPromptSubmit` | User submits a prompt, before Claude processes it | Yes |
| `PreToolUse` | Before a tool call executes | Yes |
| `PostToolUse` | After a tool call succeeds | No (context only) |
| `PostToolUseFailure` | After a tool call fails | No |
| `PermissionRequest` | A permission dialog is about to be shown | Yes (auto-approve/deny) |
| `PermissionDenied` | Auto-mode classifier denied a tool call | No (can allow retry) |
| `SubagentStart` / `SubagentStop` | Subagent spawned / finished | Stop: yes |
| `TaskCreated` / `TaskCompleted` | Task lifecycle via `TaskCreate` | Yes |
| `Stop` | Claude finishes responding | Yes |
| `StopFailure` | Turn ends due to API error | No |
| `Notification` | Claude Code sends a notification | No |
| `PreCompact` / `PostCompact` | Context compaction | PreCompact: yes |
| `InstructionsLoaded` | `CLAUDE.md` or `.claude/rules/*.md` loaded | No |
| `ConfigChange` | Settings or skills file changes mid-session | Yes |
| `CwdChanged` | Working directory changes | No |
| `FileChanged` | A watched file changes on disk | No |
| `WorktreeCreate` / `WorktreeRemove` | Worktree lifecycle | Create: yes |
| `Elicitation` / `ElicitationResult` | MCP server requests user input | Yes |
| `TeammateIdle` | Agent team teammate about to go idle | Yes |

For the full schema of each event, see the [official reference](https://code.claude.com/docs/en/hooks).

---

## Configuring a hook

Hooks live inside a `hooks` block in any settings file. Structure: **event → matcher group → handler list**.

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "jq -r '.tool_input.file_path' | xargs npx prettier --write"
          }
        ]
      }
    ]
  }
}
```

### Where to put them

| Location | Scope | Shareable |
|----------|-------|-----------|
| `~/.claude/settings.json` | All projects, local machine | No |
| `.claude/settings.json` | Single project | Yes (commit to repo) |
| `.claude/settings.local.json` | Single project, personal overrides | No (gitignored) |
| Managed policy settings | Organization-wide | Admin-controlled |
| Plugin `hooks/hooks.json` | When the plugin is enabled | Yes (bundled) |
| Skill / agent frontmatter | While that component is active | Yes (in the file) |

Type `/hooks` inside Claude Code to see every configured hook grouped by event. The menu is read-only — edit the JSON to change anything.

Disable everything at once with:

```json
{ "disableAllHooks": true }
```

---

## Matchers

A hook without a matcher fires on every occurrence of its event. Matchers narrow that down.

| Pattern | Meaning |
|---------|---------|
| `""` / `"*"` / omitted | Match all |
| `"Bash"` | Exact tool name |
| `"Edit\|Write"` | Pipe-separated exact names |
| `"^Notebook"` | Treated as regex (contains a regex-only char) |
| `"mcp__memory__.*"` | All tools from the `memory` MCP server |
| `"mcp__.*__write.*"` | Any `write*` tool from any MCP server |

Each event type matches on a different field — `tool_name` for `PreToolUse`/`PostToolUse`, `source` for `SessionStart`, `notification_type` for `Notification`, and so on.

### Narrowing with `if` (v2.1.85+)

The `if` field filters on tool **arguments** using permission-rule syntax, and only for tool events (`PreToolUse`, `PostToolUse`, `PostToolUseFailure`, `PermissionRequest`, `PermissionDenied`):

```json
{
  "type": "command",
  "if": "Bash(git *)",
  "command": "./.claude/hooks/check-git-policy.sh"
}
```

The hook process only spawns when the command starts with `git`.

---

## Input / output contract

### Input (stdin)

Every hook receives a JSON object. Common fields:

```json
{
  "session_id": "abc123",
  "cwd": "/Users/me/project",
  "hook_event_name": "PreToolUse",
  "transcript_path": "/path/to/transcript.jsonl"
}
```

Event-specific fields are added on top. A `PreToolUse` hook for a Bash command also gets:

```json
{
  "tool_name": "Bash",
  "tool_input": { "command": "npm test" },
  "tool_use_id": "toolu_..."
}
```

### Output — exit codes

| Exit code | Behavior |
|-----------|----------|
| `0` | Action proceeds. For `UserPromptSubmit` and `SessionStart`, stdout is injected into Claude's context. |
| `2` | **Blocks** the action on blockable events. stderr is fed back to Claude. |
| Anything else | Action proceeds. A `<hook name> hook error` notice appears; stderr goes to the debug log. |

### Output — structured JSON

For more control, exit `0` and write JSON to stdout. A `PreToolUse` hook denying with a reason:

```json
{
  "hookSpecificOutput": {
    "hookEventName": "PreToolUse",
    "permissionDecision": "deny",
    "permissionDecisionReason": "Use rg instead of grep"
  }
}
```

`permissionDecision` values for `PreToolUse`:

- `allow` — skip the permission prompt (deny rules still apply)
- `deny` — cancel and feed the reason back to Claude
- `ask` — show the prompt as normal
- `defer` — non-interactive mode only; preserve the tool call for SDK handling

> Do not mix exit code `2` with a JSON stdout body — Claude Code ignores the JSON when you exit `2`.

Universal JSON fields usable on most events: `continue`, `stopReason`, `suppressOutput`, `systemMessage`, `decision` (`"block"`), `reason`.

---

## Hook types

Every handler has a `type`:

| Type | Runs | Use when |
|------|------|----------|
| `command` | A shell command | Default. Fast, deterministic checks. |
| `http` | POST the event JSON to a URL | Centralized logging / team-wide audit. |
| `prompt` | Single-turn LLM call (Haiku by default) | Decisions that need judgment, no tools. |
| `agent` | Spawns a subagent with tools | Verification that needs to read files or run commands. |

`prompt` and `agent` hooks return `{"ok": true}` or `{"ok": false, "reason": "..."}` as JSON.

Shared fields: `timeout` (seconds), `if`, `statusMessage`. `command` supports `async`, `shell` (`bash` or `powershell`). `http` supports `url`, `headers`, `allowedEnvVars` (whitelist of env vars interpolated into headers).

Useful environment variables in command hooks:

- `$CLAUDE_PROJECT_DIR` — project root (quote it: `"$CLAUDE_PROJECT_DIR"`)
- `$CLAUDE_PLUGIN_ROOT` — plugin install dir (plugin hooks only)
- `$CLAUDE_ENV_FILE` — write `export FOO=bar` lines here; Claude Code sources it before each Bash command (valid in `SessionStart`, `CwdChanged`, `FileChanged`)

---

## Examples

Runnable hook snippets live in [`Examples/`](Examples/):

| Example | Event | What it does |
|---------|-------|--------------|
| [Auto-format on edit](Examples/auto-format-on-edit.md) | `PostToolUse` | Run Prettier on every file Claude edits |
| [Protect sensitive files](Examples/protect-sensitive-files.md) | `PreToolUse` | Block edits to `.env`, `package-lock.json`, `.git/` |
| [Desktop notifications](Examples/desktop-notifications.md) | `Notification` | macOS / Linux / Windows alert when Claude needs input |
| [Inject context at session start](Examples/session-start-context.md) | `SessionStart` | Echo reminders / recent commits into Claude's context |
| [Log every Bash command](Examples/log-bash-commands.md) | `PostToolUse` | Append each shell command to an audit log |
| [Block dangerous commands](Examples/block-dangerous-commands.md) | `PreToolUse` | Python validator that blocks `rm -rf /`, `drop table`, etc. |
| [Auto-approve plan mode](Examples/auto-approve-plan-mode.md) | `PermissionRequest` | Skip the `ExitPlanMode` approval dialog |
| [Require tests before stopping](Examples/stop-require-tests.md) | `Stop` | Agent hook that verifies tests pass before Claude finishes |

---

## Troubleshooting

**Hook not firing.** Open `/hooks` and confirm it appears under the right event. Matchers are case-sensitive. `PermissionRequest` doesn't fire in non-interactive mode (`-p`) — use `PreToolUse` instead.

**`jq: command not found` / `script not found`.** Install `jq`, or rewrite the hook in Python/Node. Use `"$CLAUDE_PROJECT_DIR"/.claude/hooks/script.sh` for absolute paths.

**Script isn't executed.** On macOS / Linux: `chmod +x .claude/hooks/*.sh`.

**JSON validation error even though my output looks right.** Your shell profile (`~/.zshrc`, `~/.bashrc`) probably prints something unconditionally — that output gets prepended to your hook's JSON. Wrap any echo in an interactive check:

```bash
if [[ $- == *i* ]]; then
  echo "Shell ready"
fi
```

**`Stop` hook infinite loop.** Check `stop_hook_active` in the input — exit `0` when it's already `true`:

```bash
INPUT=$(cat)
if [ "$(echo "$INPUT" | jq -r '.stop_hook_active')" = "true" ]; then
  exit 0
fi
```

**Debugging.** Start with `claude --debug-file /tmp/claude.log` and `tail -f /tmp/claude.log` in another terminal. Or run `/debug` mid-session. `Ctrl+O` shows the transcript with one-line hook summaries.

**Test a hook manually:**

```bash
echo '{"tool_name":"Bash","tool_input":{"command":"ls"}}' | ./my-hook.sh
echo $?
```

---

## Security

- Hooks run as your OS user with your credentials. Treat them like shell scripts you wrote yourself.
- **Never paste in a hook you haven't read.** A `PreToolUse` hook can exfiltrate `tool_input`.
- Only env vars listed in a handler's `allowedEnvVars` are interpolated into HTTP headers — everything else becomes an empty string.
- A hook returning `deny` overrides even `bypassPermissions` mode and `--dangerously-skip-permissions`. Hooks can tighten, not loosen, permission rules.
- Managed policy settings can set `allowManagedHooksOnly` to disable user / project hooks entirely.
- Default timeouts: command 600s, prompt 30s, agent 60s, HTTP 30s. Cap long-running hooks explicitly with `timeout`.

---

## Additional resources

- [Official hooks reference](https://code.claude.com/docs/en/hooks) — full event schemas and JSON formats
- [Hooks guide with walkthroughs](https://code.claude.com/docs/en/hooks-guide) — step-by-step setup
- [Bash command validator example](https://github.com/anthropics/claude-code/blob/main/examples/hooks/bash_command_validator_example.py) — reference Python implementation
- [[Claude Code]] product overview in this repo
- [[Plugins]] — package hooks (plus commands, agents, skills) into a distributable plugin
