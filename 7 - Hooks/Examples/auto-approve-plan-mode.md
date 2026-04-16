---
title: Auto-approve plan mode exit
description: PermissionRequest hook that skips the ExitPlanMode approval dialog.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, permissionrequest, plan-mode, quality-of-life]
---

# Auto-approve plan mode

When Claude finishes planning in plan mode, it calls `ExitPlanMode` and waits for you to approve. If you always want to proceed, auto-approve the prompt with a `PermissionRequest` hook.

Unlike `exit 2` style blocking hooks, auto-approval requires writing a **JSON decision to stdout**.

## Configuration

Add to `~/.claude/settings.json`:

```json
{
  "hooks": {
    "PermissionRequest": [
      {
        "matcher": "ExitPlanMode",
        "hooks": [
          {
            "type": "command",
            "command": "echo '{\"hookSpecificOutput\": {\"hookEventName\": \"PermissionRequest\", \"decision\": {\"behavior\": \"allow\"}}}'"
          }
        ]
      }
    ]
  }
}
```

The transcript will show *"Allowed by PermissionRequest hook"* where the dialog would have been. Claude exits plan mode and restores whatever permission mode was active before plan mode started.

## Switching into acceptEdits after plan mode

Jump straight into accept-edits mode when the plan is approved:

```json
{
  "type": "command",
  "command": "echo '{\"hookSpecificOutput\": {\"hookEventName\": \"PermissionRequest\", \"decision\": {\"behavior\": \"allow\", \"updatedPermissions\": [{\"type\": \"setMode\", \"mode\": \"acceptEdits\", \"destination\": \"session\"}]}}}'"
}
```

`destination: "session"` means the mode change lasts only for the current session — it isn't written back to `settings.json`.

Valid `mode` values: `default`, `acceptEdits`, `dontAsk`, `bypassPermissions`, `plan`.

## Other auto-approvable tools

Replace `"ExitPlanMode"` with any tool whose prompt you always accept. Common targets:

- `Read` — reading files off-cwd
- `Bash` with narrow `if`: `"if": "Bash(git status)|Bash(git diff)|Bash(git log *)"`
- A specific MCP tool: `"mcp__memory__.*"`

**Keep the matcher narrow.** `.*` or an empty matcher auto-approves *every* permission prompt — including file writes and arbitrary shell commands. That's a much bigger blast radius than you probably want.

## Notes

- Returning `allow` does not override `deny` permission rules. Managed-settings deny rules always win.
- `PermissionRequest` hooks **do not fire in non-interactive mode** (`claude -p`). In that mode, use a `PreToolUse` hook with `permissionDecision: "allow"`.
- `bypassPermissions` mode can only be set from this hook if the session was launched with it available (`--permission-mode bypassPermissions`, etc.).
