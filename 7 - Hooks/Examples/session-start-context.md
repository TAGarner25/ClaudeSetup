---
title: Inject context at session start
description: SessionStart hook that echoes project reminders or recent commits into Claude's context.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, sessionstart, context, compaction]
---

# Inject context at session start

Anything a `SessionStart` hook writes to stdout is added to Claude's context as a system reminder. Use it to re-inject details that `CLAUDE.md` can't carry — recent commits, current sprint, the branch you're on, secrets paths, today's date.

This is especially useful with the `compact` matcher: compaction summarizes old conversation to free context, and can drop load-bearing details. A `SessionStart` + `compact` hook re-plants them after every compaction.

## Static reminders

```json
{
  "hooks": {
    "SessionStart": [
      {
        "matcher": "compact",
        "hooks": [
          {
            "type": "command",
            "command": "echo 'Reminder: use Bun, not npm. Run bun test before committing. Current sprint: auth refactor.'"
          }
        ]
      }
    ]
  }
}
```

## Dynamic context from git

Inject the last 5 commits and the current branch on every session start:

```json
{
  "hooks": {
    "SessionStart": [
      {
        "matcher": "startup|resume|compact",
        "hooks": [
          {
            "type": "command",
            "command": "echo 'Branch:' $(git rev-parse --abbrev-ref HEAD) && echo 'Recent commits:' && git log --oneline -5"
          }
        ]
      }
    ]
  }
}
```

## Session-Start matchers

- `startup` — fresh launch
- `resume` — `claude --resume` or `/resume`
- `clear` — after `/clear`
- `compact` — after automatic or manual compaction

Combine with `|`, e.g. `"startup|resume"` to avoid re-injection on every compaction.

## Persisting env vars

`SessionStart` hooks can also write to `$CLAUDE_ENV_FILE`. Lines written there are sourced before every Bash tool call — useful for `NODE_ENV`, `AWS_PROFILE`, API tokens from a vault:

```bash
#!/bin/bash
if [ -n "$CLAUDE_ENV_FILE" ]; then
  echo "export AWS_PROFILE=dev" >> "$CLAUDE_ENV_FILE"
  echo "export NODE_ENV=development" >> "$CLAUDE_ENV_FILE"
fi
```

Register as a normal command hook — the env file path is supplied automatically.

## When to use this vs CLAUDE.md

| Need | Use |
|------|-----|
| Static project rules | `CLAUDE.md` |
| Changing context (branch, sprint, date) | `SessionStart` hook |
| Secrets / env vars for Bash | `SessionStart` with `$CLAUDE_ENV_FILE` |
| Re-seeding after compaction | `SessionStart` with `matcher: "compact"` |
