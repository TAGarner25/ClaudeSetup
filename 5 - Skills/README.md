---
title: Skills Read Me
description: Provides an overview of what skills are and navigation for the ./Skills/ folder.
author: Trevor Garner
created: 04/07/2026
updated: 2026-04-16
topics:
    - Skills
    - AI
    - Tools
    - Claude
    - Anthropic
    - Specification
---

# Skills

A reference and navigation hub for every Agent Skill bundled in this repository. Skills are an open, file-based standard for extending Claude (and other agents) with specialized knowledge and workflows.

## Table of contents

### File Navigation

- [What are skills](#what-are-skills)
- [How to install and use skills](#how-to-install-and-use-skills)
    - [Installation](#installation)
    - [Use](#use)
- [Creating custom skills](#creating-custom-skills)
- [Skill collections](#skill-collections)
- [Additional resources](#additional-resources)

### Folder navigation

**General business**
- [01_Document_Creation/](01_Document_Creation/) — Word, Excel, PowerPoint, PDF, web artifacts, MCP server scaffolding, brand-styled documents, the meta `Skill_Creator` (14 skills)
- [02_Sales/](02_Sales/) — account research, call prep & summary, battlecards, daily briefings, outreach, pipeline review, asset generation, forecasting (9 skills)
- [03_Product_Management/](03_Product_Management/) — PRDs, competitive analysis, metrics review, roadmap prioritization, sprint planning, stakeholder updates, user research synthesis (7 skills)
- [04_Legal/](04_Legal/) — contract redlines, compliance checks, NDA triage, risk assessments, e-signature workflows, vendor agreements, briefings (9 skills)
- [05_Operations/](05_Operations/) — process docs, change management, audit tracking, runbooks, capacity planning, KPI status reports, vendor evaluation (9 skills)
- [06_Brand_Voice/](06_Brand_Voice/) — brand guideline generation, brand material discovery, voice enforcement (3 skills)
- [07_Finance_Accounting/](07_Finance_Accounting/) — month-end close, journal entries, P&L variance, reconciliation, fund statements, audit support (6 skills)
- [08_Data_Analytics/](08_Data_Analytics/) — SQL writing, dataset profiling, statistical analysis, Python viz, HTML dashboards, analysis QA, context extraction (7 skills)
- [09_Marketing/](09_Marketing/) — campaign planning, content drafting, competitive analysis, performance analytics, brand voice style guides (5 skills)
- [10_Productivity/](10_Productivity/) — memory management system, task management (2 skills)
- [11_Engineering/](11_Engineering/) — code review, incident triage, system architecture, tech debt, documentation, testing strategy (6 skills)
- [12_Design/](12_Design/) — design critique, design system management, dev handoff, UX microcopy, user research planning, WCAG audit (6 skills)

**Finance specialists**
- [13_Equity_Research/](13_Equity_Research/) — initiating coverage, earnings updates & previews, model updates, sector overviews, morning notes, catalyst calendars, screeners, thesis tracking (9 skills)
- [14_Financial_Analysis/](14_Financial_Analysis/) — DCF, comps, LBO, three-statement, deck QA, presentation refresh, spreadsheet cleaning/auditing, Series B Personal Finance prompts, Custom Skill Creator Guide (12 skills)
- [15_Investment_Banking/](15_Investment_Banking/) — accretion/dilution, teasers, CIM, buyer universe, strip profiles, deal pipeline, datapacks, pitch decks, process letters, Series A Investment Analysis prompts (10 skills)
- [16_Private_Equity/](16_Private_Equity/) — deal sourcing, inbound screening, DD checklists & meeting prep, IC memos, IRR/MOIC, portfolio monitoring, value creation, unit economics, AI-readiness scans (10 skills)
- [17_Wealth_Management/](17_Wealth_Management/) — performance reports, review-meeting prep, financial plans, investment proposals, rebalancing, tax-loss harvesting (6 skills)
- [18_LSEG_Fixed_Income_and_Rates/](18_LSEG_Fixed_Income_and_Rates/) — bond futures basis, relative value, FX carry, portfolio review, equity research snapshots, macro rates dashboard, option vol, swap-curve strategy (8 skills)
- [19_SP_Global_Market_Intelligence/](19_SP_Global_Market_Intelligence/) — company tear sheets, earnings preview reports, funding digest slides (3 skills)
- [20_Plugin_Management/](20_Plugin_Management/) — plugin creator guide, plugin customizer (2 skills)

**Third-party / external**
- [21_D3js_Skills/](21_D3js_Skills/) — `d3-viz` skill with assets and references for interactive D3.js visualizations
- [22_EricksonGroup_BrandGuidelines/](22_EricksonGroup_BrandGuidelines/) — Erickson Group brand guideline skill
- [23_GoogleStitch_Skills/](23_GoogleStitch_Skills/) — Google's open-source Stitch MCP collection: stitch-design, stitch-loop, design-md, enhance-prompt, react-components, shadcn-ui, remotion, taste-design (8 skills)

**Special folders**
- [Overview/](Overview/) — source material on what a skill is (from the open AgentSkills spec)
- [XX_ZipFolders/](XX_ZipFolders/) — pre-packaged installable skill bundles

## What are skills

**Agent Skills** are modular, filesystem-based capabilities that extend Claude's functionality. At their core, a skill is just a folder containing a `SKILL.md` file with YAML frontmatter (a `name` and `description`) and Markdown instructions that tell the agent how to perform a specific task. Skills can also bundle scripts, templates, and reference documents.

```directory
my-skill/
├── SKILL.md          # Required: instructions + metadata
├── scripts/          # Optional: executable code
├── references/       # Optional: documentation
└── assets/           # Optional: templates, resources
```

Skills work via **progressive disclosure** — Claude loads context in three stages so capability scales without bloating the context window:

| Level | When loaded | Token cost | Content |
|-------|-------------|-----------|---------|
| **1. Metadata** | Always (at startup) | ~100 tokens per skill | `name` + `description` from YAML frontmatter |
| **2. Instructions** | When the skill is triggered | Under ~5k tokens | Body of `SKILL.md` |
| **3. Resources / code** | As needed via bash | Effectively unlimited | Bundled files, scripts, references |

Why this matters:
- **Specialize Claude** for domain-specific tasks without retraining.
- **Reduce repetition** — write the playbook once, use it automatically across conversations.
- **Compose capabilities** — multiple skills can combine into complex workflows.
- **No context penalty** for bundled content that isn't used in a given task.

Skills follow the [Agent Skills open standard](https://agentskills.io), which makes them portable across compatible agents (Claude Code, Claude.ai, Anthropic API, Cursor, Gemini CLI, Antigravity, and others).

## How to install and use skills

Skills are available across Claude's surfaces, but the install path differs:

| Surface | How skills are installed |
|---------|-------------------------|
| **Claude Code** | Custom skills only — drop a folder into one of the skills directories below |
| **Claude.ai** (Pro/Max/Team/Enterprise) | Upload a zip via **Settings → Capabilities → Skills** (per user, not org-wide) |
| **Claude API** | Upload via the `/v1/skills` endpoints; reference by `skill_id` in the `container` parameter (requires beta headers `code-execution-2025-08-25`, `skills-2025-10-02`, `files-api-2025-04-14`) |

Anthropic also ships **pre-built skills** (PowerPoint `pptx`, Excel `xlsx`, Word `docx`, PDF `pdf`) that work automatically on Claude.ai and the API with no setup.

### Installation

**Claude Code — file paths (highest priority wins):**

| Scope | Path | Applies to |
|-------|------|-----------|
| Enterprise | Managed settings location | All users in the org |
| Personal | `~/.claude/skills/<skill-name>/SKILL.md` | All your projects |
| Project | `.claude/skills/<skill-name>/SKILL.md` | This project only |
| Plugin | `<plugin>/skills/<skill-name>/SKILL.md` | Wherever the plugin is enabled |

Claude Code watches these directories and picks up new or edited skills live, no restart required (unless you create a brand-new top-level skills directory).

**From a packaged zip (e.g. files in [XX_ZipFolders/](XX_ZipFolders/)):**
1. Unzip the bundle so it produces a folder containing `SKILL.md`.
2. Move that folder into `~/.claude/skills/` (personal) or `.claude/skills/` (project).
3. Confirm by asking Claude *"What skills are available?"* or by typing `/` to see the autocomplete menu.

**From the open-source Stitch repository (example pattern, see [23_GoogleStitch_Skills/README.md](23_GoogleStitch_Skills/README.md)):**
```bash
# List all available skills in a repo
npx skills add google-labs-code/stitch-skills --list

# Install a specific skill globally
npx skills add google-labs-code/stitch-skills --skill stitch-design --global
```

**Claude.ai:** Zip the skill folder, then go to **Settings → Capabilities → Skills → Upload skill**. Code execution must be enabled.

### Use

Once installed, you can invoke a skill three ways:

1. **Automatic** — Claude reads each skill's `description` at startup and triggers the right one when your request matches. Just describe what you want ("summarize this PR", "build a DCF model") and Claude pulls the skill in.
2. **Slash command** — type `/<skill-name>` (for example `/explain-code`, `/commit`, `/deploy`). The skill name maps directly to the slash command.
3. **With arguments** — `/fix-issue 123` passes `123` as `$ARGUMENTS` (or `$0`, `$1`, … for positional args) inside the skill body.

Useful behavior to know:
- Skill content enters the conversation as a single message and stays for the rest of the session — Claude doesn't re-read the file each turn.
- `disable-model-invocation: true` in frontmatter restricts a skill to manual `/name` invocation only (good for deploys, commits, anything with side effects).
- `allowed-tools: Bash(git *)` pre-approves tools while the skill is active so you aren't prompted for permission.
- After auto-compaction, Claude Code re-attaches recent skills (first 5,000 tokens of each, 25,000-token combined budget).

## Creating custom skills

Every skill needs a `SKILL.md` with YAML frontmatter. Minimum viable skill:

```markdown
---
name: my-skill-name
description: Brief description of what this skill does and when Claude should use it.
---

# My Skill

## When to use this skill
[trigger phrases and example requests]

## Instructions
1. Step-by-step guidance for Claude.
2. Reference any bundled files: see [reference.md](reference.md).
```

**Field rules:**
- `name`: max 64 chars, lowercase letters / numbers / hyphens only. Cannot contain "anthropic" or "claude".
- `description`: max 1,024 chars (the listing truncates the combined `description` + `when_to_use` at ~1,536 chars). Front-load the key use case and trigger phrases — this is what Claude uses to decide whether to fire the skill.

**Optional Claude Code-specific frontmatter** (see [code.claude.com/docs/en/skills](https://code.claude.com/docs/en/skills) for the full table):
- `disable-model-invocation` — only the user can invoke
- `user-invocable: false` — only Claude can invoke (for background knowledge)
- `allowed-tools` — pre-approved tool list while the skill is active
- `argument-hint` — autocomplete hint, e.g. `[issue-number]`
- `context: fork` + `agent` — run the skill in a forked subagent
- `paths` — glob patterns that limit auto-activation to matching files
- `model`, `effort`, `hooks`, `shell` — per-skill overrides

**Recommended structure for non-trivial skills:**
```
my-skill/
├── SKILL.md              # Required — keep under ~500 lines
├── reference.md          # Detailed docs, loaded only when SKILL.md links to it
├── examples.md           # Concrete examples
└── scripts/
    └── helper.py         # Executed via bash; the script body never enters context
```

This repo includes meta-skills that walk through the authoring loop: [01_Document_Creation/Skill_Creator.md](01_Document_Creation/Skill_Creator.md) (intent → draft → eval → iterate) and [14_Financial_Analysis/Custom_Skill_Creator_Guide.md](14_Financial_Analysis/Custom_Skill_Creator_Guide.md).

## Skill collections

The folders below group skills by domain. Numbered prefixes are organizational only — they have no effect on how skills load.

**General business (01–12)**

- [01_Document_Creation/](01_Document_Creation/) — 14 skills covering core document workflows: Word, Excel, PowerPoint, PDF, web artifacts, MCP server scaffolding, scheduled task creation, brand-styled documents, and the meta `Skill_Creator`.
- [02_Sales/](02_Sales/) — 9 skills for the sales motion: account research, call prep & summary, competitive battlecards, daily briefings, personalized outreach, pipeline review, asset generation, forecasting.
- [03_Product_Management/](03_Product_Management/) — 7 skills for PMs: PRD/spec writing, competitive analysis, product metrics review, roadmap prioritization, sprint planning, stakeholder updates, user research synthesis.
- [04_Legal/](04_Legal/) — 9 skills for in-house legal: contract redlines, compliance checks, NDA triage, risk assessments, e-signature workflows, vendor agreement tracking, legal briefings.
- [05_Operations/](05_Operations/) — 9 skills for ops leaders: process documentation, change management, audit tracking, runbook authoring, capacity planning, KPI status reports, vendor evaluation.
- [06_Brand_Voice/](06_Brand_Voice/) — 3 skills for generating brand guidelines, discovering existing brand material, and enforcing voice across content.
- [07_Finance_Accounting/](07_Finance_Accounting/) — 6 corporate-finance skills: month-end close, journal entries, P&L variance, cash/position reconciliation, fund financial statements, audit support.
- [08_Data_Analytics/](08_Data_Analytics/) — 7 analytics skills: SQL writing, dataset profiling, statistical analysis, Python visualizations, interactive HTML dashboards, analysis QA, context extraction.
- [09_Marketing/](09_Marketing/) — 5 skills for marketers: campaign planning, content drafting, competitive analysis, performance analytics, brand voice style guides.
- [10_Productivity/](10_Productivity/) — 2 personal-productivity skills: a memory management system and lightweight task management.
- [11_Engineering/](11_Engineering/) — 6 engineering skills: code review, incident triage, system architecture, tech debt prioritization, technical documentation, testing strategy.
- [12_Design/](12_Design/) — 6 design skills: design critique, design system management, dev handoff, UX microcopy, user research planning, WCAG accessibility audit.

**Finance-specialist skills (13–20)**

- [13_Equity_Research/](13_Equity_Research/) — 9 sell-side research skills: initiating coverage, earnings updates & previews, financial model updates, sector overviews, morning notes, catalyst calendars, idea screeners, thesis tracking.
- [14_Financial_Analysis/](14_Financial_Analysis/) — 12 analyst skills: DCF, comparable company analysis, LBO and three-statement models, deck-quality checking, presentation refresh, spreadsheet cleaning/auditing, plus the **Series B Personal Finance** prompt set and a `Custom_Skill_Creator_Guide`.
- [15_Investment_Banking/](15_Investment_Banking/) — 10 IB skills: accretion/dilution merger model, anonymous teasers, CIM drafting, buyer universe building, company strip profiles, deal pipeline tracking, financial datapacks, pitch deck templates, process letters, plus the **Series A Investment Analysis** prompt set.
- [16_Private_Equity/](16_Private_Equity/) — 10 PE skills: deal sourcing, inbound screening, due-diligence checklists & meeting prep, IC memos, IRR/MOIC analysis, portfolio monitoring, post-acquisition value creation, unit economics, AI-readiness scans.
- [17_Wealth_Management/](17_Wealth_Management/) — 6 wealth-advisor skills: client performance reports, review-meeting prep, financial plan building, investment proposals, portfolio rebalancing, tax-loss harvesting.
- [18_LSEG_Fixed_Income_and_Rates/](18_LSEG_Fixed_Income_and_Rates/) — 8 fixed-income & rates skills built around LSEG data: bond futures basis, relative value, FX carry trade, portfolio review, equity research snapshots, macro rates dashboard, option vol, swap-curve strategy.
- [19_SP_Global_Market_Intelligence/](19_SP_Global_Market_Intelligence/) — 3 S&P-data skills: company tear sheets, earnings preview reports, funding digest slides.
- [20_Plugin_Management/](20_Plugin_Management/) — 2 meta-skills for authoring and customizing Claude Code plugins.

**Third-party / external skills (21–23)**

- [21_D3js_Skills/](21_D3js_Skills/) — Single bundled skill (`d3-viz`) with `assets/` and `references/` for building interactive D3.js visualizations across React, Vue, Svelte, or vanilla JS.
- [22_EricksonGroup_BrandGuidelines/](22_EricksonGroup_BrandGuidelines/) — Erickson Group brand guideline skill (single `SKILL.md`).
- [23_GoogleStitch_Skills/](23_GoogleStitch_Skills/) — Google's open-source Stitch MCP skill collection: `stitch-design`, `stitch-loop`, `design-md`, `enhance-prompt`, `react-components`, `shadcn-ui`, `remotion`, `taste-design`. Install via `npx skills add google-labs-code/stitch-skills`.

**Special folders**

- [Overview/](Overview/) — Source material for "what is a skill", pulled from the open AgentSkills spec.
- [XX_ZipFolders/](XX_ZipFolders/) — Pre-packaged installable bundles (currently `erickson-brand-guidelines.zip`).

## Additional resources

**Official Anthropic documentation**
- [Agent Skills overview](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview) — concepts, progressive disclosure, where skills work
- [Use Skills in Claude Code](https://code.claude.com/docs/en/skills) — file paths, frontmatter reference, advanced patterns
- [Authoring best practices](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/best-practices)
- [Skills quickstart (API)](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/quickstart)
- [Skills cookbook](https://platform.claude.com/cookbook/skills-notebooks-01-skills-introduction) — end-to-end custom skill examples
- [Engineering blog: Equipping agents with Agent Skills](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)

**Open standard & community**
- [agentskills.io](https://agentskills.io) — the open Agent Skills spec
- [github.com/agentskills/agentskills](https://github.com/agentskills/agentskills) — reference library and validators
- [github.com/anthropics/skills](https://github.com/anthropics/skills) — Anthropic's official open-source skill examples

**Claude.ai help center**
- [What are Skills?](https://support.claude.com/en/articles/12512176-what-are-skills)
- [Using Skills in Claude](https://support.claude.com/en/articles/12512180-using-skills-in-claude)
- [How to create custom Skills](https://support.claude.com/en/articles/12512198-creating-custom-skills)
- [Teach Claude your way of working using Skills](https://support.claude.com/en/articles/12580051-teach-claude-your-way-of-working-using-skills)
