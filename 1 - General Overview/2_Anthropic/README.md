---
title: Anthropic Claude
description: Comprehensive guide to Anthropic Claude — models, applications, and customizations
created: 2026-04-07
updated: 2026-04-07
topics:
    - Claude
    - Anthropic
    - Claude Code
    - Chat
    - Cowork
    - Projects
    - Models
    - Excel
    - PowerPoint
    - MCP
---

# Anthropic Claude

Anthropic Claude is a family of large language models built by [Anthropic](https://www.anthropic.com/), a safety-focused AI company founded in 2021 by former OpenAI researchers. Claude is designed around the principle of being helpful, harmless, and honest — trained using a technique called Constitutional AI (CAI) that aligns the model to a set of principles rather than relying solely on human feedback.

### Why Claude

- **Long context windows** — up to 1M tokens on Opus and Sonnet, meaning Claude can process entire codebases, lengthy legal documents, or full book manuscripts in a single conversation.
- **Instruction following** — Claude excels at adhering to detailed, multi-step instructions, making it reliable for structured business workflows (report generation, data extraction, compliance reviews).
- **Code generation & reasoning** — Opus in particular rivals or exceeds frontier models on agentic coding benchmarks, multi-step math, and complex logic tasks.
- **Safety & refusals** — Claude is less likely to produce harmful, biased, or fabricated content compared to many competitors, which matters in regulated industries (finance, healthcare, legal).
- **Artifacts & tools** — Claude's application surfaces (web, desktop, code) support rendered outputs (HTML, React, SVG), file uploads, web search, and extensible tool use via MCP.

### How Claude Compares

| Dimension | Claude (Anthropic) | GPT-4o (OpenAI) | Gemini 2.5 (Google) |
|---|---|---|---|
| **Context window** | Up to 1M tokens | 128K tokens | 1M tokens |
| **Coding** | Opus 4.6 leads on SWE-bench | Strong, GPT-4o competitive | Strong on benchmarks |
| **Safety** | Constitutional AI, conservative refusals | RLHF-based alignment | Google safety layer |
| **Multimodal** | Text + vision + PDF | Text + vision + audio + video | Text + vision + audio + video |
| **Tool use** | MCP (open standard) | Function calling + plugins | Extensions + Grounding |
| **Best for** | Long-form analysis, code, business writing | General purpose, broad integrations | Search-grounded tasks, multimodal |

> **When to choose Claude:** You need deep reasoning over long documents, reliable structured output, agentic coding workflows, or operate in a domain where safety and accuracy matter more than breadth of integrations.

---

## Models

Anthropic offers three model tiers — **Haiku**, **Sonnet**, and **Opus** — each balancing speed, intelligence, and cost differently. All models in the current 4.5/4.6 generation share the same architecture but are trained at different scales.

```
┌─────────────────────────────────────────────────────────┐
│                    Claude Model Tiers                    │
├──────────┬──────────────┬──────────────┬────────────────┤
│          │    Haiku     │    Sonnet    │     Opus       │
│          │   (Light)    │  (Balanced)  │   (Frontier)   │
├──────────┼──────────────┼──────────────┼────────────────┤
│ Speed    │  ★★★★★       │  ★★★★        │  ★★★           │
│ Intel.   │  ★★★         │  ★★★★        │  ★★★★★         │
│ Cost     │  $            │  $$          │  $$$           │
│ Context  │  200K        │  1M          │  1M            │
│ Output   │  64K         │  64K         │  128K          │
└──────────┴──────────────┴──────────────┴────────────────┘
```

### Thinking vs Non-Thinking

Claude models support **extended thinking** (also called "thinking mode"), where the model reasons step-by-step internally before producing a final answer. This dramatically improves performance on math, logic, coding, and multi-step analysis tasks.

- **Adaptive thinking** (Opus 4.6 & Sonnet 4.6) — the model automatically decides how much to think based on task complexity. Controlled via an `effort` parameter: `low`, `medium`, or `high`.
- **Manual thinking** (older models) — you set a `budget_tokens` value to cap internal reasoning.

> **Rule of thumb:** Use thinking mode for anything requiring multi-step reasoning (code debugging, financial analysis, complex writing). Skip it for simple Q&A or quick lookups where speed matters more.

| Effort Level | When to Use | Example Tasks |
|---|---|---|
| **Low** | Simple, fast responses | Summarization, classification, reformatting |
| **Medium** | Moderate reasoning | Code review, report drafting, data analysis |
| **High** | Deep, multi-step reasoning | Architecture design, complex debugging, legal analysis |

> [Docs: Extended Thinking](https://docs.anthropic.com/en/docs/build-with-claude/extended-thinking)

---

### Haiku

**Model ID:** `claude-haiku-4-5-20251001`
**Context:** 200K tokens | **Max Output:** 64K tokens
**Pricing:** ~$1 / $5 per million tokens (input / output)

Haiku is Anthropic's **speed-optimized** model — the fastest and cheapest in the lineup. It's designed for high-volume, latency-sensitive workloads where you need a "good enough" answer instantly.

**Strengths:**
- Extremely fast response times (sub-second for short prompts)
- Lowest cost per token — ideal for batch processing thousands of items
- Still surprisingly capable for its size — handles summarization, classification, extraction, and simple code tasks well
- Supports extended thinking for when you need a quality boost

**Weaknesses:**
- Smaller context window (200K vs 1M for Sonnet/Opus)
- Less reliable on complex multi-step reasoning, nuanced writing, or ambiguous instructions
- More prone to hallucination on niche or specialized topics
- May miss subtle context in long conversations

**When to use Haiku:**
- Real-time applications (chatbots, autocomplete, inline suggestions)
- High-volume pipelines (classifying thousands of support tickets, extracting fields from invoices)
- Cost-sensitive workloads where you'd rather run 5x more queries than use a bigger model
- Prototyping and iteration — test your prompts cheaply before upgrading to Sonnet/Opus

> [Docs: Choosing a Model](https://docs.anthropic.com/en/docs/about-claude/models)

---

### Sonnet

**Model ID:** `claude-sonnet-4-6`
**Context:** 1M tokens | **Max Output:** 64K tokens
**Pricing:** ~$3 / $15 per million tokens (input / output)

Sonnet is the **balanced workhorse** — it hits a sweet spot between intelligence and speed that makes it the default choice for most production applications and daily use.

**Strengths:**
- Strong reasoning and coding ability at fast speeds
- Full 1M token context — can process entire codebases, long reports, or multi-document analysis
- Excellent at structured output (JSON, tables, formatted reports)
- Great instruction following — reliable for business workflows
- Cost-effective for the quality level

**Weaknesses:**
- Not quite as capable as Opus on the hardest reasoning tasks (complex math proofs, deeply ambiguous problems)
- Can occasionally over-simplify when a problem requires truly deep analysis
- Slightly slower than Haiku for real-time applications

**When to use Sonnet:**
- **Default choice** for most tasks — if you're unsure, start here
- Daily business work (drafting emails, analyzing documents, writing reports)
- Code generation and review for standard development tasks
- Production APIs where you need a balance of quality, speed, and cost
- Long-document analysis (contracts, research papers, financial filings)

> Sonnet is what powers most Claude interactions across web, desktop, and code by default.

---

### Opus

**Model ID:** `claude-opus-4-6`
**Context:** 1M tokens | **Max Output:** 128K tokens
**Pricing:** ~$5 / $25 per million tokens (input / output)

Opus is Anthropic's **frontier model** — the most intelligent Claude available. It leads on agentic coding benchmarks (SWE-bench), complex reasoning, and tasks that require sustained multi-step problem solving.

**Strengths:**
- Highest reasoning capability — excels at problems other models struggle with
- 128K output tokens — can generate extremely long, detailed responses
- Best-in-class agentic coding (autonomous bug fixing, feature implementation, multi-file refactors)
- Superior at nuance, ambiguity resolution, and creative problem-solving
- Most reliable at following complex, multi-constraint instructions

**Weaknesses:**
- Slowest of the three tiers — not ideal for real-time or latency-sensitive applications
- Most expensive per token
- Overkill for simple tasks (you're paying for intelligence you don't need)

**When to use Opus:**
- Complex software engineering (architecture design, multi-file refactors, debugging subtle issues)
- High-stakes analysis (financial modeling, legal review, medical literature synthesis)
- Tasks where accuracy is critical and cost is secondary
- Agentic workflows — Claude Code uses Opus for its most capable mode
- Research and exploration of novel problems

> [Docs: Models Overview](https://docs.anthropic.com/en/docs/about-claude/models)

---

## Claude Applications

Claude is available across multiple application surfaces, each designed for different workflows. Here's how they relate:

```
┌──────────────────────────────────────────────────────────────────────┐
│                        Claude Applications                          │
│                                                                      │
│  ┌─────────────┐   ┌──────────────────────────────────────────────┐ │
│  │  claude.ai  │   │           Claude Desktop                     │ │
│  │   (Web)     │   │  ┌──────┐ ┌────────┐ ┌──────┐ ┌──────────┐ │ │
│  │             │   │  │ Chat │ │ Cowork │ │ Code │ │ Projects │ │ │
│  │  - Chat     │   │  └──────┘ └────────┘ └──────┘ └──────────┘ │ │
│  │  - Projects │   │  + MCP Servers  + Local Files  + Extensions │ │
│  │  - Artifacts│   └──────────────────────────────────────────────┘ │
│  │  - Search   │                                                     │
│  └─────────────┘   ┌──────────────────────────────────────────────┐ │
│                     │           Claude Code (CLI/IDE)              │ │
│                     │  Terminal + VS Code + JetBrains              │ │
│                     │  + Full file system + Git + Shell execution  │ │
│                     └──────────────────────────────────────────────┘ │
└──────────────────────────────────────────────────────────────────────┘
```

| Feature | Web | Desktop | Code (CLI/IDE) |
|---|---|---|---|
| Chat conversations | Yes | Yes | Yes |
| File uploads | Yes | Yes | Yes (reads local files) |
| Artifacts (rendered HTML/React) | Yes | Yes | No |
| Web search | Yes | No | Via MCP |
| MCP servers | Some (remote) | Yes (local + remote) | Yes (local + remote) |
| Local file system access | No | Limited | Full |
| Terminal / shell execution | No | No | Yes |
| Git integration | No | No | Yes |
| Projects & knowledge bases | Yes | Yes | Via CLAUDE.md |
| Cowork (background tasks) | No | Yes | N/A (always agentic) |
| Plugins & extensions | No | Yes | Yes |

---

### Web

**URL:** [claude.ai](https://claude.ai)

The Claude web interface is the most accessible way to use Claude — no installation required, works in any browser.

**Key features:**
- **Artifacts** — Claude can render interactive HTML, React components, SVGs, and Mermaid diagrams in a side panel. Great for visualizations, prototypes, and formatted documents.
- **File uploads** — Drag and drop PDFs, images, CSVs, Word docs, and more directly into the conversation. Claude can analyze, summarize, and extract data from them.
- **Web search** — Claude can search the web in real-time to ground answers in current information.
- **Projects** — Create persistent knowledge bases with custom instructions (see [[#Projects]] below).
- **Model selection** — Switch between Haiku, Sonnet, and Opus mid-conversation.

**Strengths:**
- Zero setup — works immediately in any browser
- Best artifact rendering experience
- Web search built in
- Shareable conversation links

**Weaknesses:**
- No local file system access
- No MCP server support (limited to remote integrations)
- No terminal or code execution
- Can't run background tasks

**When to use:** Quick questions, document analysis, brainstorming, writing tasks, sharing conversations with colleagues, or any time you're away from your development machine.

---

#### Chat

Chat is the core conversational interface available on both web and desktop. It's the default mode when you open Claude.

**How it works:** You send messages, Claude responds. Conversations are threaded and persistent — you can return to them later. Each message can include text, files, or images.

**Key capabilities:**
- Multi-turn conversations with full context retention
- File and image analysis inline
- Model switching mid-conversation
- Artifact generation (web) or tool use (desktop)
- Conversation search and organization

**When to use:** Any ad-hoc question, analysis, writing, or brainstorming task. Chat is the "default mode" — start here unless you have a specific reason to use another surface.

---

### Desktop

**Platforms:** macOS, Windows, Linux
**Download:** [claude.ai/download](https://claude.ai/download)

The Claude Desktop app provides everything the web interface does, plus deep OS integration and local tool connectivity.

**Key additions over web:**
- **MCP server support** — Connect Claude to local tools, databases, file systems, APIs, and more via the Model Context Protocol. This is the killer feature of Desktop.
- **Cowork mode** — Claude works on tasks in the background while you do other things (see [[#Cowork]] below).
- **System-level integration** — Keyboard shortcuts, notification support, always-available via system tray.
- **Local file access** — More direct interaction with files on your machine (via MCP).

**Strengths:**
- MCP servers unlock virtually unlimited tool integrations
- Cowork mode for autonomous background work
- Native OS experience (faster, keyboard shortcuts, notifications)
- All web features plus local capabilities

**Weaknesses:**
- Requires installation
- MCP server setup can be technical (JSON configuration)
- No direct terminal/shell access (use Claude Code for that)

**When to use:** Daily driver for power users. If you work with local files, need tool integrations, or want Claude running tasks in the background, Desktop is the right choice.

> [Docs: Claude Desktop](https://claude.ai/download)

---

#### Chat

Chat on Desktop works identically to web chat, with the same conversational interface and capabilities. The key difference is that Desktop chat has access to any MCP servers you've configured, meaning Claude can use tools (read files, query databases, call APIs) directly within the chat flow.

**Example:** With a GitHub MCP server configured, you can ask Claude in Desktop chat to "list my open PRs" and it will call the GitHub API directly — no copy-pasting needed.

---

#### Cowork

Cowork is a **background task mode** available in Claude Desktop. Instead of a back-and-forth conversation, you give Claude a task and it works on it autonomously — reading files, using tools, and producing deliverables while you focus on other work.

**How it works:**
1. Describe a task (e.g., "Review this document and create a summary with action items")
2. Claude works in the background, using available tools and MCP servers
3. You receive a notification when the task is complete
4. Review the output and provide feedback if needed

**Strengths:**
- Frees you from waiting — Claude works while you do other things
- Can handle multi-step tasks that would be tedious in chat (research, analysis, document creation)
- Full access to MCP servers and tools
- Great for tasks that take minutes, not seconds

**Weaknesses:**
- Less interactive — you can't guide Claude mid-task as easily as in chat
- Requires well-defined task descriptions (garbage in, garbage out)
- Limited to Desktop app

**When to use:**
- Document analysis and summarization of large files
- Research tasks that require multiple tool calls
- Report generation from data sources
- Any task where you'd rather delegate and check back later

---

#### Code

**Claude Code** is Anthropic's **agentic coding tool** — available as a CLI, a VS Code extension, a JetBrains extension, and a web app at [claude.ai/code](https://claude.ai/code).

**How it works:** Claude Code has full access to your development environment — it can read and write files, execute terminal commands, run tests, use git, and interact with GitHub. It operates as an autonomous coding agent that can implement features, fix bugs, refactor code, and manage your repository.

**Key capabilities:**
- **File operations** — Read, write, edit, and create files across your entire project
- **Terminal execution** — Run build commands, tests, linters, scripts, and any shell command
- **Git integration** — Create commits, branches, PRs; review diffs; manage your repo
- **Multi-file edits** — Coordinate changes across many files simultaneously
- **Agentic workflows** — Give Claude a task and it plans, implements, tests, and iterates autonomously
- **Extensible** — Skills, plugins, MCP servers, hooks, CLAUDE.md, and custom agents

**Strengths:**
- The most powerful Claude surface for software development
- Autonomous multi-step task execution
- Full project context (reads your entire codebase)
- Highly customizable via CLAUDE.md, skills, hooks, and plugins
- Works in terminal (CLI), VS Code, JetBrains, and web

**Weaknesses:**
- Requires trust — Claude can modify files and run commands (permission system mitigates this)
- Learning curve for customization (CLAUDE.md, hooks, MCP config)
- Token-intensive for large codebases (but 1M context helps)
- Not designed for non-coding tasks (use Chat/Desktop for those)

**When to use:**
- Any software development task: feature implementation, bug fixing, refactoring
- Code review and analysis
- Repository maintenance (documentation, CI/CD, dependency updates)
- Complex multi-file changes that would be tedious to do manually

> [Docs: Claude Code](https://docs.anthropic.com/en/docs/claude-code)

---

#### Projects

Projects are **persistent knowledge bases** that give Claude long-term context about a specific domain, team, or workflow. Available on both web and desktop.

**How they work:**
1. Create a project and give it a name and description
2. Upload reference documents (PDFs, code files, data, documentation)
3. Write custom instructions that tell Claude how to behave in this project's context
4. Every conversation within the project automatically includes these documents and instructions

**Example project setups:**

| Project | Documents | Custom Instructions |
|---|---|---|
| **Q4 Financial Review** | 10-K filing, earnings transcript, analyst reports | "Always cite page numbers. Use conservative estimates. Format as executive summary." |
| **Product Docs Writer** | Style guide, API reference, existing docs | "Match the voice and format of existing documentation. Use the API reference for accuracy." |
| **Code Review Helper** | Architecture docs, coding standards, PR template | "Review against our coding standards. Flag security issues. Suggest tests." |

**Strengths:**
- Persistent context — no need to re-upload files or re-explain instructions every conversation
- Up to ~200K tokens of project knowledge
- Custom instructions shape every response
- Shareable with team members (on team plans)

**Weaknesses:**
- Limited to ~200K tokens of uploaded context (not the full model context window)
- Documents are static — you need to re-upload when they change
- Custom instructions require iteration to get right

**When to use:**
- Recurring workflows where you'd otherwise paste the same context repeatedly
- Team knowledge bases (shared style guides, procedures, reference docs)
- Domain-specific assistants (finance, legal, product, engineering)

> [Docs: Projects](https://support.anthropic.com/en/articles/9517075-what-are-projects)

---

## Customizations & Extensions

Claude offers a rich ecosystem of customization mechanisms that let you tailor its behavior, connect it to external tools, and automate workflows. These range from simple (a markdown file) to powerful (programmatic hooks and plugins).

```
┌──────────────────────────────────────────────────────────────────┐
│                 Customization & Extension Layers                 │
│                                                                  │
│  ┌────────────┐  Simple, declarative, no code required           │
│  │ CLAUDE.md  │  → Project instructions & conventions            │
│  └────────────┘                                                  │
│  ┌────────────┐  Markdown-based, easy to create                  │
│  │   Skills   │  → Reusable prompts & workflows                  │
│  └────────────┘                                                  │
│  ┌────────────┐  Configuration-based                             │
│  │ Connectors │  → External data sources (Notion, Drive, etc.)   │
│  └────────────┘                                                  │
│  ┌────────────┐  JSON config + external servers                  │
│  │MCP Servers │  → Tools, APIs, databases, file systems          │
│  └────────────┘                                                  │
│  ┌────────────┐  JSON config + shell commands or prompts         │
│  │   Hooks    │  → Lifecycle automation (format, lint, validate)  │
│  └────────────┘                                                  │
│  ┌────────────┐  Packages combining all of the above             │
│  │  Plugins   │  → Shareable bundles of skills, hooks, agents    │
│  └────────────┘                                                  │
└──────────────────────────────────────────────────────────────────┘
```

| Mechanism | Complexity | Scope | Best For |
|---|---|---|---|
| **CLAUDE.md** | Low | Project or user | Coding conventions, project context |
| **Skills** | Low | User or project | Reusable prompts, slash commands |
| **Connectors** | Low | Organization | Connecting SaaS data (Google Drive, Notion) |
| **MCP Servers** | Medium | User or project | Tool integrations (GitHub, databases, APIs) |
| **Hooks** | Medium | User or project | Automated formatting, linting, validation |
| **Slash Commands** | Low | User or project | Quick-access actions (now part of Skills) |
| **Plugins** | High | Shareable | Bundled extensions for distribution |
| **Custom Agents** | Medium | User or project | Specialized autonomous sub-agents |

---

### Skills

Skills are **reusable prompt templates** that you can invoke with a slash command (e.g., `/commit`, `/review-pr`). They're the primary way to create custom workflows in Claude Code and Desktop.

**How they work:**
A skill is a markdown file with YAML frontmatter stored in a specific location. When invoked, the skill's content is injected into the conversation as instructions.

**File structure:**
```
~/.claude/skills/my-skill/          # Personal (all projects)
  SKILL.md
.claude/skills/my-skill/            # Project-level (shared via git)
  SKILL.md
```

**Example skill** (`~/.claude/skills/code-review/SKILL.md`):
```markdown
---
name: code-review
description: Review code changes for bugs, style, and security issues
allowed-tools:
  - Read
  - Grep
  - Glob
  - Bash(git diff*)
---

Review the current git diff for:
1. Bugs or logic errors
2. Security vulnerabilities
3. Style guide violations
4. Missing error handling
5. Test coverage gaps

Format findings as a markdown checklist with severity levels.
```

**Invoke it:** Type `/code-review` in Claude Code or Desktop.

**Key features:**
- **Dynamic context** — Use `` !`command` `` syntax to inject live data (e.g., `` !`git diff` `` inserts the current diff)
- **Tool restrictions** — Limit which tools the skill can use via `allowed-tools`
- **Auto-invocation** — Claude can detect when a skill is relevant and suggest it (disable with `disable-model-invocation: true`)
- **Fork context** — Run in an isolated subagent with `context: fork`

**When to use:** Any workflow you repeat regularly — code review, commit messages, PR creation, report generation, data analysis templates.

> [Docs: Skills](https://docs.anthropic.com/en/docs/claude-code/skills)

---

### Connectors

Connectors let you **bring external data into Claude** from SaaS tools and cloud services — like Google Drive, Notion, Confluence, or SharePoint — without building custom integrations.

**How they work:**
Connectors are configured at the organization level (typically by admins on Claude for Work/Teams plans). Once set up, Claude can search and reference content from connected services directly in conversations.

**Example use cases:**
- Connect Google Drive so Claude can reference your team's documentation
- Connect Confluence so Claude can answer questions from your knowledge base
- Connect Notion databases for project tracking context

**Strengths:**
- No code required — admin configuration only
- Claude can search across connected sources
- Keeps data fresh (pulls from live sources)
- Organization-wide availability

**Weaknesses:**
- Limited to supported platforms (not all SaaS tools have connectors yet)
- Requires admin setup and permissions
- Read-only — Claude can query but typically can't write back
- Primarily available on business/enterprise plans

**When to use:** When your team's knowledge lives in external tools and you want Claude to reference it without manual copy-pasting.

> [Docs: Connectors](https://support.anthropic.com/en/articles/11066825-about-connectors)

---

### Claude.md

CLAUDE.md is a **plain markdown file** that provides persistent instructions to Claude at the start of every session. It's the simplest and most important customization mechanism — think of it as a README that Claude reads before every conversation.

**Where to put it:**

| Location | Scope | Shared? |
|---|---|---|
| `./CLAUDE.md` or `./.claude/CLAUDE.md` | Project (this repo) | Yes (commit to git) |
| `./CLAUDE.local.md` | Project (personal) | No (gitignored) |
| `~/.claude/CLAUDE.md` | All projects (personal) | No |
| OS managed path | Organization-wide | Admin-managed |

**Example CLAUDE.md:**
```markdown
# CLAUDE.md

## Project Overview
This is a Node.js REST API using Express, TypeScript, and PostgreSQL.

## Conventions
- Use camelCase for variables, PascalCase for types
- All API responses use the `ApiResponse<T>` wrapper type
- Tests go in `__tests__/` next to the source file
- Never use `any` — always type explicitly

## Commands
- Build: `npm run build`
- Test: `npm test`
- Lint: `npm run lint`

## Architecture
- `src/routes/` — Express route handlers
- `src/services/` — Business logic
- `src/models/` — Database models (Prisma)
- `src/middleware/` — Auth, logging, error handling
```

**Advanced features:**
- **Rules directory** — For large projects, use `.claude/rules/*.md` files with `paths` frontmatter to load rules only when relevant files are edited
- **Imports** — Reference other files with `@path/to/file` syntax
- **Keep it concise** — Under 200 lines for best adherence

**When to use:** Every project. Even a minimal CLAUDE.md with build commands and conventions dramatically improves Claude's output quality.

> [Docs: CLAUDE.md](https://docs.anthropic.com/en/docs/claude-code/claude-md)

---

### MCP Servers

The **Model Context Protocol (MCP)** is an open standard created by Anthropic that lets Claude connect to external tools, APIs, databases, and services. MCP servers are the bridge between Claude and the outside world.

**How it works:**

```
┌──────────┐         ┌─────────────┐         ┌──────────────┐
│  Claude   │ ──MCP── │  MCP Server  │ ──API── │ External     │
│  (Client) │         │  (Bridge)    │         │ Service      │
└──────────┘         └─────────────┘         └──────────────┘

Examples:
  Claude ──MCP── GitHub Server ──API── GitHub.com
  Claude ──MCP── Postgres Server ──SQL── Your Database
  Claude ──MCP── Filesystem Server ──── Local Files
```

**Configuration** (`.mcp.json` in project root or `~/.claude/.mcp.json` for personal):
```json
{
  "mcpServers": {
    "github": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "ghp_..."
      }
    },
    "postgres": {
      "type": "stdio",
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://localhost/mydb"]
    }
  }
}
```

**Transport types:**
- **stdio** — Local process (most common for local tools)
- **SSE** — Server-sent events (remote servers)
- **HTTP** — Standard HTTP (cloud services)

**Popular MCP servers:**
- **GitHub** — PRs, issues, repos, code search
- **PostgreSQL / SQLite** — Database queries
- **Filesystem** — Local file operations
- **Slack** — Read/send messages
- **Google Drive** — Document access
- **Sentry** — Error monitoring

**Strengths:**
- Open standard — works across Claude Desktop, Code, and third-party tools
- Huge ecosystem of pre-built servers
- Claude uses tools naturally within conversation flow
- Composable — run multiple servers simultaneously

**Weaknesses:**
- Setup requires JSON configuration and sometimes API keys
- Local stdio servers need Node.js or Python installed
- Debugging MCP issues can be opaque (check server logs)
- Security: MCP servers have the permissions of the process running them

**When to use:** Whenever you want Claude to interact with external systems — databases, APIs, SaaS tools, local files, or custom internal tools.

> [Docs: MCP](https://docs.anthropic.com/en/docs/claude-code/mcp-servers) | [MCP Spec](https://modelcontextprotocol.io)

---

### Hooks

Hooks are **automated actions** that run at specific points in Claude's lifecycle — before a tool runs, after a tool runs, when a session starts, or when Claude finishes a task. They let you enforce rules, run formatters, validate outputs, or trigger external workflows.

**Lifecycle events:**

```
Session Start ──→ User Message ──→ PreToolUse ──→ [Tool Runs] ──→ PostToolUse ──→ ... ──→ Stop
     │                                  │                              │                    │
     ▼                                  ▼                              ▼                    ▼
  SessionStart                    Can BLOCK the              Can run formatters,       Stop hook
  hook fires                      tool call                  linters, validators       fires
```

| Event | When it Fires | Common Use |
|---|---|---|
| `SessionStart` | Session begins | Set up environment, check prerequisites |
| `PreToolUse` | Before any tool call | Block dangerous commands, validate inputs |
| `PostToolUse` | After any tool call | Run formatters, linters, update logs |
| `Stop` | Claude finishes responding | Final validation, notifications |
| `Notification` | Claude sends a notification | External alerting |

**Configuration** (`~/.claude/settings.json` or `.claude/settings.json`):
```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "npx prettier --write \"$CLAUDE_FILE_PATH\""
          }
        ]
      }
    ],
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          {
            "type": "command",
            "command": "echo '$CLAUDE_TOOL_INPUT' | grep -q 'rm -rf' && exit 2 || exit 0"
          }
        ]
      }
    ]
  }
}
```

**Hook types:**
- **`command`** — Runs a shell command. Exit code `0` = allow, `2` = block.
- **`prompt`** — Sends a prompt to Claude to make a decision.
- **`agent`** — Spawns a subagent with tool access.

**Matchers** filter which tools trigger the hook (e.g., `"Edit|Write"` only fires on file edits).

**When to use:**
- Auto-format code after every edit (Prettier, Black, gofmt)
- Block dangerous commands (prevent `rm -rf /`, force pushes)
- Run linters after file changes
- Send notifications when tasks complete

> [Docs: Hooks](https://docs.anthropic.com/en/docs/claude-code/hooks)

---

### Slash Commands

Slash commands are **quick-access shortcuts** you type in the Claude interface to trigger specific actions. They are now unified under the **Skills** system — every slash command is backed by a skill.

**Built-in commands:**

| Command | What it Does |
|---|---|
| `/help` | Show help and available commands |
| `/clear` | Clear conversation context |
| `/compact` | Compress conversation to save context |
| `/model` | Switch the active model |
| `/cost` | Show token usage and cost |
| `/permissions` | View and manage tool permissions |
| `/memory` | View or manage Claude's memory |
| `/status` | Show current session status |

**Custom slash commands** are created by writing skills (see [[#Skills]] above). Any skill you create becomes available as a slash command:

```
/commit          → Runs your commit skill
/review-pr       → Runs your PR review skill
/deploy          → Runs your deployment skill
```

**When to use:** Anytime you want quick access to a workflow without typing a full prompt. Slash commands are especially useful for actions you perform multiple times per day.

---

### Plugins

Plugins are **shareable bundles** that package multiple customizations together — skills, hooks, agents, MCP servers, and commands — into a single installable unit.

**Plugin structure:**
```
my-plugin/
├── plugin.json              ← Manifest (name, version, components)
├── skills/
│   └── my-skill/
│       └── SKILL.md
├── agents/
│   └── my-agent.md
├── hooks/
│   └── format-on-save.sh
└── .mcp.json                ← MCP servers bundled with the plugin
```

**plugin.json example:**
```json
{
  "name": "my-dev-toolkit",
  "version": "1.0.0",
  "description": "Development workflow automation",
  "skills": ["skills/my-skill"],
  "agents": ["agents/my-agent.md"],
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Write",
        "hooks": [{ "type": "command", "command": "hooks/format-on-save.sh" }]
      }
    ]
  }
}
```

**When to use:** When you want to share a curated set of customizations with your team or the community. Plugins are the distribution mechanism for Claude extensions.

---

### Custom Agents

Custom agents are **specialized autonomous sub-agents** that Claude can spawn to handle specific types of tasks. They're defined as markdown files with system prompts and tool restrictions.

**File location:** `.claude/agents/<name>.md`

**Example** (`.claude/agents/test-runner.md`):
```markdown
---
name: test-runner
description: Runs tests and reports results with coverage analysis
allowed-tools:
  - Bash
  - Read
  - Grep
model: sonnet
---

You are a test execution specialist. When invoked:

1. Identify the test framework in use (Jest, pytest, Go test, etc.)
2. Run the full test suite
3. If tests fail, analyze the failures and suggest fixes
4. Report coverage statistics
5. Flag any tests that are flaky or suspiciously slow
```

**Key features:**
- **Tool restrictions** — Limit what tools the agent can use
- **Model selection** — Use a cheaper model for simple agent tasks
- **Isolation** — Agents run in their own context, keeping the main conversation clean
- **Composability** — Skills and hooks can spawn agents

**When to use:** When you have a well-defined, repeatable task that benefits from a focused system prompt and limited tool access — test running, code review, documentation generation, security auditing.

---

### Keybindings

You can customize keyboard shortcuts in Claude Code by editing `~/.claude/keybindings.json`.

**Example:**
```json
[
  { "key": "ctrl+shift+r", "command": "skill:code-review" },
  { "key": "ctrl+shift+t", "command": "skill:run-tests" },
  { "key": "ctrl+enter", "command": "submit" }
]
```

---

### Settings

Global and project-level settings are configured in JSON files:

| File | Scope |
|---|---|
| `~/.claude/settings.json` | User-level (all projects) |
| `.claude/settings.json` | Project-level (shared) |
| `.claude/settings.local.json` | Project-level (personal, gitignored) |

**Common settings:**
```json
{
  "model": "claude-sonnet-4-6",
  "permissions": {
    "allow": ["Read", "Glob", "Grep"],
    "deny": ["Bash(rm *)"]
  },
  "env": {
    "GITHUB_TOKEN": "...",
    "NODE_ENV": "development"
  },
  "hooks": { ... }
}
```

---

### Memory

Claude Code has an **automatic memory system** that persists learnings across conversations. It stores memories as markdown files in `~/.claude/projects/<project>/memory/`.

**Memory types:**
- **User** — Your role, preferences, expertise level
- **Feedback** — Corrections and confirmed approaches
- **Project** — Ongoing work, goals, deadlines
- **Reference** — Pointers to external resources

Claude automatically saves and recalls memories to improve future interactions. You can also explicitly ask Claude to "remember" or "forget" something.

---

## Further Reading

- [Anthropic Documentation](https://docs.anthropic.com/)
- [Claude Code Docs](https://docs.anthropic.com/en/docs/claude-code)
- [Model Context Protocol](https://modelcontextprotocol.io)
- [Anthropic Cookbook (Examples)](https://github.com/anthropics/anthropic-cookbook)
- [Claude Code GitHub](https://github.com/anthropics/claude-code)
- [[ClaudeResources]] — Curated resource collection in this vault
