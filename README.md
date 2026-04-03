---
tags:
  - para/area
  - status/active
  - type/moc
  - claude
  - ai
created: 2026-03-23
updated: 2026-04-03
---

# Claude AI Tooling — Area Overview

> **Area:** Claude AI (Chat · Cowork · Code)
> **Status:** Active — ongoing, no fixed end date
> **Home:** [[../NOTES READ ME|← Home]]

---

## What's Here

This repository is the central hub for everything related to using Claude across its surfaces — Chat, Cowork, and Claude Code. It stores skill reference documentation, reusable finance prompts, curated external resources, setup guides, and third-party skill libraries collected over time.

---

## Folder Structure

```
Claude/
├── CLAUDE READ ME.md              ← You are here — master index
├── General Overview/
│   ├── The Complete Claude Setup Guide.md
│   └── The Complete Claude Setup Guide.pptx
├── Prompts/
│   ├── 01–20 Finance Prompts (.txt)
│   └── FINANCE_PROMPTS_EXPLAINED.md
├── Resources/
│   └── ClaudeResources.md
└── Skills/
    ├── skill_investment_analysis.md
    ├── skill_personal_finance.md
    └── Skill Files/
        ├── 01–20 Category Folders (reference docs)
        ├── Zip Folders/ (packaged skills)
        ├── claude-d3js-skill-main/ (third-party)
        └── stitch-skills-main/ (third-party)
```

---

## General Overview

A comprehensive beginner-to-power-user guide covering the entire Claude ecosystem: surfaces, skills, plugins, connectors, and personal setup configuration.

- [[General Overview/The Complete Claude Setup Guide|The Complete Claude Setup Guide]] — Markdown version
- `General Overview/The Complete Claude Setup Guide.pptx` — Presentation version

---

## Skills

### Custom Skills (Personal)

Two custom prompt collections modeled after institutional finance approaches:

- [[Skills/skill_investment_analysis|Investment & Trading Analysis Skills (Series A)]] — 10 prompts covering stock screening, DCF valuation, risk analysis, earnings breakdowns, portfolio construction, technical analysis, dividend strategy, competitive advantage, pattern recognition, and macro impact assessment
- [[Skills/skill_personal_finance|Personal Finance & Wealth Planning Skills (Series B)]] — 10 prompts covering wealth diagnostics, retirement planning, portfolio architecture, tax optimization, debt elimination, emergency funds, insurance audits, college savings, estate planning, and real estate analysis

### Skill Reference Library

Reference documentation for skills organized by category. These are notes documenting what each skill does — the actual skills themselves are installed via plugins or the Cowork environment.

| # | Category | Files | Coverage |
|---|----------|-------|----------|
| 01 | [[Skills/Skill Files/01_Document_Creation/\|Document Creation]] | 14 | Word, PowerPoint, Excel, PDF, Canvas Design, Web Artifacts, MCP Builder, Skill Creator, Theme Factory, Brand Guidelines, Scheduling, Doc Co-authoring |
| 02 | [[Skills/Skill Files/02_Sales/\|Sales]] | 9 | Account Research, Call Prep, Call Summary, Outreach Drafting, Competitive Intel, Daily Briefing, Pipeline Review, Forecasting, Sales Assets |
| 03 | [[Skills/Skill Files/03_Product_Management/\|Product Management]] | 7 | Feature Specs/PRDs, Competitive Analysis, Metrics Review, Roadmap Updates, Sprint Planning, Stakeholder Updates, User Research Synthesis |
| 04 | [[Skills/Skill Files/04_Legal/\|Legal]] | 9 | Contract Review, NDA Triage, Compliance Checks, Legal Briefings, Inquiry Response, Meeting Briefings, Risk Assessment, E-Signatures, Vendor Status |
| 05 | [[Skills/Skill Files/05_Operations/\|Operations]] | 9 | Process Docs, Change Management, Compliance Tracking, Risk Assessment, Runbooks, Process Optimization, Capacity Planning, Status Reports, Vendor Reviews |
| 06 | [[Skills/Skill Files/06_Brand_Voice/\|Brand Voice]] | 3 | Brand Guidelines Generation, Brand Material Discovery, Voice Content Enforcement |
| 07 | [[Skills/Skill Files/07_Finance_Accounting/\|Finance & Accounting]] | 6 | Journal Entries, Close Management, Variance Analysis, Reconciliation, Financial Statements, Audit Support |
| 08 | [[Skills/Skill Files/08_Data_Analytics/\|Data Analytics]] | 7 | SQL Queries, Dataset Profiling, Data Validation, Visualization (Python), Statistical Analysis, Dashboard Builder, Data Context Extraction |
| 09 | [[Skills/Skill Files/09_Marketing/\|Marketing]] | 5 | Brand Voice/Style, Campaign Planning, Competitive Analysis, Content Drafting, Performance Analytics |
| 10 | [[Skills/Skill Files/10_Productivity/\|Productivity]] | 2 | Memory Management, Task Management |
| 11 | [[Skills/Skill Files/11_Engineering/\|Engineering]] | 6 | Code Review, Incident Response, System Architecture, Tech Debt, Technical Documentation, Testing Strategy |
| 12 | [[Skills/Skill Files/12_Design/\|Design]] | 6 | Design Critique, Design System Management, Developer Handoff, UX Microcopy, User Research, WCAG Accessibility Audit |
| 13 | [[Skills/Skill Files/13_Equity_Research/\|Equity Research]] | 9 | Initiating Coverage, Earnings Updates, Earnings Preview, Morning Notes, Model Updates, Thesis Tracking, Sector Overviews, Idea Screening, Catalyst Calendar |
| 14 | [[Skills/Skill Files/14_Financial_Analysis/\|Financial Analysis]] | 11 | 3-Statement Model, LBO Model, DCF Model, Comps Analysis, Competitive Landscape, Deck Refresh, Deck QC, Data Cleaning, Formula Audit, PPT Templates, Custom Skill Creator Guide |
| 15 | [[Skills/Skill Files/15_Investment_Banking/\|Investment Banking]] | 9 | CIM Drafting, Pitch Deck Populator, Company Strip Profiles, Deal Teasers, Process Letters, Buyer Universe, Deal Pipeline, Merger Models, Financial Datapacks |
| 16 | [[Skills/Skill Files/16_Private_Equity/\|Private Equity]] | 10 | Deal Sourcing, Deal Screening, Due Diligence Checklists, DD Meeting Prep, IC Memos, Portfolio Monitoring, Returns Analysis, Value Creation Plans, Unit Economics, AI Readiness Scans |
| 17 | [[Skills/Skill Files/17_Wealth_Management/\|Wealth Management]] | 6 | Client Reports, Client Review Prep, Financial Plans, Investment Proposals, Portfolio Rebalancing, Tax-Loss Harvesting |
| 18 | [[Skills/Skill Files/18_LSEG_Fixed_Income_and_Rates/\|LSEG Fixed Income & Rates]] | 8 | Bond RV Analysis, Bond Futures Basis, FX Carry Trade, Fixed Income Portfolio Review, Equity Research Snapshot, Macro Rates Dashboard, Option Volatility, Swap Curve Strategy |
| 19 | [[Skills/Skill Files/19_SP_Global_Market_Intelligence/\|S&P Global Market Intelligence]] | 3 | Company Tear Sheets, Earnings Preview Reports, Funding Digest Slides |
| 20 | [[Skills/Skill Files/20_Plugin_Management/\|Plugin Management]] | 2 | Plugin Creator Guide, Plugin Customizer |

**Total: 20 categories, 141 skill reference files**

### Third-Party Skill Repositories

Cloned/downloaded skill repos stored for reference and potential installation:

- **D3.js Visualization Skills** (`Skills/Skill Files/claude-d3js-skill-main/`) — Interactive data visualization skill using D3.js for custom charts, network diagrams, geographic visualizations, and animated transitions. Includes chart templates, color scheme references, and scale reference docs.
- **Stitch Skills** (`Skills/Skill Files/stitch-skills-main/`) — Google Labs skill library for the Stitch MCP server. Includes skills for design-md generation, prompt enhancement, React components, Remotion video composition, shadcn/ui components, Stitch design workflows, Stitch Loop (multi-page site generation), and taste-based design.
- **Erickson Brand Guidelines** (`Skills/Skill Files/Zip Folders/erickson-brand-guidelines/`) — Packaged brand guideline skill for Erickson Group styling (also available as .zip).

---

## Prompts

A library of **20 institutional-style finance prompts** stored as individual .txt files, each modeled after a specific firm's analytical approach:

| # | Prompt | Modeled After |
|---|--------|---------------|
| 01 | Stock Screener | Goldman Sachs |
| 02 | DCF Valuation | Morgan Stanley |
| 03 | Risk Analysis Framework | Bridgewater |
| 04 | Earnings Breakdown | JPMorgan |
| 05 | Portfolio Construction | BlackRock |
| 06 | Technical Analysis System | Citadel |
| 07 | Dividend Strategy | Harvard Endowment |
| 08 | Competitive Advantage Analysis | Bain |
| 09 | Pattern Finder | Renaissance Technologies |
| 10 | Macro Impact Assessment | McKinsey |
| 11 | Wealth Diagnostic | Goldman Sachs |
| 12 | Retirement Planning Calculator | Vanguard |
| 13 | Investment Portfolio Architect | Morgan Stanley |
| 14 | Tax Optimization Strategist | Deloitte |
| 15 | Debt Elimination Engineer | JPMorgan |
| 16 | Emergency Fund/Cash Strategy | Charles Schwab |
| 17 | Insurance Audit | Northwestern Mutual |
| 18 | College Savings Architect | Fidelity |
| 19 | Estate Planning Organizer | Edward Jones |
| 20 | Real Estate Investment Analyzer | Wealthfront |

Prompts 01–10 focus on investment analysis (Series A). Prompts 11–20 focus on personal finance and wealth planning (Series B).

See [[Prompts/FINANCE_PROMPTS_EXPLAINED|Finance Prompts Explained]] for a detailed breakdown of when and how to use each prompt.

---

## Resources

A curated collection of external links for maximizing Claude usage:

- [[Resources/ClaudeResources|Claude Resources]] — master link collection covering:
  - **Anthropic Documentation** — official docs on skills, tool use, MCPs, context windows, compaction, code execution, connectors, plugins, and cookbooks
  - **GitHub Repositories** — Anthropic's official repos, community skill repos, plugin collections, Claude Code best practices, config examples, marketplace directories
  - **Skills** — links to 30+ individual community-built skills covering data analysis, database design, visualization, dashboards, finance, PowerPoint, and more
  - **Agents** — data intelligence agents, orchestration/automation agents, agent toolkit repos
  - **Plugins** — official Anthropic plugins, database plugins, visual explainer, developer kit, business plugins, compound engineering, SWE marketplace, and more
  - **Placeholder sections** for Claude.md examples, websites, social media, and YouTube videos (to be populated)

---

## Notes & Reference

- [[Prompts/FINANCE_PROMPTS_EXPLAINED|Finance Prompts Explained]] — detailed breakdown of all 20 finance prompts with use cases and methodology

---

#claude #ai #para/area #status/active
