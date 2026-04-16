---
title: Log every Bash command Claude runs
description: PostToolUse hook that appends every shell command to an audit log.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, postooluse, audit, logging]
---

# Log every Bash command

Keep a plain-text log of everything Claude runs in the shell. Useful for audit, post-hoc debugging, or just curiosity.

## Configuration

Add to `~/.claude/settings.json` for a global log, or `.claude/settings.json` for a per-project log:

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "jq -r '\"[\\(now | todate)] \\(.tool_input.command)\"' >> ~/.claude/command-log.txt"
          }
        ]
      }
    ]
  }
}
```

Each run appends a line like:

```
[2026-04-16T14:22:01Z] git status
[2026-04-16T14:22:04Z] npm test
```

## Log full tool I/O

Capture input *and* output (useful for debugging):

```json
"command": "jq -c '{ts: now | todate, cmd: .tool_input.command, exit: .tool_response.exit_code, stdout: .tool_response.stdout}' >> ~/.claude/bash-audit.jsonl"
```

Each line is a JSON object — parse later with `jq`.

## Log only failures

Use `PostToolUseFailure` instead:

```json
{
  "hooks": {
    "PostToolUseFailure": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "jq -c '{ts: now | todate, cmd: .tool_input.command, error: .error}' >> ~/.claude/bash-failures.jsonl"
          }
        ]
      }
    ]
  }
}
```

## Rotate the log

`command-log.txt` grows forever. Add a weekly cron / scheduled task to rotate it:

```bash
# Unix cron
0 0 * * 0 mv ~/.claude/command-log.txt ~/.claude/command-log.$(date +\%Y\%m\%d).txt

# Windows Task Scheduler — PowerShell one-liner
Move-Item "$HOME\.claude\command-log.txt" "$HOME\.claude\command-log.$(Get-Date -f yyyyMMdd).txt"
```

## Notes

- `PostToolUse` fires after the command completes — it cannot block. Use `PreToolUse` for blocking. See [Block dangerous commands](block-dangerous-commands.md).
- Hooks run in parallel and output is interleaved — the timestamp in each line keeps things ordered.
