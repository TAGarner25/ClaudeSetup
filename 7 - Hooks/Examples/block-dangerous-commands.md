---
title: Block dangerous shell commands
description: PreToolUse hook that blocks destructive Bash commands before they execute.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, pretooluse, bash, security, blocking]
---

# Block dangerous shell commands

A Python validator that inspects `Bash` commands before they run and blocks anything matching known-bad patterns: `rm -rf /`, `drop table`, force-pushes to `main`, `sudo rm`, and so on. Claude sees the reason and can adjust.

This is adapted from the [official reference implementation](https://github.com/anthropics/claude-code/blob/main/examples/hooks/bash_command_validator_example.py).

## 1. The validator

Save as `.claude/hooks/bash-validator.py`:

```python
#!/usr/bin/env python3
"""Block destructive Bash commands before Claude runs them."""
import json
import re
import sys

BLOCKED_PATTERNS = [
    (r"\brm\s+-rf?\s+/(?!\w)", "rm -rf on filesystem root"),
    (r"\brm\s+-rf?\s+~\s*$",    "rm -rf on home directory"),
    (r"\bsudo\s+rm\b",          "sudo rm (use non-destructive alternatives)"),
    (r":\(\)\{.*\};:",          "fork bomb"),
    (r"\bmkfs\.",               "filesystem format"),
    (r"\bdd\s+.*of=/dev/sd",    "dd to a block device"),
    (r"\bdrop\s+table\b",       "SQL DROP TABLE (add a WHERE clause or use a migration)"),
    (r"\bdrop\s+database\b",    "SQL DROP DATABASE"),
    (r"\bgit\s+push\s+.*--force\b.*\b(main|master)\b", "force push to main/master"),
    (r"\bgit\s+reset\s+--hard\b.*origin/(main|master)", "hard reset to origin/main"),
    (r"\bcurl\b.*\|\s*(bash|sh)\b", "piping curl to shell (review the script first)"),
]

WARN_PATTERNS = [
    (r"\bgrep\b(?!.*\|)", "prefer rg (ripgrep) for performance"),
    (r"\bfind\b.*-name\b", "prefer rg --files --glob for filename search"),
]

def main():
    payload = json.load(sys.stdin)
    command = payload.get("tool_input", {}).get("command", "")

    for pattern, reason in BLOCKED_PATTERNS:
        if re.search(pattern, command, re.IGNORECASE):
            print(f"Blocked: {reason}. Command was: {command}", file=sys.stderr)
            sys.exit(2)

    warnings = [
        reason for pattern, reason in WARN_PATTERNS
        if re.search(pattern, command, re.IGNORECASE)
    ]
    if warnings:
        print(json.dumps({
            "hookSpecificOutput": {
                "hookEventName": "PreToolUse",
                "permissionDecision": "allow",
                "additionalContext": "Warnings: " + "; ".join(warnings)
            }
        }))

    sys.exit(0)

if __name__ == "__main__":
    main()
```

## 2. Register it

In `.claude/settings.json`:

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "python \"$CLAUDE_PROJECT_DIR\"/.claude/hooks/bash-validator.py"
          }
        ]
      }
    ]
  }
}
```

On macOS / Linux also `chmod +x .claude/hooks/bash-validator.py` and drop the leading `python`.

## How it works

- Reads the `PreToolUse` event from stdin.
- For each blocked pattern: exit `2` with a reason on stderr → Claude sees the reason and retries differently.
- For each warn pattern: exit `0` with a JSON body that **allows** the call but appends `additionalContext` for Claude to consider next time.

## Ideas for more patterns

- Block `npm install --force` or `--legacy-peer-deps`.
- Require a scratch branch prefix before allowing `git commit`: reject commands that run `git commit` on `main`.
- Warn when `docker run` omits `--rm`.
- Block `terraform apply` in directories under `prod/`.

## Limits

- Regex can't see environment state. A command like `cd /tmp && rm -rf *` is harder to reason about than raw paths — keep patterns tight.
- `PostToolUse` cannot undo a command. This only works pre-execution.
- The hook receives the raw string Claude passed; shell expansion (globs, command substitution) hasn't happened yet.
