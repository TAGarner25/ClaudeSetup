---
title: Auto-format files after Claude edits them
description: PostToolUse hook that runs Prettier on every file Edit or Write touches.
created: 2026-04-16
updated: 2026-04-16
topics: [hooks, postooluse, formatting, prettier]
---

# Auto-format on edit

Runs [Prettier](https://prettier.io/) against any file Claude edits with `Edit` or `Write`, so formatting stays consistent without prompting Claude to do it manually.

## When it fires

After `Edit` or `Write` completes successfully. The matcher is `Edit|Write`, so it skips `Bash`, `Read`, `Glob`, etc.

## Configuration

Add to `.claude/settings.json` in the project root (team-shared) or `~/.claude/settings.json` (global):

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "jq -r '.tool_input.file_path' | xargs npx prettier --write --ignore-unknown"
          }
        ]
      }
    ]
  }
}
```

## How it works

- The hook receives the full `PostToolUse` JSON on stdin.
- `jq -r '.tool_input.file_path'` extracts just the path.
- `xargs` passes it to `prettier --write`.
- `--ignore-unknown` skips file types Prettier doesn't know (images, binaries, etc.) instead of erroring.

## Variants

**Run the project's own formatter.** If your repo has `npm run format -- <path>`, call it directly:

```json
"command": "jq -r '.tool_input.file_path' | xargs npm run format --"
```

**Python (Black + Ruff).** Match only `.py` edits via `if`:

```json
{
  "type": "command",
  "if": "Edit(*.py)|Write(*.py)",
  "command": "jq -r '.tool_input.file_path' | xargs -I{} sh -c 'ruff check --fix {} && black {}'"
}
```

**Go.** `gofmt -w` is a one-liner:

```json
"command": "jq -r '.tool_input.file_path' | xargs gofmt -w"
```

## Notes

- `PostToolUse` can't undo the edit — it runs *after* Claude has written the file. The formatter rewrites it in place.
- If Prettier fails (syntax error in Claude's output), the non-zero exit just logs a warning. Claude won't see it unless you exit `2`.
- Install `jq` first: `brew install jq`, `apt install jq`, or [jqlang.github.io/jq](https://jqlang.github.io/jq/download/).
