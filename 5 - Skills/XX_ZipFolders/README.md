---
title: Packaged Skill Bundles
description: Pre-zipped, installable skill bundles ready to drop into Claude.ai or Claude Code.
created: 2026-04-16
updated: 2026-04-16
topics: [skills, zip, packaged, installable, bundles]
---

# Packaged Skill Bundles

Pre-zipped skill folders ready for installation. Each `.zip` contains a `SKILL.md` plus any supporting files; unzipping produces a folder you can drop into your skills directory.

## Bundles

| Bundle | Source | Description |
|--------|--------|-------------|
| `erickson-brand-guidelines.zip` | [erickson-brand-guidelines/](erickson-brand-guidelines/) | Erickson Group brand guideline skill |

## Install — Claude Code

```bash
unzip <bundle>.zip -d ~/.claude/skills/
# or for project-only:
unzip <bundle>.zip -d .claude/skills/
```

Then verify:

```bash
ls ~/.claude/skills/
```

Or in Claude Code, run `/skills` (if available) or just ask "what skills are available?".

## Install — Claude.ai

1. Go to **Settings → Capabilities → Skills → Upload skill**.
2. Upload the `.zip` directly (do not unzip first).
3. Confirm the skill appears in the list.

Code execution must be enabled for skills to run on Claude.ai.

## Related

- [`../README.md`](../README.md) — parent skills index
- [Use Skills in Claude Code](https://code.claude.com/docs/en/skills)
