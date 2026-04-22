---
title: Block edits to sensitive files
description: PreToolUse hook that prevents Claude from writing to .env, lock files, .git, etc.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, pretooluse, security, blocking]
---

# Protect sensitive files

Stops Claude from touching files you never want it to modify — secrets, lock files, git internals. The hook exits with code `2` to **block** the tool call and returns a reason Claude can use to adjust.

## When it fires

Before any `Edit` or `Write` tool call.

## 1. Create the script

Save as `.claude/hooks/protect-files.sh`:

```bash
#!/bin/bash
# .claude/hooks/protect-files.sh

INPUT=$(cat)
FILE_PATH=$(echo "$INPUT" | jq -r '.tool_input.file_path // empty')

PROTECTED=(
  ".env"
  ".env.local"
  ".env.production"
  "package-lock.json"
  "yarn.lock"
  "pnpm-lock.yaml"
  "poetry.lock"
  ".git/"
  "credentials.json"
  ".aws/"
  ".ssh/"
)

for pattern in "${PROTECTED[@]}"; do
  if [[ "$FILE_PATH" == *"$pattern"* ]]; then
    echo "Blocked: $FILE_PATH matches protected pattern '$pattern'. Ask the user before modifying this file." >&2
    exit 2
  fi
done

exit 0
```

## 2. Make it executable (macOS / Linux)

```bash
chmod +x .claude/hooks/protect-files.sh
```

## 3. Register the hook

In `.claude/settings.json`:

```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "\"$CLAUDE_PROJECT_DIR\"/.claude/hooks/protect-files.sh"
          }
        ]
      }
    ]
  }
}
```

## How it works

- Reads the `PreToolUse` JSON on stdin and extracts `tool_input.file_path`.
- Compares against a list of protected substrings.
- On match: writes a reason to **stderr** (which Claude sees) and exits `2` (which **blocks** the call).
- On no match: exits `0`, the edit proceeds normally.

## Windows variant

Save as `.claude/hooks/protect-files.ps1` and use `"shell": "powershell"`:

```powershell
$input = [Console]::In.ReadToEnd() | ConvertFrom-Json
$path = $input.tool_input.file_path
$protected = @(".env", "package-lock.json", ".git\", "credentials.json")
foreach ($pattern in $protected) {
  if ($path -like "*$pattern*") {
    [Console]::Error.WriteLine("Blocked: $path matches '$pattern'")
    exit 2
  }
}
exit 0
```

```json
{
  "type": "command",
  "shell": "powershell",
  "command": "& \"$CLAUDE_PROJECT_DIR\\.claude\\hooks\\protect-files.ps1\""
}
```

## Notes

- A `deny` from this hook overrides `bypassPermissions` and `--dangerously-skip-permissions` — this is the point. It's how you enforce project policy that users can't flip a flag around.
- Prefer an allow-list if your repo is security-sensitive. Denylists miss new files.
- For commands (not file writes), use a `Bash`-matcher hook. See [Block dangerous commands](block-dangerous-commands.md).
