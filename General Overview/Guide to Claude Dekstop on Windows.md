# The complete guide to Claude's desktop products on Windows

**Claude's three desktop modes — Chat, Cowork, and Code — form an integrated AI workspace that handles everything from quick questions to autonomous file processing to full software development.** For a Pro subscriber on Windows, this means access to conversational AI, an autonomous knowledge-work agent, and a terminal-based coding assistant, all within a single application. This guide covers installation, configuration, and advanced usage of every major feature, with Windows-specific instructions throughout.

The Claude Desktop App launched its three-tab architecture in early 2026, unifying what were previously separate products. Your **$20/month Pro subscription** unlocks all three tabs, Opus model access, unlimited Projects, and roughly **5× the usage** of the free tier. Understanding how Chat, Cowork, and Code differ — and when to use each — is the single biggest lever for getting value from your subscription.

---

## Installing Claude Desktop on Windows

### System requirements and download

Windows 10 version 2004 (build 19041) or later is required, and **Windows S Mode must be disabled**. Two additional prerequisites matter: the **Virtual Machine Platform** Windows feature must be enabled for Cowork, and **Git for Windows** must be installed for the Code tab's local sessions.

Download the installer from **claude.com/download** — click "Windows" to get `ClaudeSetup.exe`. The installer requests administrator credentials via UAC; granting admin enables the full feature set including Cowork. Without admin access, Claude installs but Cowork is unavailable. MSIX packages are also available for enterprise deployment via Intune, SCCM, or Group Policy.

**Enable Virtual Machine Platform** before first launch (run as Administrator in PowerShell):
```powershell
Enable-WindowsOptionalFeature -Online -FeatureName VirtualMachinePlatform -All -NoRestart
```

After installation, launch from the Start menu and sign in with your Anthropic account credentials.

### Initial configuration checklist

Open **Settings** immediately after first launch to configure these essentials. Set your default model — **Sonnet 4.6** for everyday use, **Opus 4.6** for complex reasoning. Configure the global keyboard shortcut (commonly Ctrl+Alt+Space on Windows) for pulling up Claude over any application. Enable **Memory** under Capabilities so Claude retains context across conversations. Navigate to **Settings → Extensions** to browse desktop extensions, and **Settings → Connectors** to connect cloud services like Google Drive and Slack.

---

## Understanding the three tabs: Chat, Cowork, and Code

The desktop app presents three tabs at the top of the interface. Each is optimized for different work patterns.

**Chat** is the familiar conversational experience — quick questions, brainstorming, iterative drafting. It supports web search, file drag-and-drop, extended thinking, artifacts, and voice input. Chat is available on all plans including Free, and is best when you want real-time back-and-forth interaction.

**Cowork** is an autonomous background agent. You give it a goal and folder access, and it works independently — reading files, spinning up sub-agents for parallel work, creating deliverables, and saving results back to your filesystem. Cowork runs inside an **isolated virtual machine** with controlled file and network access. It supports scheduled recurring tasks, browser automation via Chrome, and plugins that extend its capabilities. Think of it as leaving a task for a capable coworker rather than having a conversation.

**Code** is Claude Code with a graphical interface — a full development environment for writing, testing, and deploying software. It offers three interaction modes: **Ask** (proposes changes, waits for approval), **Code** (auto-accepts file edits, checks before terminal commands), and **Plan** (outlines approach without touching files). Visual diff review shows exactly what changed with accept/reject controls.

| Aspect | Chat | Cowork | Code |
|--------|------|--------|------|
| **Best for** | Quick exchanges, brainstorming | Complex deliverables, file processing | Building software |
| **Interaction** | Real-time conversation | Autonomous background work | Interactive development |
| **File access** | Upload/drag-drop | Full folder read/write in VM | Full project access |
| **Unique features** | Artifacts, voice, quick entry | Sub-agents, scheduling, plugins | Git integration, visual diffs |

### Subscription tiers at a glance

**Pro ($20/month)** includes all three tabs, access to Opus 4.6, unlimited Projects, Research mode, and Claude for Excel/PowerPoint (beta). Usage runs on a **rolling 5-hour window** of approximately 45 prompts. A weekly cap also exists for sustained heavy usage, affecting fewer than 5% of subscribers. During **peak hours** (weekdays 5am–11am PT), limits burn faster — schedule heavy work for off-peak periods to stretch your allocation. Annual billing at $200/year saves roughly $40.

**Max 5× ($100/month)** and **Max 20× ($200/month)** multiply Pro's usage by 5× and 20× respectively, add priority access during peak hours, and provide early access to new features.

---

## Claude Cowork: autonomous knowledge work

### Getting started with folder access

Cowork's core workflow starts with granting folder access. Switch to the Cowork tab, click "Work in a Folder," and select a specific directory. This creates a **security boundary** — Claude can read, write, create, and delete files only within that mounted folder. The folder is mounted into an isolated VM where all processing occurs.

**Best practice:** Create a dedicated work folder rather than pointing at your entire Documents directory. On Windows, Cowork currently **restricts folder selection to the home directory** (`%USERPROFILE%`) — external drives, NAS mounts, and non-C: partitions cannot be selected. This is a known limitation tracked for improvement.

Permissions follow a principle of least privilege. No file access exists by default; deletion always requires explicit approval via a permission prompt. You can configure read-only versus read-write access, and permissions persist across sessions but remain revocable. Global instructions (Settings → Cowork → Global Instructions) apply to every session, while folder instructions provide project-specific context.

### Built-in skills for document creation

Cowork ships with four built-in skills that activate automatically when you request specific file types. These skills live at `/mnt/skills/public/` inside the VM:

**DOCX (Word)** is the most reliable format — Word documents are XML under the hood, and LLMs handle XML well. Claude creates properly formatted documents with heading hierarchies, tables, and executive summaries. It can even perform tracked-changes editing and redlining workflows.

**PPTX (PowerPoint)** supports creation from scratch or templates, HTML-to-PPTX conversion with formatting, and visual validation via thumbnail grids that catch text cutoff and layout issues.

**XLSX (Excel)** creates spreadsheets with working formulas and formatting. However, the xlsx skill has a significant limitation: it relies on Python libraries expecting clean columnar data. **"Presentation-style" spreadsheets with merged cells, section headers, and multi-region layouts cause parsing failures.** Stick to database-table-like structures for best results.

**PDF** goes beyond reading to support merging, splitting, form-filling, data extraction, and conversion to images.

### The skill creator and custom skills

Cowork includes a built-in **Skill Creator** that interviews you about what you want, then generates a properly structured `SKILL.md` file. It follows a phased process: collecting your skill's purpose, input/output specs, quality standards with examples, and then compiles a Skill Definition Brief. After creation, it can optimize the description for triggering accuracy by generating 20 evaluation queries.

Custom skills live in `~/.claude/skills/` and work in both Cowork and Claude Code. Each skill is a folder containing a `SKILL.md` file with YAML frontmatter (metadata for when/how Claude should use it) and Markdown content (the actual instructions). Skills load on demand — only names and descriptions enter the system prompt initially, consuming roughly **2% of the context window** for all active skills.

### Current limitations worth knowing

Cowork is in **research preview** with several constraints. The desktop app must remain open and the computer awake for tasks to run. Chrome automation is notably slow — every browser interaction requires a screenshot → decision → action → screenshot cycle, meaning three newsletter unsubscriptions took approximately 30 minutes in testing. Memory works within Cowork Projects but does **not persist across standalone sessions**. Sessions cannot be shared with others, and complex multi-step tasks consume significantly more usage allocation than standard Chat.

---

## Claude Code: agentic coding in the terminal

### Installation on Windows — no WSL required

Claude Code now runs **natively on Windows** without WSL, using Git Bash internally. Install Git for Windows first, then run the native installer from PowerShell:

```powershell
irm https://claude.ai/install.ps1 | iex
```

Alternative installation methods include `winget install Anthropic.ClaudeCode` or the legacy `npm install -g @anthropic-ai/claude-code` (requires Node.js 18+). No administrator privileges are needed. After installation, run `claude` in any terminal and follow browser prompts to authenticate. Run `claude doctor` to verify installation health.

If Git Bash isn't found automatically, set its path in settings:
```json
{
  "env": {
    "CLAUDE_CODE_GIT_BASH_PATH": "C:\\Program Files\\Git\\bin\\bash.exe"
  }
}
```

**Windows-specific notes:** Use **Alt+V** (not Ctrl+V) to paste clipboard images. When adding MCP servers that use `npx`, wrap with `cmd /c`: `claude mcp add --transport stdio my-server -- cmd /c npx -y @some/package`. For WSL users, WSL 2 supports sandboxing while WSL 1 does not.

### Essential commands and workflows

Start an interactive session with `claude`, or pass an initial prompt with `claude "explain this codebase"`. Use `claude -p "analyze this code" > output.txt` for one-shot queries. Resume previous sessions with `claude -c` (last session) or `claude -r <session-id>` (specific session).

Key in-session commands include `/init` (generates a starter CLAUDE.md by analyzing your project), `/compact` (summarizes conversation to free context), `/model` (switch models mid-session), `/cost` (show token usage), `/memory` (browse auto-memory files), and `/mcp` (check MCP server status). **Shift+Tab** cycles between normal, auto-accept, and plan modes — plan mode is especially useful before large refactors, as Claude outlines its approach without modifying files.

Reference files directly with `@./path/to/file` in prompts. Run shell commands inline with `!git status`. Toggle extended thinking with **Alt+T**, and use thinking keywords like "think harder" or "ultrathink" for progressively deeper reasoning.

### Git integration and test-driven development

Claude Code has deep, native git integration requiring no special setup. Ask it to "commit my changes with a descriptive message" and it auto-generates commit messages from diffs. It creates git checkpoints before making changes, respects `.gitignore`, warns about committing secrets, and won't push directly to main without permission. The `--worktree` flag creates isolated git worktrees for parallel development with separate Claude sessions.

For test-driven development, Claude naturally writes implementation first — you **must explicitly prompt for TDD**. The effective pattern is: first ask Claude to "write FAILING tests for [feature], do NOT write implementation yet," then "implement the minimum code to make these tests pass," then "refactor while ensuring tests still pass." Add TDD conventions to your CLAUDE.md file for persistent enforcement, and consider using PostToolUse hooks to auto-run tests after every file edit.

---

## CLAUDE.md files and project configuration

### The hierarchy of memory files

CLAUDE.md is Claude Code's persistent project memory — a Markdown file loaded automatically into the context window at every session start. It survives `/compact` operations (re-read from disk) and serves as the highest-leverage configuration point.

Files load in this priority order, with all layers combining into one system prompt:

| File | Scope | Git-tracked |
|------|-------|-------------|
| `~/.claude/CLAUDE.md` | All projects (global preferences) | N/A |
| `./CLAUDE.md` (project root) | Team-shared project instructions | Yes |
| `./CLAUDE.local.md` | Personal project overrides | No (gitignored) |
| `./.claude/rules/*.md` | Path-scoped modular instructions | Yes |
| Subdirectory `CLAUDE.md` | Directory-specific rules | Yes |

### What to include and what to leave out

An effective CLAUDE.md contains your project overview, architecture map, tech stack, essential commands (`npm run dev`, `npm test`, `npm run lint-fix`), coding conventions, testing requirements, git conventions, and critical gotchas — the things Claude would get wrong without explicit guidance. **Keep it under 200 lines.** Frontier LLMs follow approximately **150–200 instructions** reliably; beyond that, adherence drops.

For every line, ask: "Would Claude make a mistake without this?" Don't use CLAUDE.md as a linter — use actual linters via hooks instead. Link to documentation files rather than embedding them (`"For complex usage, see docs/api.md"` rather than `@docs/api.md`, which embeds the entire file every run). When prohibiting something, always provide the alternative: "Never use `--foo-bar`; prefer `--baz` instead."

CLAUDE.md instructions are **advisory, not enforced** — Claude follows them roughly 70–80% of the time. For critical safety rules (never delete production data, never push to main), use **hooks** for deterministic enforcement instead.

### The .claude directory structure

The `.claude/` directory at your project root organizes all Claude Code configuration:

```
.claude/
├── settings.json            # Team-shared permissions, hooks, model config
├── settings.local.json      # Personal settings (auto-gitignored)
├── .mcp.json                # MCP server configurations
├── rules/                   # Path-scoped modular instructions
├── skills/                  # Reusable workflows
├── agents/                  # Specialized sub-agent definitions
├── commands/                # Custom slash commands
├── agent-memory/            # Shared agent memory (team)
└── agent-memory-local/      # Personal agent memory (gitignored)
```

Auto-memory accumulates at `~/.claude/projects/<project-hash>/memory/`, where `MEMORY.md` serves as an index with its first 200 lines loaded every session. This stores debugging insights, architecture observations, and code patterns Claude discovers while working.

---

## Connectors, MCP, and the integration ecosystem

### Web connectors versus desktop extensions

Connectors link Claude to external services and data sources. They come in two forms: **web connectors** (remote MCP servers running in the cloud) and **desktop extensions** (local MCP servers running on your machine). Web connectors sync across all Claude apps — desktop, web, mobile — and handle cloud services like Google Drive, Slack, and Notion. Desktop extensions keep data on your machine and are ideal for confidential documents, local databases, and developer tools.

Browse and install connectors at **Settings → Connectors**. Click "Connect" on any connector, authenticate via OAuth, and it becomes available in conversations. Toggle connectors per-conversation using the "+" button in the chat interface. Free users can add one custom connector; paid plans unlock the full catalog of **over 50 curated integrations**.

Desktop extensions use `.mcpb` (MCP Bundle) files that package everything needed for single-click installation — no Node.js, no JSON editing, no dependency management required.

### The connectors catalog

The directory spans every major work category. **Google Workspace** connectors (Gmail, Google Calendar, Google Drive) are available natively to all users. Gmail can search and read emails and draft replies but **cannot send on your behalf**. Google Calendar views events, finds free time, and audits meeting patterns. Google Drive searches documents, and its cataloging feature indexes your Google Docs for automatic context retrieval.

Notable integrations include **Slack** (draft and preview messages, summarize channels), **Notion** and **Linear** for project management, **GitHub** for repository and issue management, **Canva** and **Figma** for design, **Stripe** and **PayPal** for finance, **Honeycomb** and **Sentry** for engineering observability, and automation platforms like **Zapier** and **n8n**. Nine integrations now offer **interactive UI** rendered directly inside Claude conversations, including Slack, Canva, Figma, and Asana.

### The Chrome extension

The **Claude in Chrome** extension (beta) lets Claude read, click, navigate, and automate tasks in your browser from a side panel. Install from the Chrome Web Store, sign in, and choose between "Ask before acting" or "Act without asking" permission modes. It can record workflows (perform steps manually while recording, then save as a reusable shortcut), schedule recurring browser tasks, and manage multiple tabs simultaneously.

On Pro plans, the Chrome extension is **limited to Haiku 4.5** — Max and Team plans get model choice. It works only in Chrome and Edge (not Brave, Arc, or mobile browsers). JavaScript dialogs block Claude and must be dismissed manually. Avoid using it for financial transactions or sensitive data operations due to prompt injection risks on untrusted sites.

### Model Context Protocol (MCP) fundamentals

MCP is the **open-source standard** underpinning all Claude integrations — think of it as a USB-C port for AI. It defines a client-server architecture where Claude (the host) communicates with MCP servers that expose tools, resources, and prompts. Servers can access local resources (files, databases) or remote APIs. Communication happens via **stdio** (local servers), **Streamable HTTP** (remote servers), or **SSE** (legacy remote).

For Claude Desktop, MCP servers are configured in `claude_desktop_config.json` located at `%APPDATA%\Claude\claude_desktop_config.json` on Windows. A typical configuration:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "C:\\Program Files\\nodejs\\npx.cmd",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "C:\\Users\\username\\Projects"],
    },
    "github": {
      "command": "C:\\Program Files\\nodejs\\npx.cmd",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": { "GITHUB_PERSONAL_ACCESS_TOKEN": "<YOUR_TOKEN>" }
    }
  }
}
```

**Windows tip:** Using `"command": "npx"` often causes connection errors. Use the **full path** `"C:\\Program Files\\nodejs\\npx.cmd"` instead. After editing, completely restart Claude Desktop and look for the hammer/tools icon in the chat input.

For Claude Code, add servers via the CLI: `claude mcp add github -- cmd /c npx -y @modelcontextprotocol/server-github`. Check status with `/mcp` during a session. Over **5,000 community MCP servers** exist, cataloged at github.com/modelcontextprotocol/servers and github.com/wong2/awesome-mcp-servers.

---

## The Cowork plugin system

### Four building blocks, one package

A Cowork plugin bundles up to four component types into a single installable package:

- **Skills** — domain knowledge in `SKILL.md` files that Claude draws on automatically when context requires it
- **Slash commands** — explicit functions invokable with `/command` syntax for targeted actions (e.g., `/sales:call-prep`)
- **MCP connectors** — pre-built integrations to specific tools defined in `.mcp.json`
- **Sub-agents** — specialized mini-personas that handle specific domains, enabling parallel processing (10 files in parallel reduced ~30 minutes to ~4 minutes in testing)

Plugins are **cross-compatible** between Cowork and Claude Code, and are entirely file-based — Markdown and JSON, no build steps, no infrastructure.

### Plugin structure and manifest

Every plugin follows a standard directory layout:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json          # Manifest: name, version, author
├── .mcp.json                # MCP connections (optional)
├── commands/                # Slash commands (Markdown files)
├── skills/                  # Domain knowledge (SKILL.md files)
└── agents/                  # Sub-agent instructions (optional)
```

**Critical rule:** Only `plugin.json` goes inside `.claude-plugin/`. All other directories must be at the plugin root level.

The manifest is minimal:
```json
{
  "name": "my-plugin",
  "description": "What this plugin does",
  "version": "1.0.0",
  "author": { "name": "Your Name" }
}
```

Each `SKILL.md` requires YAML frontmatter with `name`, `description` (200 chars max — Claude uses this to decide when to invoke), and optional fields like `allowed-tools` (restrict capabilities), `disable-model-invocation` (only user can trigger), and `user-invocable` (only Claude can trigger). The `description` field is the **primary mechanism** determining whether Claude invokes a skill — write it to be slightly "pushy" about when the skill applies, since Claude tends to undertrigger.

### Installing and building plugins

Install from the plugin library via Cowork tab → Customize → Browse plugins → Install. Upload custom `.plugin` zip files for personal or shared plugins. Anthropic's **knowledge-work-plugins** GitHub repository provides 11+ official plugins covering Productivity, Sales, Customer Support, Product Management, Marketing, Legal, Finance, Data Analysis, Engineering, Design, Human Resources, and Operations — each with pre-configured MCP connectors for major SaaS tools.

The built-in **Plugin Create** tool walks you through building custom plugins from scratch by defining your workflow in natural language. It identifies necessary capabilities, generates the complete scaffolding, and can optimize skill descriptions for triggering accuracy.

---

## Power user techniques for Pro subscribers

### Maximizing your usage allocation

Pro's rolling 5-hour window resets after 5 hours from your first prompt. A weekly cap exists for sustained heavy users. Since March 2026, **peak-hour throttling** (weekdays 5am–11am PT) burns limits faster while off-peak gives more capacity. Schedule intensive work — batch file processing, long Cowork sessions, deep research — for evenings and weekends.

Use **Sonnet 4.6 as your default model** and reserve Opus for genuinely complex reasoning. Batch related questions into single structured prompts. Use Projects to reuse context (leverages caching). Start new conversations for new topics rather than letting threads accumulate tokens. In Claude Code, use `/compact` when context fills up and `/clear` when switching tasks entirely.

### Extended thinking and Research mode

Extended thinking gives Claude dedicated reasoning space before responding. Enable it via the "Search and tools" button or **Alt+T** in Claude Code. It's most valuable for complex math, architecture decisions, multi-step analysis, and code debugging — not for simple lookups. In Claude Code, thinking keywords escalate reasoning depth: "think" → "think harder" → "think step by step" → "ultrathink" (maximum depth).

**Research mode** is best for comprehensive information gathering requiring multiple tool calls over 1–3 minutes. It auto-enables extended thinking and excels at synthesizing multi-source reports, competitor comparisons, and document updates with web information.

### Memory, Projects, and artifacts

**Memory** (Settings → Capabilities) lets Claude retain preferences and context across all conversations — enable it immediately to stop repeating yourself. You can directly tell Claude what to remember, edit memories manually, or import preferences from ChatGPT.

**Projects** organize related conversations with persistent uploaded documents and custom instructions. Create separate projects for each work domain. On paid plans, RAG auto-scales when project knowledge approaches context limits, expanding capacity up to 10×. Project instructions stack with your profile preferences, so avoid repetition.

**Artifacts** auto-generate when Claude produces significant content — code snippets, interactive HTML apps, data visualizations, documents. Enable "AI-powered Artifacts" in Settings for LLM-powered interactive apps that work without API keys. Every iteration saves automatically with full version history, and published artifacts generate shareable links.

### Network configuration and enterprise features

Cowork's network egress is controlled under Settings → Capabilities → "Code execution and file creation." Options range from none to package managers only (default) to specific domains to all domains. Add individual domains to the allowlist for targeted access. Claude Code supports `allowedDomains` in sandbox settings for OS-level enforcement.

Enterprise plans add audit logs (covering chat, connector, and Code tab activity but **not Cowork session content**), a Compliance API for SIEM integration, configurable data retention (minimum 30 days), and Zero Data Retention options. Windows enterprise deployment supports registry-based configuration at `HKLM:\SOFTWARE\Policies\Claude` for controlling auto-updates, extensions, and Claude Code access. Tenant restrictions work with Zscaler, Palo Alto Prisma, and other proxies.

## Conclusion

Claude's desktop ecosystem on Windows delivers three distinct but complementary workflows through a single application. The most important setup steps are enabling Virtual Machine Platform and installing Git before first launch — these unlock Cowork and Code respectively. For a Pro subscriber, the highest-impact habits are using Sonnet as default while reserving Opus for complexity, scheduling heavy work outside peak hours, investing time in CLAUDE.md files for any recurring project, and connecting Google Workspace immediately to eliminate manual context-copying.

The plugin and MCP ecosystem transforms Claude from a standalone assistant into an orchestration layer across your entire toolchain. Start with Anthropic's official plugins and Google Workspace connectors, then expand to custom MCP servers and skills as your workflows mature. The platform is evolving rapidly — Cowork launched on Windows only in February 2026, and new connectors and capabilities ship weekly.