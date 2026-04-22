---
title: Claude Code Plugins
description: Reference and examples for Claude Code plugins — bundles of slash commands, agents, hooks, skills, and MCP servers shipped together.
created: 2026-04-16
updated: 2026-04-16
topics: [claude-code, plugins, marketplaces, mcp, hooks, skills]
---

# Claude Code Plugins

A plugin packages **slash commands, subagents, hooks, skills, and MCP servers** into a single installable unit. Plugins are the recommended way to share custom Claude Code behavior with a team or with the wider community.

## What's in a plugin

A plugin is just a directory with one or more of these subfolders:

```
my-plugin/
├── .claude-plugin/
│   └── plugin.json          # name, version, description
├── commands/                # custom /slash commands
├── agents/                  # subagent definitions
├── hooks/
│   └── hooks.json           # lifecycle hooks
├── skills/                  # bundled skills
└── mcp.json                 # MCP server configuration
```

Anything you can drop into `~/.claude/` you can ship as a plugin instead.

## Installing a plugin

1. **Add a marketplace** that hosts the plugin: `/plugin marketplace add <owner>/<repo>` (a public Git repo with a `.claude-plugin/marketplace.json`).
2. **Install** from that marketplace: `/plugin install <plugin-name>`.
3. **Confirm** with `/plugin` — the menu lists installed plugins, version, and source.

Update with `/plugin update <name>`. Disable temporarily with `/plugin disable <name>`. Remove with `/plugin uninstall <name>`.

## Authoring a plugin

1. Scaffold the directory above.
2. Fill `plugin.json` (`name`, `version`, `description`, optional `author`, `homepage`, `repository`).
3. Add commands / agents / hooks / skills / MCP servers as needed.
4. Publish the directory to a Git repo.
5. Create a marketplace JSON (`.claude-plugin/marketplace.json`) that lists the plugin, then point others at the repo.

The [`5 - Skills/20_Plugin_Management/`](../5%20-%20Skills/20_Plugin_Management/) folder contains meta-skills (`Plugin_Creator`, `Plugin_Customizer`) that walk through this end-to-end.

## Examples

Examples and authored plugins will land in `Examples/` (planned). For now see:

- [Anthropic plugin examples](https://github.com/anthropics/claude-code-plugins) — reference implementations
- [`5 - Skills/20_Plugin_Management/`](../5%20-%20Skills/20_Plugin_Management/) — authoring guides bundled in this repo

## Related

- [`7 - Hooks/README.md`](../7%20-%20Hooks/README.md) — hooks shipped inside a plugin work the same as user-installed hooks
- [`5 - Skills/README.md`](../5%20-%20Skills/README.md) — skills bundled in a plugin work the same as standalone skills
- [Official plugins reference](https://code.claude.com/docs/en/plugins)
