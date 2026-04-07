---
title: Claude Code - The Complete Guide
description: A comprehensive guide to Claude Code, Anthropic's agentic coding tool.
created: 2026-04-06
updated: 2026-04-06
topics:
  - Claude Code
  - Anthropic
  - AI Coding
  - Agentic AI
  - MCP
  - Automation
  - Prompt Engineering
  - Developer Tools
---

# Master Claude Code — The Complete Guide for Everyone
*A comprehensive reference covering everything you need to know about Claude Code — from first launch to advanced automation.*

---

> **What is Claude Code?**
> Claude Code is Anthropic's agentic coding tool that transforms Claude from a chat assistant into an **operating system layer** that runs across your entire workflow. Instead of just asking Claude for help and copy-pasting answers, Claude Code can directly read your files, run commands, manage Git, connect to external tools, and work autonomously on complex, hours-long tasks. Think of it as the difference between asking a colleague for advice vs. having a capable teammate who can actually execute.

---

## Table of Contents

1. [Why Claude Code Changes Everything](#1-why-claude-code-changes-everything)
2. [What Claude Code Can Do](#2-what-claude-code-can-do)
3. [The Claude Code Workflow](#3-the-claude-code-workflow)
4. [Getting Started](#4-getting-started)
5. [Connect Everything with MCP](#5-connect-everything-with-mcp)
6. [Essential Commands](#6-essential-commands)
7. [Skills and CLAUDE.md](#7-skills-and-claudemd)
8. [Prompting Techniques](#8-prompting-techniques)
9. [Resources and Further Learning](#9-resources-and-further-learning)

---

## 1. Why Claude Code Changes Everything

Before Claude Code, working with AI looked like this:

- You had a **chat window** — type a question, get an answer, copy-paste it yourself
- There were **upload limits** — you could only share a few files at a time
- **Sessions expired** — context was lost between conversations
- **You did everything** — Claude could advise, but you had to execute every step manually

**Claude Code removes all of those barriers:**

| Before (Chat-Only)         | After (Claude Code)              |
|---------------------------|----------------------------------|
| Chat window only          | Full system access               |
| Upload limits             | All files, any size              |
| Sessions expire           | Hours-long tasks                 |
| You do everything         | AI teammates that execute        |

> **What does "operating system layer" mean?**
> Traditional AI chat is like texting a smart friend — they can give advice, but you still have to do the work. Claude Code is more like hiring a capable employee who sits at your computer, can open any file, run any program, and carry out multi-step tasks from start to finish. It's the difference between *asking for help* and *having a capable teammate*.

---

## 2. What Claude Code Can Do

Claude Code has four core capabilities that make it fundamentally different from a chat interface:

### 2a. Full File System Access

Claude Code can **read, write, create, and organize any file** on your computer. There are no upload limits and no file-size restrictions.

**What this means in practice:**
- Process 10,000 files in minutes vs. hours of manual uploads
- Read entire codebases, not just snippets you paste in
- Create, rename, move, and delete files directly
- Work with any file type — code, documents, images, data files, etc.

### 2b. Tool and Command Execution

Claude Code can **run shell commands, execute scripts, manage Git, and install packages** — all through natural language instructions.

**What this means in practice:**
- Non-coders can run bash commands without learning syntax
- Developers can delegate routine terminal operations
- Claude handles package installation, builds, testing, and deployment commands
- Version control (Git) operations happen conversationally

### 2c. MCP Connections (200+ Tools)

MCP (Model Context Protocol) lets Claude Code **connect to GitHub, Notion, Slack, Jira, databases, APIs, and hundreds of other tools** — all through one standardized protocol.

**What this means in practice:**
- "One interface for your entire tool ecosystem"
- No switching between apps — Claude can read from Notion, update Jira, push to GitHub, and message Slack in a single workflow
- See [Section 5](#5-connect-everything-with-mcp) for full details

### 2d. Autonomous Multi-Agent Work

Claude Code supports **subagents that work in parallel**, background tasks, and checkpoints that let you rewind if something goes wrong.

**What this means in practice:**
- "Delegate like you have 5 junior employees"
- Multiple agents can research, code, and test simultaneously
- Background tasks run while you continue working
- Checkpoint system means you can undo mistakes easily

---

## 3. The Claude Code Workflow

Claude Code supports a full **end-to-end workflow** from research through execution. Here's how the four stages work:

```
┌──────────────────┐   ┌──────────────────┐   ┌──────────────────┐   ┌──────────────────┐
│ 1. ANALYZE &     │   │ 2. PLAN &        │   │ 3. CREATE &      │   │ 4. SCALE &       │
│    RESEARCH      │──▶│    DECIDE        │──▶│    EXECUTE       │──▶│    REPEAT        │
│                  │   │                  │   │                  │   │                  │
│ • Synthesize     │   │ • Draft PRDs     │   │ • Generate       │   │ • Set up         │
│   customer       │   │   from notes     │   │   presentations  │   │   recurring      │
│   feedback       │   │ • Create roadmap │   │ • Write code /   │   │   workflows      │
│ • Research       │   │   priorities     │   │   prototypes     │   │ • Connect tools  │
│   competitors    │   │ • Generate       │   │ • Create reports │   │   via MCP        │
│ • Extract        │   │   strategy       │   │   and docs       │   │ • Create         │
│   insights from  │   │   options        │   │ • Build          │   │   reusable       │
│   documents      │   │ • Build decision │   │   dashboards     │   │   skills         │
│ • Read and       │   │   frameworks     │   │                  │   │ • Schedule and   │
│   summarize      │   │                  │   │                  │   │   batch tasks    │
│   files          │   │                  │   │                  │   │                  │
└──────────────────┘   └──────────────────┘   └──────────────────┘   └──────────────────┘
```

### Real-World Example: Product Manager Workflow

Here's how a product manager might use all four stages in a single workflow:

```
PRD from              Jira tickets         Slack summary         Dashboard
meeting transcript ──▶ auto-created    ──▶ posted           ──▶ updated
```

1. Claude reads a meeting transcript and drafts a PRD (Product Requirements Document)
2. From that PRD, it creates Jira tickets automatically
3. It posts a summary to the team's Slack channel
4. It updates the project dashboard with the latest status

---

## 4. Getting Started

### Recommended Setup Path

The **best experience** is using Claude Code inside [Cursor](https://cursor.com) (an AI-focused code editor) or VS Code:

1. Download Cursor from [cursor.com](https://cursor.com) (or use VS Code)
2. Open your project folder in Cursor
3. Open the terminal inside Cursor (`View → Terminal`)
4. Type `claude` and press Enter
5. Authenticate via your browser when prompted

### Alternative: Direct Terminal

If you prefer working directly in the terminal:

**Mac / Linux:**
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

**Windows (PowerShell):**
```powershell
irm https://claude.ai/install.ps1 | iex
```

Then navigate to your project folder and type `claude`.

### Requirements Checklist

Before you begin, make sure you have:

- **Operating System:** macOS 13+, Ubuntu 20+, or Windows 10+ (with WSL or Git Bash)
- **Subscription:** Claude Pro ($20/mo), Max ($100-200/mo), or API credits
- **Optional:** A code editor like Cursor or VS Code for the best experience

> **What is WSL?**
> WSL (Windows Subsystem for Linux) lets you run a Linux environment directly on Windows. Claude Code was originally built for Unix-based systems, so WSL gives you the smoothest experience on Windows. Git Bash is a lighter alternative that works for basic usage.

---

## 5. Connect Everything with MCP

### What is MCP?

**MCP (Model Context Protocol)** is an open standard that connects Claude to your external tools. Think of it as **USB-C for AI** — one protocol, hundreds of connections.

Just as USB-C replaced a tangle of proprietary cables with one universal connector, MCP replaces custom API integrations with a single, standardized way for Claude to talk to any tool.

### Available Connections

MCP servers exist for tools across every category:

| Category           | Tools Available                                                |
|--------------------|----------------------------------------------------------------|
| **Developer Tools** | GitHub, Sentry, Linear, GitLab                                |
| **Productivity**    | Notion, Slack, Jira Product Discovery                         |
| **Data & Research** | Perplexity, PostgreSQL, Brave Search, Filesystem              |
| **Communication**   | Gmail, Typefully, Buffer, Discord                             |

### Quick Add Command

Adding a new MCP connection is a single command:

```bash
claude mcp add --transport http notion https://mcp.notion.com/mcp
```

This tells Claude Code to connect to Notion's MCP server. Once connected, Claude can read, search, and write to your Notion workspace directly.

> **How do I find MCP servers?**
> The community maintains a growing directory at [mcp.notion.com/mcp](https://mcp.notion.com/mcp) and through the [MCPso Collection](https://mcpso.com). Many popular tools (GitHub, Slack, Notion, etc.) have official MCP servers. You can also browse available servers by running `/mcp` inside Claude Code.

---

## 6. Essential Commands

### Slash Commands (type `/` in Claude Code)

Slash commands are shortcuts you type directly into the Claude Code prompt. They trigger specific actions instantly instead of requiring you to type out a full instruction.

| Command     | What It Does                                         |
|-------------|------------------------------------------------------|
| `/help`     | Show all available commands                          |
| `/clear`    | Reset context (use between tasks!)                   |
| `/compact`  | Compress conversation to save tokens                 |
| `/model`    | Switch between Opus, Sonnet, and Haiku models        |
| `/mcp`      | Check MCP server connections                         |
| `/doctor`   | Diagnose installation issues                         |
| `/config`   | Open settings                                        |

> **Why use `/clear` between tasks?**
> Claude Code maintains context from your entire conversation. If you've been working on Task A and switch to Task B, all of Task A's context is still loaded — this wastes tokens (which cost money on usage-based plans) and can confuse Claude. Use `/clear` to start fresh between unrelated tasks.

> **What are Opus, Sonnet, and Haiku?**
> These are different Claude models with different trade-offs:
> - **Opus** — Most capable, best for complex reasoning and large tasks (slowest, most expensive)
> - **Sonnet** — Balanced performance and speed (good default for most work)
> - **Haiku** — Fastest and cheapest, best for simple tasks and quick lookups

### File References (type `@` to reference)

The `@` symbol lets you point Claude at specific files or folders without manually describing their location:

| Syntax      | Example           | What It Does                          |
|-------------|-------------------|---------------------------------------|
| `@filename` | `@report.csv`     | Reference a specific file             |
| `@folder/`  | `@data/`          | Reference an entire folder            |
| Tab key     | —                 | Autocomplete file and folder paths    |

### Keyboard Shortcuts

| Action               | Keys                            |
|----------------------|---------------------------------|
| Cancel / Stop        | `Esc`                           |
| Rewind checkpoint    | `Esc` twice                     |
| Paste image          | `Ctrl+V` (not Cmd+V on Mac)    |
| Run shell directly   | Start with `!`                  |

> **What is "rewind checkpoint"?**
> Claude Code automatically creates checkpoints as it works. If Claude makes a change you don't like, pressing `Esc` twice rewinds to the previous checkpoint — like an undo button for AI actions. This is one of the most important safety features to know about.

---

## 7. Skills and CLAUDE.md

### Claude Skills (Reusable Automations)

**Skills** are task-specific instruction packages that Claude auto-loads when relevant. Think of them as "playbooks" that teach Claude how to handle specific types of work consistently.

**Folder Structure:**
Skills live in `~/.claude/skills/` (your home directory). Each skill is a folder containing instructions:

```
~/.claude/skills/
├── linkedin-writer/
│   └── skill.md
├── prd-generator/
│   └── skill.md
└── data-cleaner/
    └── skill.md
```

**Built-in Skills (common document types):**
- **docx** — Word documents
- **xlsx** — Spreadsheets
- **pptx** — Presentations
- **pdf** — PDF processing

> **How are Skills different from just giving Claude instructions?**
> You *could* type detailed instructions every time, but Skills save you from repeating yourself. Once you create a skill for "write LinkedIn posts in my voice" or "generate PRDs in our company format," Claude loads those instructions automatically whenever the task matches. Skills are reusable across all your conversations.

### CLAUDE.md (Project Memory)

**CLAUDE.md** is a markdown file that gives Claude permanent context about your project. Place it in your project's root directory, and Claude Code reads it automatically every time you start a session in that folder.

**Example CLAUDE.md:**
```markdown
# Project: Marketing Dashboard

## Key Commands
- npm run build
- npm run test

## Style Guide
- Use TypeScript
- Follow existing patterns

## Important Context
- Main data source: data/analytics.csv
- Target: Series C investors
```

**Where to place CLAUDE.md files:**
- **Global:** `~/.claude/CLAUDE.md` — applies to all projects (your personal preferences)
- **Project:** `./CLAUDE.md` — applies to a specific project (team conventions, build commands, architecture notes)

> **Why bother with CLAUDE.md?**
> Without it, you'd need to re-explain your project setup, coding conventions, and preferences every time you start a new conversation. CLAUDE.md is like onboarding documentation for your AI teammate — write it once, and Claude always knows how your project works.

---

## 8. Prompting Techniques

How you phrase your requests to Claude Code significantly impacts the quality of results. Here are the key techniques:

### Core Techniques

| Technique          | When to Use                                      | Example                                                              |
|--------------------|--------------------------------------------------|----------------------------------------------------------------------|
| **Be Specific**    | Always — vague prompts get vague results         | "Clean this CSV — remove rows where column B is empty, deduplicate on email" |
| **Give Examples**  | When output format matters                       | "Show 1-2 examples of what you want"                                 |
| **Chain Steps**    | Complex tasks with multiple stages               | "First analyze, then summarize, then create action items"            |
| **Set Constraints**| Quality control                                  | "Max 500 words" or "Only use data from 2024"                        |
| **Assign Roles**   | When expertise matters                           | "Act as a data analyst reviewing this dataset"                       |
| **Use /clear Often** | Between unrelated tasks                        | Resets context to prevent confusion and save tokens                  |

### The Pro Pattern: Checkpoint + Iterate

This is the most effective workflow pattern for getting great results from Claude Code:

1. **Ask Claude to make a plan first** — "Before coding, outline your approach"
2. **Review the plan** — make sure you agree with the direction before Claude executes
3. **Let it create checkpoints** — Claude saves state as it works
4. **Rewind (`Esc` twice) if something goes wrong** — roll back to the last good state
5. **Iterate with specific feedback** — "The header is good, but change the chart to a bar graph"

> **Why plan first?**
> It's much cheaper (in time and tokens) to correct a plan than to undo completed work. A 30-second plan review can save you 10 minutes of rewinding and re-doing. This is especially important for large tasks like refactoring a codebase or generating a complex document.

---

## 9. Resources and Further Learning

### Official Documentation

| Resource                     | Link                                                          |
|------------------------------|---------------------------------------------------------------|
| Setup Guide                  | [code.claude.com/docs/en/setup](https://code.claude.com/docs/en/setup) |
| MCP Reference                | [code.claude.com/docs/en/mcp](https://code.claude.com/docs/en/mcp)     |
| Best Practices               | [anthropic.com/engineering/claude-code-best-practices](https://anthropic.com/engineering/claude-code-best-practices) |

### Community Guides and Tutorials

| Resource                       | Description                                         |
|--------------------------------|-----------------------------------------------------|
| Claude Code Pro Guide          | In-depth power-user walkthrough                     |
| How to Use Claude Code Like a Pro | Advanced tips and workflows                      |
| Skills Deep Dive               | Detailed guide to building and using Skills         |
| Claude Skills Tutorial         | Step-by-step skill creation                         |
| Downloadable Skills            | Pre-built skills you can install immediately        |
| Steal 6 of My Claude Skills    | Curated community skill collection                  |
| AI Agents Guide                | Understanding and building AI agents                |
| AI Agents for PMs              | Product manager-specific agent workflows            |
| Prompting Guide                | Comprehensive prompt engineering reference          |
| Prompt Engineering             | Advanced techniques for better AI outputs           |
| ChatGPT for PMs                | PM-focused techniques (applicable to Claude too)    |

### Pricing Quick Reference

| Plan      | Monthly | Best For                                  |
|-----------|---------|-------------------------------------------|
| **Pro**   | $20     | Light usage, short tasks                  |
| **Max 5x**| $100   | Daily use, larger projects                |
| **Max 20x**| $200  | Power users, heavy automation             |
| **API**   | Pay-per-use | CI/CD, enterprise pipelines          |

> **Which plan should I choose?**
> - If you're just getting started or use Claude Code occasionally: **Pro** is fine
> - If you use Claude Code daily for real work: **Max 5x** gives you room to breathe
> - If you're running autonomous agents, multi-hour tasks, or enterprise workflows: **Max 20x**
> - If you're integrating Claude Code into automated pipelines (CI/CD, scheduled tasks): **API** billing gives you the most flexibility

---

*Original cheat sheet: "Master Claude Code — The Complete Guide for Everyone" v1.0, January 2026, by Aakash Gupta. This expanded guide adds explanations and context for users new to Claude Code and the broader Claude ecosystem.*

---
#claude-code #anthropic #ai-coding #agentic-ai #mcp #automation #prompt-engineering #developer-tools 