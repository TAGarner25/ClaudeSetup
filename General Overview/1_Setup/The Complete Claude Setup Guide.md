# The Complete Claude Setup Guide
*A comprehensive guide to understanding, installing, and maximizing Claude — written for beginners and power users alike.*

---

> **What is Claude?**
> Claude is an AI assistant made by [Anthropic](https://www.anthropic.com). Think of it like a very capable coworker who can read, write, research, analyze data, write code, build documents, and automate tasks — and it's available 24/7. Claude comes in several different "surfaces" (ways to access it), each designed for a different kind of work.

---

## Table of Contents

1. [The Claude Ecosystem — Five Ways to Access Claude](#1-the-claude-ecosystem)
2. [When to Use Which Tool](#2-when-to-use-which-tool)
3. [Skills — Teaching Claude New Tricks](#3-skills)
4. [Plugins — Bundles of Superpowers](#4-plugins)
5. [Connectors — Linking Claude to Your Other Tools](#5-connectors)
6. [My Personal Setup (Trevor's Configuration)](#6-my-personal-setup)
7. [Getting Started Checklist](#7-getting-started-checklist)
8. [Official Resources](#8-official-resources)

---

## 1. The Claude Ecosystem

There are **five main ways** to use Claude. They all share the same underlying AI, but they're built for different situations.

```
┌─────────────────────────────────────────────────────────────────┐
│                     THE CLAUDE ECOSYSTEM                        │
│                                                                 │
│  ┌─────────────┐  ┌────────────┐  ┌─────────────────────────┐  │
│  │  Claude.ai  │  │  Desktop   │  │        Cowork           │  │
│  │  (Web Chat) │  │    Chat    │  │  (Autonomous Agent)     │  │
│  │             │  │            │  │                         │  │
│  │ Browser-    │  │ Offline-   │  │ Works independently,    │  │
│  │ based,      │  │ capable,   │  │ reads/writes files,     │  │
│  │ any device  │  │ native app │  │ runs scheduled tasks    │  │
│  └─────────────┘  └────────────┘  └─────────────────────────┘  │
│                                                                 │
│  ┌─────────────────────────┐  ┌─────────────────────────────┐  │
│  │   Claude Code Desktop   │  │    Claude Code CLI          │  │
│  │   (Visual Dev Tool)     │  │    (Terminal)               │  │
│  │                         │  │                             │  │
│  │ GUI for coding with     │  │ For developers: full        │  │
│  │ diffs, Ask/Code/Plan    │  │ agentic coding in the       │  │
│  │ modes, visual review    │  │ command line                │  │
│  └─────────────────────────┘  └─────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```

---

### 1a. Claude.ai — Web Chat
**→ [claude.ai](https://claude.ai)**

This is the most familiar way to use Claude — a chat window in your browser, similar to ChatGPT. You type a message, Claude responds. It's available on any device with a web browser, no installation needed.

**What makes it special:**
- Supports **Projects** — persistent conversations where you can upload documents, images, and files that Claude remembers across sessions. Great for ongoing work like "my Q2 marketing campaign" or "my investment research."
- **Artifacts** — Claude can produce interactive outputs like code playgrounds, visual charts, and mini web apps right inside the chat.
- **Voice input** — you can speak your questions instead of typing.
- **Web search** — Claude can look things up in real time.
- **Extended Thinking** — for complex problems, Claude can reason step-by-step before answering.

**Best for:** Quick questions, brainstorming, drafting documents, iterative back-and-forth conversations, anything where you want to stay in the browser.

📖 *Official docs: [Intro to Claude](https://docs.claude.com/en/docs/intro)*

---

### 1b. Claude Desktop — Desktop Chat
**→ [Download from anthropic.com](https://www.anthropic.com/download)**

This is the same chat experience as the web version, but installed as an app on your computer (Windows or Mac). The biggest advantage is that it can connect to **MCP Connectors** (explained in Section 5) and supports **Cowork mode** — neither of which is available in the browser.

**What makes it special:**
- Everything from the web version, plus...
- Runs natively on your computer (slightly faster, works offline for some tasks)
- The gateway to **Cowork** and **Claude Code** (Desktop) features
- Supports **Connectors** that link Claude to your other apps

**Best for:** Anyone who uses Claude regularly and wants more power than the browser version offers. This is the recommended starting point for most users.

---

### 1c. Cowork — Autonomous Background Agent
**→ Available inside the Claude Desktop app**

Cowork is the most powerful non-coding version of Claude. Instead of having a back-and-forth conversation, you give Claude a goal and a folder on your computer, and it works independently to complete the task — reading files, creating documents, running sub-tasks, and saving results back to your computer.

Think of it like this: **Chat is like texting a smart colleague. Cowork is like handing a project to that colleague and going to lunch.**

**What makes it special:**
- Claude can **read and write files** on your computer directly
- It can spin up **multiple sub-agents** to work on parts of a task in parallel (like having a whole team)
- Supports **scheduled tasks** — Claude can run a task automatically every morning, every week, etc.
- Supports **Plugins** (covered in Section 4) for industry-specific workflows
- Has **browser automation** — Claude can control Chrome on your behalf

**Best for:** Long, multi-step tasks like "Analyze all the PDFs in my Downloads folder and create a summary report," "Organize my notes into categories," "Build me a financial model from this spreadsheet," or recurring automations.

> ⚠️ **Important note:** Cowork runs in an isolated environment for safety — it can only access folders you explicitly give it permission to access.

📖 *Official docs: [Get Started with Cowork](https://support.claude.com/en/articles/13345190-get-started-with-cowork)*

---

### 1d. Claude Code Desktop — Visual Development Tool
**→ Available inside the Claude Desktop app (for developers)**

Claude Code Desktop is a graphical interface for software developers. It shows you exactly what changes Claude is proposing to make to your code, with visual "diffs" (side-by-side comparisons of old vs. new code) that you can accept or reject.

**Three modes:**
- **Ask mode** — Claude explains and proposes, but doesn't make any changes without your approval
- **Code mode** — Claude makes file changes automatically but asks before running any terminal commands
- **Plan mode** — Claude outlines its approach without touching anything first

**Best for:** Developers who want Claude to write, review, debug, or refactor code with visual oversight.

> 💡 If you're not a developer, you can safely skip this section — Cowork handles file tasks and automation for non-coders much more naturally.

---

### 1e. Claude Code CLI — Command Line Interface
**→ [Claude Code Docs](https://docs.claude.com/en/docs/claude-code/overview)**

This is the original, terminal-based version of Claude Code, designed for experienced developers who prefer working in a command line. It's extremely powerful for coding workflows — you can point it at an entire codebase and ask it to make changes, write tests, debug issues, and commit to Git.

**Best for:** Software engineers and developers who live in the terminal.

> 💡 Again — if you're not a developer, this one isn't for you. The Cowork surface covers everything a non-developer needs.

---

## 2. When to Use Which Tool

Here's a quick decision guide:

| Your Situation | Best Tool |
|---|---|
| Quick question, one-off task | **Web Chat (claude.ai)** |
| Ongoing project with documents | **Web Chat with Projects** |
| You want more power, connectors | **Desktop Chat** |
| Multi-step task, file processing, automation | **Cowork** |
| Recurring task (weekly report, daily summary) | **Cowork (Scheduled Tasks)** |
| Writing or debugging code (with visual review) | **Claude Code Desktop** |
| Professional developer, terminal-native | **Claude Code CLI** |

### Real-World Use Case Examples

```
📝 WRITING & RESEARCH
────────────────────────────────────────────────────────────────
Web Chat    → "Write a cover letter for this job posting"
Web Chat    → "Explain the difference between ETFs and mutual funds"
Cowork      → "Read all 12 PDFs in my Research folder and
               create a consolidated summary document"

📊 FINANCE & ANALYSIS
────────────────────────────────────────────────────────────────
Web Chat    → "What are the key metrics to evaluate before
               buying a stock?"
Cowork      → "Build a DCF valuation model for Apple using
               their latest 10-K filing"
Cowork      → "Every Monday morning, summarize last week's
               market news from my saved articles"

💼 BUSINESS WORK
────────────────────────────────────────────────────────────────
Web Chat    → "Brainstorm 10 marketing campaign ideas"
Web Chat    → "Review this contract and flag any concerning clauses"
Cowork      → "Go through my Inbox and create a summary of all
               emails from this week that need a response"

🖥️ CODING (DEVELOPERS ONLY)
────────────────────────────────────────────────────────────────
Code Desktop → "Review my codebase and fix any bugs you find"
Code CLI     → "Add user authentication to my web app"
```

---

## 3. Skills

### What is a Skill?

A **Skill** is a set of detailed instructions you give Claude to help it perform a specific type of task extremely well. Think of it as handing Claude a cheat sheet before it starts working.

Without a Skill, if you ask Claude to "make me a PowerPoint," it will do its best — but it might produce something generic. With a **PowerPoint Skill** loaded, Claude knows exactly what Python libraries to use, how to format slides, how to handle images, and dozens of other best practices baked in from experience.

> 🎓 **Analogy:** Imagine hiring a great general contractor. They can build anything — but if you hire one who specializes in custom kitchens, they're going to do a much better job on your kitchen remodel because they already know all the tricks. Skills are the specialization.

### How Skills Work

Skills are stored as folders containing a `SKILL.md` file — a plain text file with instructions. When you trigger a skill, Claude reads those instructions before it starts working, ensuring professional-quality results.

**In Cowork (Desktop App):** Skills are triggered automatically when Claude detects your request matches a skill's purpose. You can also call a skill by name (e.g., "use the pptx skill to make me a presentation").

**In Claude Code (CLI):** Skills work the same way — they're folders of instructions that Claude reads before starting a task.

### Where Skills Are Available

| Surface | Supports Skills? |
|---|---|
| Web Chat (claude.ai) | ❌ No |
| Desktop Chat | ✅ Yes (via Cowork) |
| Cowork | ✅ Yes — primary home |
| Claude Code Desktop | ✅ Yes |
| Claude Code CLI | ✅ Yes |

### Built-In Skills (Come Pre-Installed in Cowork)

These skills come built into Cowork automatically:

| Skill | What It Does |
|---|---|
| **docx** | Creates professional Microsoft Word documents |
| **pptx** | Builds PowerPoint presentations |
| **xlsx** | Creates Excel spreadsheets with formulas |
| **pdf** | Processes, creates, and extracts from PDFs |
| **canvas-design** | Creates visual artwork and design files |
| **mcp-builder** | Builds MCP connector integrations |
| **schedule** | Creates scheduled/recurring tasks |
| **skill-creator** | Creates new skills from scratch |
| **theme-factory** | Applies visual themes to documents and presentations |
| **web-artifacts-builder** | Builds complex interactive web pages |
| **doc-coauthoring** | Guides you through co-writing documentation |
| **brand-guidelines** | Applies Anthropic's official brand styling |

### How to Install Additional Skills

Skills can be installed into Cowork by:

1. **From a `.skill` file** — If someone shares a skill file (it ends in `.skill`), you can drag it into Cowork's sidebar or share it via the chat interface. Cowork will display a "Copy to your skills" button.

2. **From Plugins** — Installing a Plugin (see next section) automatically adds its skills to Cowork. This is the most common way to expand your skill library.

3. **Creating your own** — You can ask Claude to create a new skill using the built-in `skill-creator` skill. Just say: *"Create a skill that helps me write professional email templates."*

### How to Create Your Own Skill

You don't need to be technical to create a skill. Just describe what you want to Claude:

> *"Create a skill that helps me draft weekly progress reports for my team. Reports should always include: a summary of what was completed, blockers, and next steps. Use a professional but friendly tone."*

Claude (using the `skill-creator` skill) will generate the skill file for you. From then on, whenever you ask for a weekly progress report, Claude will follow those exact instructions.

📖 *More about skills: [Claude Code Skills overview](https://docs.claude.com/en/docs/claude-code/overview)*

---

## 4. Plugins

### What is a Plugin?

A **Plugin** is a bundle of multiple related Skills packaged together, often with connectors to external tools. If a Skill is a single cheat sheet, a Plugin is an entire playbook.

> 🎓 **Analogy:** Think of Skills as individual apps on your phone. Plugins are like installing a full productivity suite (Microsoft Office) that gives you Word, Excel, PowerPoint, and Outlook all at once — plus they're all designed to work together.

### What's Inside a Plugin

A plugin can contain:
- Multiple **Skills** organized around a theme (e.g., all finance skills)
- **Slash commands** — shortcuts you can type to trigger workflows instantly
- **MCP Connectors** — connections to external services and data sources
- **Agents** — specialized sub-agents that can tackle specific sub-tasks

### Plugin Marketplaces

Plugins are organized in **Marketplaces** — curated collections of plugins grouped by theme. In Cowork, you can browse available marketplaces and install plugins directly.

**Available Marketplaces include:**
- **Knowledge Work Plugins** — productivity, sales, marketing, engineering, design, operations, product management
- **Financial Services Plugins** — financial analysis, equity research, investment banking, private equity, wealth management

### How to Install Plugins

**In Cowork:**
1. Open the Cowork session
2. Look for the **plugin marketplace** icon in the sidebar
3. Browse available plugins and click **Install**
4. The plugin's skills become immediately available

Once installed, Claude will automatically suggest the right skill when your request matches it — you don't need to manually invoke them.

### How to Create Your Own Plugin

Creating a plugin is more involved than creating a single skill, but Cowork has a built-in `cowork-plugin-management:create-cowork-plugin` skill to guide you through it step by step. Just say:

> *"Help me create a plugin for my HR department that handles onboarding checklists, interview feedback forms, and job description drafting."*

📖 *Official plugin docs: [Create plugins](https://code.claude.com/docs/en/plugins)* | *[Plugin examples on GitHub](https://github.com/anthropics/claude-plugins-official)*

---

## 5. Connectors

### What is a Connector?

A **Connector** (also called an **MCP Connector**) links Claude to your real-world tools and data. Without connectors, Claude only knows what you tell it in the chat. With connectors, Claude can actually *look things up* in your Google Drive, check your calendar, pull data from GitHub, and more.

> 🎓 **Analogy:** Without connectors, Claude is like a brilliant consultant who only knows what you've told them in the meeting. With connectors, it's like that consultant has read-only access to your company's entire database and can look things up in real time.

### MCP — The Technology Behind Connectors

Connectors are built on the **Model Context Protocol (MCP)** — an open standard developed by Anthropic. MCP is what allows Claude to communicate with external apps in a secure, standardized way. You don't need to understand the technical details to use connectors — just think of MCP as the "language" all connectors speak.

### Types of Connectors

| Type | Description | Example |
|---|---|---|
| **Official Directory** | Vetted by Anthropic, one-click install | Google Drive, GitHub, Figma |
| **Custom Remote** | You add a URL to a connector you or someone else built | Internal company tools |
| **Local (Desktop only)** | Runs on your computer, connects to local apps | Obsidian, filesystem access |

### Where Connectors Are Available

| Surface | Supports Connectors? |
|---|---|
| Web Chat (claude.ai) | ✅ Yes (Claude.ai Settings → Connectors) |
| Desktop Chat / Cowork | ✅ Yes (Claude Desktop Settings) |
| Claude Code | ✅ Yes (via config file) |

### How to Install a Connector (Web / Desktop)

**For Official Connectors:**
1. Go to **[claude.ai/settings/connectors](https://claude.ai/settings/connectors)** (or in the Desktop app: Settings → Connectors)
2. Click **"Browse connectors"**
3. Find the connector you want (e.g., Google Drive)
4. Click **Connect** and follow the authentication prompts
5. The connector is now active — Claude can use it in conversations

**For Custom Connectors:**
1. Same settings page → click **"Add custom connector"**
2. Enter a name and the MCP server URL provided by the tool/service
3. Click **Add**

> 🔒 **Security tip:** Stick to the official Anthropic connector directory when possible. These have been vetted for safety. Third-party connectors should only be installed if you trust the developer.

📖 *Official connector docs: [Use connectors to extend Claude's capabilities](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities)*

### How to Build a Custom Connector

Building a connector requires some technical ability — you're essentially building a small server that Claude can talk to. However, Cowork's built-in `mcp-builder` skill can walk you through it:

> *"Help me build an MCP connector that connects Claude to my company's internal project tracking tool."*

📖 *Building connectors: [Building custom connectors via remote MCP](https://support.claude.com/en/articles/11503834-building-custom-connectors-via-remote-mcp-servers)*

---

## 6. My Personal Setup

*This section documents the current configuration of Trevor's Claude setup — everything that's been installed beyond the defaults. Use this as a reference model for building your own setup.*

---

### 6a. The Knowledge Management System

A key part of making Claude truly useful over time is giving it **persistent memory** — notes, references, and context that carry across conversations. This setup uses **Obsidian** (a note-taking app) as the backbone.

**How it works:**
1. Cowork has access to the Notes folder on the computer
2. Claude can read and write notes in Obsidian format (Markdown files with `[[links]]` between notes)
3. A master overview file (`CLAUDE READ ME.md`) acts as a table of contents for Claude — so it always knows where things are

**The folder structure:**
```
Notes/
├── Claude/
│   ├── CLAUDE READ ME.md          ← Master index Claude reads first
│   ├── Claude Setup.md            ← Overview of tools and connectors
│   ├── Skills/
│   │   └── Skill Files/           ← Reference docs for each skill
│   │       ├── 01_Document_Creation/
│   │       ├── 02_Sales/
│   │       ├── 03_Product_Management/
│   │       ├── 07_Finance_Accounting/
│   │       ├── 08_Data_Analytics/
│   │       ├── 13_Equity_Research/
│   │       ├── 14_Financial_Analysis/
│   │       ├── 15_Investment_Banking/
│   │       ├── 16_Private_Equity/
│   │       └── 17_Wealth_Management/
│   └── Notes/
│       └── FINANCE_PROMPTS_EXPLAINED.md
```

> 💡 **Why this matters:** Without a system like this, every conversation with Claude starts from scratch. With a well-organized notes folder that Claude can access, it builds context over time — almost like a coworker who gets smarter about your work the longer they work with you.

---

### 6b. Built-in Cowork Skills (Pre-installed)

These skills come with Cowork automatically and require no setup:

| Skill | Category | What It Produces |
|---|---|---|
| `docx` | Documents | Professional Word documents (.docx) |
| `pptx` | Presentations | PowerPoint slide decks (.pptx) |
| `xlsx` | Spreadsheets | Excel workbooks with formulas (.xlsx) |
| `pdf` | Documents | PDFs — create, edit, extract |
| `canvas-design` | Design | Visual art and design files (.png, .pdf) |
| `brand-guidelines` | Design | Anthropic brand-styled documents |
| `theme-factory` | Design | Apply visual themes to any artifact |
| `doc-coauthoring` | Writing | Structured co-writing workflow |
| `schedule` | Automation | Create scheduled recurring tasks |
| `skill-creator` | Meta | Create new skills from scratch |
| `mcp-builder` | Technical | Build new MCP connectors |
| `web-artifacts-builder` | Technical | Build complex web UIs and apps |

---

### 6c. Installed Plugins (from Marketplaces)

Two plugin marketplaces are installed: **Knowledge Work** and **Financial Services**. Here's the full breakdown:

#### 🏢 Knowledge Work Plugins

| Plugin | Skills Included |
|---|---|
| **Cowork Plugin Management** | Plugin Customizer, Plugin Creator |
| **Finance** | Journal Entries, Variance Analysis, Reconciliation, Financial Statements, Close Management, Audit Support |
| **Data** | SQL Queries, Data Exploration, Data Validation, Data Visualization, Statistical Analysis, Interactive Dashboard Builder, Data Context Extractor |
| **Marketing** | Content Creation, Campaign Planning, Competitive Analysis, Brand Voice, Performance Analytics |
| **Productivity** | Memory Management, Task Management |
| **Engineering** | Code Review, Documentation, Incident Response, System Design, Tech Debt, Testing Strategy |
| **Design** | Design Critique, Accessibility Review, Design Handoff, Design System Management, UX Writing, User Research |
| **Operations** | Process Documentation, Process Optimization, Risk Assessment, Runbook, Change Request, Compliance Tracking, Capacity Planning, Status Report, Vendor Review |
| **Product Management** | Feature Spec / PRD Writing, User Research Synthesis, Stakeholder Updates, Sprint Planning, Roadmap Updates, Metrics Review, Competitive Brief |
| **Sales** | Account Research, Call Prep, Call Summary, Draft Outreach, Competitive Intelligence, Daily Briefing, Pipeline Review, Forecast, Create Sales Asset |
| **Legal** | Contract Review, NDA Triage, Compliance Check, Risk Assessment, Meeting Briefing, Legal Response, Signature Request, Vendor Check |
| **Brand Voice** | Brand Voice Enforcement, Guideline Generation, Brand Discovery |

#### 📈 Financial Services Plugins

| Plugin | Skills Included |
|---|---|
| **Financial Analysis** | 3-Statement Model, LBO Model, DCF Model, Comps Analysis, Competitive Analysis, Deck Refresh, Deck QC, Data Cleaning, Spreadsheet Audit, PPT Templates |
| **Equity Research** | Initiating Coverage, Earnings Analysis, Earnings Preview, Morning Note, Model Update, Thesis Tracker, Sector Overview, Idea Generation, Catalyst Calendar |
| **Investment Banking** | CIM Drafter, Pitch Deck Populator, Strip Profile, Teaser, Process Letter, Buyer List, Deal Tracker, Merger Model, Financial Datapack |
| **Private Equity** | Deal Sourcing, Deal Screening, Due Diligence Checklist, DD Meeting Prep, IC Memo, Portfolio Monitoring, Returns Analysis, Value Creation Plan, Unit Economics, AI Readiness Scan |
| **Wealth Management** | Client Report, Client Review, Financial Plan, Investment Proposal, Portfolio Rebalancing, Tax-Loss Harvesting |
| **S&P Global** | Company Tear Sheet, Earnings Preview, Funding Digest Slide |
| **LSEG** | Equity Research Snapshot, Fixed Income Portfolio Review, Bond RV Analysis, Bond Futures Basis, FX Carry Trade, Macro/Rates Monitor, Swap Curve Strategy, Option Vol Analysis |

---

### 6d. Connectors

Connectors fall into two categories: **official** (vetted by Anthropic) and **unofficial** (open-source, trusted by the developer).

#### ✅ Official Connectors (via claude.ai/settings/connectors)

| Connector | Purpose |
|---|---|
| **Canva** | Design software — Claude can pull and reference Canva projects |
| **Figma** | Design software — Claude can read Figma designs and specs |
| **GitHub** | Code repositories — Claude can read code, issues, and PRs |
| **Google Calendar** | Calendar access — Claude can read and reference calendar events |
| **Google Drive** | File access — Claude can read documents, spreadsheets, and slides |
| **Linear** | Task/project management — Claude can reference tasks and sprints |
| **Mermaid Charts** | Diagram creation — Claude can produce rendered diagrams |
| **Microsoft Docs** | Official Microsoft product documentation |
| **PDF Viewer** | Inline PDF rendering in conversations |
| **Three.js 3D Viewer** | 3D web animation previews (for web development) |
| **Claude in Chrome** | Browser extension — Claude can interact with websites you're visiting |
| **Context7** | Up-to-date documentation for software libraries |

#### 🔧 Unofficial / Community Connectors

These are open-source connectors maintained by the community. They require slightly more setup and trust — only install if you know and trust the source.

| Connector | Purpose | Notes |
|---|---|---|
| **Desktop Commander** | Control your desktop | Less needed now that Cowork handles most file tasks |
| **Filesystem** | Direct local file access | Largely replaced by Cowork |
| **Memory** | Cross-conversation memory | Now replaced by Anthropic's built-in memory feature |
| **Obsidian** | Connect Claude to your Obsidian notes | Still very useful for note-based workflows |
| **Sequential Thinking** | Forces Claude to reason step-by-step | Now rebuilt as a Skill (more efficient) |
| **Windows MCP** | Interact with Windows system settings | Less needed thanks to Cowork and Claude Code |

> 💡 **Note on community connectors:** Several of these (Desktop Commander, Filesystem, Memory) were workarounds before Cowork existed. Cowork now handles most of what they did natively. You may not need to install them at all.

---

### 6e. Memory & Preferences

Claude's built-in **Memory** feature (found in Claude Desktop → Settings → Memory) is enabled. This allows Claude to remember facts about you across all conversations — things like your name, your preferences, how you like responses formatted, your areas of expertise, etc.

**Example memories stored:**
- Communication style preferences (no fluff, use confidence levels)
- Note-taking and file organization conventions
- Areas of professional focus (finance, investing, etc.)
- Knowledge graph update instructions

> 💡 You can view and manage your memories anytime in Settings → Memory. You can delete specific memories or clear all of them.

---

### 6f. The Prompt Library

A curated library of **20 finance-focused prompts** is maintained in the Notes folder, modeled after institutional investment approaches:

- Goldman Sachs–style stock screener
- Morgan Stanley–style DCF valuation
- Bridgewater–style risk analysis
- JPMorgan–style earnings breakdown
- BlackRock–style portfolio construction
- ...and 15 more

These are stored as text files in Obsidian and referenced when needed. This is a great practice — keeping a personal prompt library means you don't have to re-invent the wheel every time you start a new task.

---

## 7. Getting Started Checklist

Here's a step-by-step path for someone setting up Claude from scratch. Start at the beginning and work your way down as you get more comfortable.

### 🟢 Level 1 — Start Here

- [ ] Create an account at **[claude.ai](https://claude.ai)**
- [ ] Try a few conversations to get comfortable
- [ ] Upgrade to **Pro or Max** plan for full access to the best models and features
- [ ] Create your first **Project** — upload a document relevant to your work and start a conversation with it

### 🟡 Level 2 — Get More Power

- [ ] Download the **[Claude Desktop app](https://www.anthropic.com/download)** (Windows or Mac)
- [ ] Enable **Memory** in Settings → Memory — teach Claude about you and your preferences
- [ ] Install 2–3 **official Connectors** that match your tools (e.g., Google Drive, GitHub, Notion)
- [ ] Try **Cowork** — give it a folder on your computer and a real task

### 🔵 Level 3 — Power User

- [ ] Browse and install **Plugins** that match your industry or role
- [ ] Create a **Skill** for a task you repeat often
- [ ] Set up a **Scheduled Task** in Cowork for a recurring workflow
- [ ] Build a **knowledge folder** — a directory Claude can access with notes, templates, and reference files
- [ ] Start a **Prompt Library** — save your best prompts as text files for reuse

### 🟣 Level 4 — Advanced

- [ ] Build a custom **MCP Connector** for a tool that doesn't have one yet
- [ ] Create a **Plugin** bundling your custom skills and share it with your team
- [ ] Set up multiple scheduled tasks to automate your recurring workflows
- [ ] Use Claude Code (Desktop or CLI) if you're writing software

---

## 8. Official Resources

Here are the key official links you'll want to bookmark:

| Resource | Link |
|---|---|
| Claude web app | [claude.ai](https://claude.ai) |
| Download Claude Desktop | [anthropic.com/download](https://www.anthropic.com/download) |
| Official documentation hub | [docs.claude.com](https://docs.claude.com) |
| Claude Code overview | [Claude Code Docs](https://docs.claude.com/en/docs/claude-code/overview) |
| Connectors directory | [claude.ai/settings/connectors](https://claude.ai/settings/connectors) |
| Connectors help article | [Use connectors](https://support.claude.com/en/articles/11176164-use-connectors-to-extend-claude-s-capabilities) |
| Build custom connectors | [Building custom connectors](https://support.claude.com/en/articles/11503834-building-custom-connectors-via-remote-mcp-servers) |
| Cowork guide | [Get Started with Cowork](https://support.claude.com/en/articles/13345190-get-started-with-cowork) |
| Claude API docs | [API Overview](https://docs.claude.com/en/api/overview) |
| Official plugins on GitHub | [anthropics/claude-plugins-official](https://github.com/anthropics/claude-plugins-official) |
| Plugin creation docs | [Create plugins](https://code.claude.com/docs/en/plugins) |
| MCP Connector API | [MCP Connector docs](https://platform.claude.com/docs/en/agents-and-tools/mcp-connector) |
| Claude Help Center | [support.claude.com](https://support.claude.com) |
| Anthropic website | [anthropic.com](https://www.anthropic.com) |

---

## Quick Reference Card

```
╔══════════════════════════════════════════════════════════════╗
║                    CLAUDE QUICK REFERENCE                    ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  WHAT YOU WANT              → USE THIS                       ║
║  ─────────────────────────────────────────────────────────   ║
║  Quick question             → Web Chat (claude.ai)           ║
║  Ongoing project            → Web Chat with Projects         ║
║  Connectors, more power     → Desktop Chat                   ║
║  Multi-step task + files    → Cowork                         ║
║  Recurring automation       → Cowork Scheduled Tasks         ║
║  Writing/reviewing code     → Claude Code Desktop            ║
║  Developer terminal use     → Claude Code CLI                ║
║                                                              ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  WHAT IT IS                 → QUICK DEFINITION               ║
║  ─────────────────────────────────────────────────────────   ║
║  Skill       → Instructions that make Claude better at       ║
║                one specific type of task                     ║
║  Plugin      → A bundle of skills + tools for a topic area   ║
║  Connector   → A link between Claude and another app         ║
║  MCP         → The technical protocol that powers            ║
║                connectors (Model Context Protocol)           ║
║  Project     → A persistent chat with memory + files         ║
║                                                              ║
╠══════════════════════════════════════════════════════════════╣
║                                                              ║
║  POWER USER TIP: The more context you give Claude,           ║
║  the better its answers. Upload files, use Projects,         ║
║  set up Memory, and build a knowledge folder.                ║
║                                                              ║
╚══════════════════════════════════════════════════════════════╝
```

---

*Last updated: March 2026 | Guide created by Claude (Cowork mode) from Trevor's personal setup*
