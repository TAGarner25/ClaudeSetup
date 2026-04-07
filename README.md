---
tags:
  - para/area
  - status/active
  - type/moc
  - claude
  - ai
created: 2026-03-23
updated: 2026-04-06
---

# Claude AI Tooling

A personal knowledge base and resource hub for Claude across all its surfaces — Chat, Cowork, and Code. Contains setup guides, reusable finance prompts, skill reference documentation, and curated external resources.

---

## Contents

- [General Overview](#general-overview) — Setup guides for Claude Desktop on Windows
- [Prompts](#prompts) — 20 institutional-grade finance prompts (ready to use)
- [Skills](#skills) — Custom prompts + reference docs for 20 skill categories + third-party skill libraries
- [Resources](#resources) — Curated external links for Claude, Gemini, Obsidian, Stitch, and Flow

---

## General Overview

Guides covering the full Claude ecosystem from installation to advanced usage.

| File | Description |
|------|-------------|
| [The Complete Claude Setup Guide](General%20Overview/The%20Complete%20Claude%20Setup%20Guide.md) | Beginner-to-power-user walkthrough of Claude.ai, Desktop, Cowork, and Code — surfaces, skills, plugins, connectors, and personal setup |
| [Guide to Claude Desktop on Windows](General%20Overview/Guide%20to%20Claude%20Dekstop%20on%20Windows.md) | Windows-specific install, configuration, and usage guide for Claude Desktop's three-tab architecture (Chat, Cowork, Code) |
| `The Complete Claude Setup Guide.pptx` | Presentation version of the setup guide |

---

## Prompts

20 institutional-style finance prompts, each modeled after a specific firm's analytical approach. Stored as individual `.txt` files — copy the prompt, fill in the `[BRACKETED FIELDS]`, and submit to Claude.

See [Finance Prompts Explained](Prompts/Finance/00_FINANCE_PROMPTS_EXPLAINED.md) for when and how to use each prompt.

### Series A — Investment & Trading Analysis

| # | Prompt | Modeled After |
|---|--------|---------------|
| 01 | [Stock Screener](Prompts/Finance/01_Goldman_Sachs_Stock_Screener.txt) | Goldman Sachs |
| 02 | [DCF Valuation](Prompts/Finance/02_Morgan_Stanley_DCF_Valuation.txt) | Morgan Stanley |
| 03 | [Risk Analysis Framework](Prompts/Finance/03_Bridgewater_Risk_Analysis_Framework.txt) | Bridgewater |
| 04 | [Earnings Breakdown](Prompts/Finance/04_JPMorgan_Earnings_Breakdown.txt) | JPMorgan |
| 05 | [Portfolio Construction](Prompts/Finance/05_BlackRock_Portfolio_Construction.txt) | BlackRock |
| 06 | [Technical Analysis System](Prompts/Finance/06_Citadel_Technical_Analysis_System.txt) | Citadel |
| 07 | [Dividend Strategy](Prompts/Finance/07_Harvard_Endowment_Dividend_Strategy.txt) | Harvard Endowment |
| 08 | [Competitive Advantage Analysis](Prompts/Finance/08_Bain_Competitive_Advantage_Analysis.txt) | Bain |
| 09 | [Pattern Finder](Prompts/Finance/09_Renaissance_Technologies_Pattern_Finder.txt) | Renaissance Technologies |
| 10 | [Macro Impact Assessment](Prompts/Finance/10_McKinsey_Macro_Impact_Assessment.txt) | McKinsey |

### Series B — Personal Finance & Wealth Planning

| # | Prompt | Modeled After |
|---|--------|---------------|
| 11 | [Wealth Diagnostic](Prompts/Finance/11_Goldman_Sachs_Wealth_Diagnostic.txt) | Goldman Sachs |
| 12 | [Retirement Planning Calculator](Prompts/Finance/12_Vanguard_Retirement_Planning_Calculator.txt) | Vanguard |
| 13 | [Investment Portfolio Architect](Prompts/Finance/13_Morgan_Stanley_Investment_Portfolio_Architect.txt) | Morgan Stanley |
| 14 | [Tax Optimization Strategist](Prompts/Finance/14_Deloitte_Tax_Optimization_Strategist.txt) | Deloitte |
| 15 | [Debt Elimination Engineer](Prompts/Finance/15_JPMorgan_Debt_Elimination_Engineer.txt) | JPMorgan |
| 16 | [Emergency Fund & Cash Strategy](Prompts/Finance/16_Charles_Schwab_Emergency_Fund_Cash_Strategy.txt) | Charles Schwab |
| 17 | [Insurance Audit](Prompts/Finance/17_Northwestern_Mutual_Insurance_Audit.txt) | Northwestern Mutual |
| 18 | [College Savings Architect](Prompts/Finance/18_Fidelity_College_Savings_Architect.txt) | Fidelity |
| 19 | [Estate Planning Organizer](Prompts/Finance/19_Edward_Jones_Estate_Planning_Organizer.txt) | Edward Jones |
| 20 | [Real Estate Investment Analyzer](Prompts/Finance/20_Wealthfront_Real_Estate_Investment_Analyzer.txt) | Wealthfront |

---

## Skills

### Custom Skills (Personal)

Two prompt collections built for direct use in Claude — each prompt is a complete, ready-to-submit instruction set with `[BRACKETED FIELDS]` to fill in.

| File | Series | Coverage |
|------|--------|----------|
| [skill_investment_analysis.md](Skills/skill_investment_analysis.md) | A | Stock screening, DCF valuation, risk analysis, earnings breakdown, portfolio construction, technical analysis, dividend strategy, competitive advantage, pattern recognition, macro impact |
| [skill_personal_finance.md](Skills/skill_personal_finance.md) | B | Wealth diagnostics, retirement planning, portfolio architecture, tax optimization, debt elimination, emergency funds, insurance audits, college savings, estate planning, real estate analysis |

> Start with Skill 11 (Wealth Diagnostic) if you're new to Series B — its output will direct you to the most relevant follow-on skills.

### Skill Reference Library

Reference documentation organized by category — these describe what each installed skill does, not the skills themselves. Actual skill installation happens via Claude's plugins/Cowork interface.

| # | Category | Files | Skills Covered |
|---|----------|-------|----------------|
| 01 | [Document Creation](Skills/Skill%20Files/01_Document_Creation/) | 13 | Word, PowerPoint, Excel, PDF, Canvas Design, Web Artifacts, MCP Builder, Skill Creator, Theme Factory, Brand Guidelines, Scheduling, Algorithmic Art, Doc Co-authoring |
| 02 | [Sales](Skills/Skill%20Files/02_Sales/) | 9 | Account Research, Call Prep, Call Summary, Outreach Drafting, Competitive Intel, Daily Briefing, Pipeline Review, Forecasting, Sales Assets |
| 03 | [Product Management](Skills/Skill%20Files/03_Product_Management/) | 7 | Feature Specs/PRDs, Competitive Analysis, Metrics Review, Roadmap Updates, Sprint Planning, Stakeholder Updates, User Research Synthesis |
| 04 | [Legal](Skills/Skill%20Files/04_Legal/) | 9 | Contract Review, NDA Triage, Compliance Checks, Legal Briefings, Inquiry Response, Meeting Briefings, Risk Assessment, E-Signatures, Vendor Status |
| 05 | [Operations](Skills/Skill%20Files/05_Operations/) | 9 | Process Docs, Change Management, Compliance Tracking, Risk Assessment, Runbooks, Process Optimization, Capacity Planning, Status Reports, Vendor Reviews |
| 06 | [Brand Voice](Skills/Skill%20Files/06_Brand_Voice/) | 3 | Brand Guidelines Generation, Brand Material Discovery, Voice Content Enforcement |
| 07 | [Finance & Accounting](Skills/Skill%20Files/07_Finance_Accounting/) | 5 | Journal Entries, Close Management, Variance Analysis, Reconciliation, Financial Statements |
| 08 | Data Analytics | 7 | SQL Queries, Dataset Profiling, Data Validation, Visualization (Python), Statistical Analysis, Dashboard Builder, Data Context Extraction |
| 09 | [Marketing](Skills/Skill%20Files/09_Marketing/) | 5 | Brand Voice/Style, Campaign Planning, Competitive Analysis, Content Drafting, Performance Analytics |
| 10 | [Productivity](Skills/Skill%20Files/10_Productivity/) | 2 | Memory Management, Task Management |
| 11 | [Engineering](Skills/Skill%20Files/11_Engineering/) | 6 | Code Review, Incident Response, System Architecture, Tech Debt, Technical Documentation, Testing Strategy |
| 12 | [Design](Skills/Skill%20Files/12_Design/) | 6 | Design Critique, Design System Management, Developer Handoff, UX Microcopy, User Research, WCAG Accessibility Audit |
| 13 | [Equity Research](Skills/Skill%20Files/13_Equity_Research/) | 9 | Initiating Coverage, Earnings Updates, Earnings Preview, Morning Notes, Model Updates, Thesis Tracking, Sector Overviews, Idea Screening, Catalyst Calendar |
| 14 | [Financial Analysis](Skills/Skill%20Files/14_Financial_Analysis/) | 9 | 3-Statement Model, LBO Model, DCF Model, Comps Analysis, Competitive Landscape, Deck Refresh, Deck QC, PPT Templates, Custom Skill Creator Guide |
| 15 | [Investment Banking](Skills/Skill%20Files/15_Investment_Banking/) | 9 | CIM Drafting, Pitch Deck Populator, Company Strip Profiles, Deal Teasers, Process Letters, Buyer Universe, Deal Pipeline, Merger Models, Financial Datapacks |
| 16 | [Private Equity](Skills/Skill%20Files/16_Private_Equity/) | 10 | Deal Sourcing, Deal Screening, Due Diligence Checklists, DD Meeting Prep, IC Memos, Portfolio Monitoring, Returns Analysis, Value Creation Plans, Unit Economics, AI Readiness Scans |
| 17 | [Wealth Management](Skills/Skill%20Files/17_Wealth_Management/) | 6 | Client Reports, Client Review Prep, Financial Plans, Investment Proposals, Portfolio Rebalancing, Tax-Loss Harvesting |
| 18 | [LSEG Fixed Income & Rates](Skills/Skill%20Files/18_LSEG_Fixed_Income_and_Rates/) | 8 | Bond RV Analysis, Bond Futures Basis, FX Carry Trade, Fixed Income Portfolio Review, Equity Research Snapshot, Macro Rates Dashboard, Option Volatility, Swap Curve Strategy |
| 19 | [S&P Global Market Intelligence](Skills/Skill%20Files/19_SP_Global_Market_Intelligence/) | 3 | Company Tear Sheets, Earnings Preview Reports, Funding Digest Slides |
| 20 | [Plugin Management](Skills/Skill%20Files/20_Plugin_Management/) | 2 | Plugin Creator Guide, Plugin Customizer |

**Total: 20 categories, 141+ skill reference files**

### Third-Party Skill Libraries

Cloned repos stored for reference and potential installation.

| Library | Path | Description |
|---------|------|-------------|
| **D3.js Visualization Skills** | [claude-d3js-skill-main](Skills/Skill%20Files/claude-d3js-skill-main/) | Interactive data visualization using D3.js — chart templates, color schemes, scale references, JSX component templates |
| **Stitch Skills** (Google Labs) | [stitch-skills-main](Skills/Skill%20Files/stitch-skills-main/) | 8 skills: design-md, prompt enhancement, React components, Remotion video composition, shadcn/ui, Stitch design workflows, Stitch Loop (multi-page site generation), taste-based design |
| **Erickson Brand Guidelines** | [Zip Folders](Skills/Skill%20Files/Zip%20Folders/) | Packaged brand guideline skill (also available as `.zip`) |

---

## Resources

Curated external link collections by tool/platform. Files for Gemini, Obsidian, Stitch, and Flow are placeholders pending population.

| File | Status | Coverage |
|------|--------|----------|
| [ClaudeResources.md](Resources/ClaudeResources.md) | Active | Anthropic docs, GitHub repos, 30+ community skills, agents, plugins, MCP servers, Claude Code guides |
| [GeminiResources.md](Resources/GeminiResources.md) | Placeholder | — |
| [ObsidianResources.md](Resources/ObsidianResources.md) | Placeholder | — |
| [StitchResources.md](Resources/StitchResources.md) | Placeholder | — |
| [FlowResources.md](Resources/FlowResources.md) | Placeholder | — |

---

#claude #ai #para/area #status/active
