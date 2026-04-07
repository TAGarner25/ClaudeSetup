---
title: Claude Setup Documents
description: Tips, tricks, and other information on how to setup and use Claude (or other AI tools).
created: 2026-03-23
updated: 2026-04-07
---

# Claude AI Tooling

A personal knowledge base and resource hub for Claude across all its surfaces — Chat, Cowork, and Code. Contains setup guides, reusable prompts, skill reference documentation, and curated external resources. Synced with Obsidian.

---

## Contents

- [General Overview](#general-overview) — Setup guides and product deep-dives for Claude and Google AI
- [Cheat Sheets](#cheat-sheets) — Quick-reference guides
- [Prompts](#prompts) — Finance, design, Excel, data analysis, and document generation prompts
- [Skills](#skills) — 23 skill categories with 180+ reference files, plus third-party skill libraries
- [Hooks](#hooks) — Claude Code hook examples
- [Plugins](#plugins) — Claude Code plugin examples
- [Use Cases](#use-cases) — Domain-specific workflow examples
- [Resources](#resources) — Curated external links for Claude, Gemini, Obsidian, Stitch, and Flow

---

## General Overview

Guides covering the Claude ecosystem and Google AI products, from installation to advanced usage.

### Setup

| File | Description |
|------|-------------|
| [The Complete Claude Setup Guide](General%20Overview/1_Setup/The%20Complete%20Claude%20Setup%20Guide.md) | Beginner-to-power-user walkthrough of Claude.ai, Desktop, Cowork, and Code |
| [Guide to Claude Desktop on Windows](General%20Overview/1_Setup/Guide%20to%20Claude%20Dekstop%20on%20Windows.md) | Windows-specific install, configuration, and usage guide |
| [`The Complete Claude Setup Guide.pptx`](General%20Overview/1_Setup/pptx/The%20Complete%20Claude%20Setup%20Guide.pptx) | Presentation version of the setup guide |

### Anthropic Claude Products

Product-specific guides under [`General Overview/2_Anthropic/`](General%20Overview/2_Anthropic/).

| Guide | Link |
|-------|------|
| Anthropic Claude Overview | [README.md](General%20Overview/2_Anthropic/README.md) |
| Claude Chat | [README.md](General%20Overview/2_Anthropic/Claude%20Chat/README.md) |
| Claude Code | [README.md](General%20Overview/2_Anthropic/Claude%20Code/README.md) |
| Master Claude Code — The Complete Guide | [Guide](General%20Overview/2_Anthropic/Claude%20Code/Master%20Claude%20Code%20-%20The%20Complete%20Guide.md) |
| Claude Computer Use | [README.md](General%20Overview/2_Anthropic/Claude%20Computer%20Use/README.md) |
| Claude Cowork | [README.md](General%20Overview/2_Anthropic/Claude%20Cowork/README.md) |
| Claude Desktop | [README.md](General%20Overview/2_Anthropic/Claude%20Desktop/README.md) |
| Claude For Excel | [README.md](General%20Overview/2_Anthropic/Claude%20For%20Excel/README.md) |
| Claude For PowerPoint | [README.md](General%20Overview/2_Anthropic/Claude%20For%20PowerPoint/README.md) |
| Claude Projects | [README.md](General%20Overview/2_Anthropic/Claude%20Projects/README.md) |

### Google AI Products

| Guide | Link |
|-------|------|
| Google AI Overview | [README.md](General%20Overview/3_Google/README.md) |
| Stitch Design-MD Format | [stitch-design-md-format.md](General%20Overview/3_Google/Stitch/stitch-design-md-format.md) |
| Stitch Design-MD Guide | [stitch-design-md-guide.md](General%20Overview/3_Google/Stitch/stitch-design-md-guide.md) |
| Stitch Prompting Guide | [stitch-prompting-guide.md](General%20Overview/3_Google/Stitch/stitch-prompting-guide.md) |

---

## Cheat Sheets

Quick-reference guides — see [`Cheat Sheets/`](Cheat%20Sheets/).

---

## Prompts

Prompt templates organized by domain. Each prompt uses `[BRACKETED FIELDS]` as fill-in-the-blank placeholders.

| Domain | Path | Contents |
|--------|------|----------|
| Finance | [Prompts/Finance/](Prompts/Finance/) | 20 institutional-grade finance prompts ([explained here](Prompts/Finance/README.md)) |
| Design | [Prompts/Design/](Prompts/Design/) | [Diagram generation prompt](Prompts/Design/diagram-generation.md) |
| Excel | [Prompts/Excel/](Prompts/Excel/) | [Three-Statement Financial Model](Prompts/Excel/Financial%20Modelling/Three_Statement_Financial_Model.md) |
| Data Analysis | [Prompts/Data Analysis/](Prompts/Data%20Analysis/) | Data analysis prompts |
| Document Generation | [Prompts/Document Generation/](Prompts/Document%20Generation/) | Document generation prompts |
| PowerPoint | [Prompts/PowerPoint/](Prompts/PowerPoint/) | PowerPoint prompts |

### Finance Prompts — Series A (Investment & Trading Analysis)

| # | Prompt | Modeled After |
|---|--------|---------------|
| 01 | [Stock Screener](Prompts/Finance/Insitutional%20Finance/01_Goldman_Sachs_Stock_Screener.md) | Goldman Sachs |
| 02 | [DCF Valuation](Prompts/Finance/Insitutional%20Finance/02_Morgan_Stanley_DCF_Valuation.md) | Morgan Stanley |
| 03 | [Risk Analysis Framework](Prompts/Finance/Insitutional%20Finance/03_Bridgewater_Risk_Analysis_Framework.md) | Bridgewater |
| 04 | [Earnings Breakdown](Prompts/Finance/Insitutional%20Finance/04_JPMorgan_Earnings_Breakdown.md) | JPMorgan |
| 05 | [Portfolio Construction](Prompts/Finance/Insitutional%20Finance/05_BlackRock_Portfolio_Construction.md) | BlackRock |
| 06 | [Technical Analysis System](Prompts/Finance/Insitutional%20Finance/06_Citadel_Technical_Analysis_System.md) | Citadel |
| 07 | [Dividend Strategy](Prompts/Finance/Insitutional%20Finance/07_Harvard_Endowment_Dividend_Strategy.md) | Harvard Endowment |
| 08 | [Competitive Advantage Analysis](Prompts/Finance/Insitutional%20Finance/08_Bain_Competitive_Advantage_Analysis.md) | Bain |
| 09 | [Pattern Finder](Prompts/Finance/Insitutional%20Finance/09_Renaissance_Technologies_Pattern_Finder.md) | Renaissance Technologies |
| 10 | [Macro Impact Assessment](Prompts/Finance/Insitutional%20Finance/10_McKinsey_Macro_Impact_Assessment.md) | McKinsey |

### Finance Prompts — Series B (Personal Finance & Wealth Planning)

| # | Prompt | Modeled After |
|---|--------|---------------|
| 11 | [Wealth Diagnostic](Prompts/Finance/Insitutional%20Finance/11_Goldman_Sachs_Wealth_Diagnostic.md) | Goldman Sachs |
| 12 | [Retirement Planning Calculator](Prompts/Finance/Insitutional%20Finance/12_Vanguard_Retirement_Planning_Calculator.md) | Vanguard |
| 13 | [Investment Portfolio Architect](Prompts/Finance/Insitutional%20Finance/13_Morgan_Stanley_Investment_Portfolio_Architect.md) | Morgan Stanley |
| 14 | [Tax Optimization Strategist](Prompts/Finance/Insitutional%20Finance/14_Deloitte_Tax_Optimization_Strategist.md) | Deloitte |
| 15 | [Debt Elimination Engineer](Prompts/Finance/Insitutional%20Finance/15_JPMorgan_Debt_Elimination_Engineer.md) | JPMorgan |
| 16 | [Emergency Fund & Cash Strategy](Prompts/Finance/Insitutional%20Finance/16_Charles_Schwab_Emergency_Fund_Cash_Strategy.md) | Charles Schwab |
| 17 | [Insurance Audit](Prompts/Finance/Insitutional%20Finance/17_Northwestern_Mutual_Insurance_Audit.md) | Northwestern Mutual |
| 18 | [College Savings Architect](Prompts/Finance/Insitutional%20Finance/18_Fidelity_College_Savings_Architect.md) | Fidelity |
| 19 | [Estate Planning Organizer](Prompts/Finance/Insitutional%20Finance/19_Edward_Jones_Estate_Planning_Organizer.md) | Edward Jones |
| 20 | [Real Estate Investment Analyzer](Prompts/Finance/Insitutional%20Finance/20_Wealthfront_Real_Estate_Investment_Analyzer.md) | Wealthfront |

---

## Skills

### Skill Reference Library

Reference documentation for 23 skill categories. These describe what each installed skill does — actual skill installation happens via Claude's plugin/Cowork interfaces.

| # | Category | Files |
|---|----------|-------|
| 01 | [Document Creation](Skills/01_Document_Creation/) | 14 |
| 02 | [Sales](Skills/02_Sales/) | 9 |
| 03 | [Product Management](Skills/03_Product_Management/) | 7 |
| 04 | [Legal](Skills/04_Legal/) | 9 |
| 05 | [Operations](Skills/05_Operations/) | 9 |
| 06 | [Brand Voice](Skills/06_Brand_Voice/) | 3 |
| 07 | [Finance & Accounting](Skills/07_Finance_Accounting/) | 6 |
| 08 | [Data Analytics](Skills/08_Data_Analytics/) | 7 |
| 09 | [Marketing](Skills/09_Marketing/) | 5 |
| 10 | [Productivity](Skills/10_Productivity/) | 2 |
| 11 | [Engineering](Skills/11_Engineering/) | 6 |
| 12 | [Design](Skills/12_Design/) | 6 |
| 13 | [Equity Research](Skills/13_Equity_Research/) | 9 |
| 14 | [Financial Analysis](Skills/14_Financial_Analysis/) | 12 |
| 15 | [Investment Banking](Skills/15_Investment_Banking/) | 10 |
| 16 | [Private Equity](Skills/16_Private_Equity/) | 10 |
| 17 | [Wealth Management](Skills/17_Wealth_Management/) | 6 |
| 18 | [LSEG Fixed Income & Rates](Skills/18_LSEG_Fixed_Income_and_Rates/) | 8 |
| 19 | [S&P Global Market Intelligence](Skills/19_SP_Global_Market_Intelligence/) | 3 |
| 20 | [Plugin Management](Skills/20_Plugin_Management/) | 2 |
| 21 | [D3.js Visualization](Skills/21_D3js_Skills/) | 4 |
| 22 | [Erickson Group Brand Guidelines](Skills/22_EricksonGroup_BrandGuidelines/) | 1 |
| 23 | [Google Stitch Skills](Skills/23_GoogleStitch_Skills/) | 40 |

**Total: 23 categories, 188 skill reference files**

### Additional Skill Resources

| Resource | Link |
|----------|------|
| What Are Skills | [Overview](Skills/Overview/what-are-skills.mdx) |
| Installable Skill Bundles (Zip) | [XX_ZipFolders](Skills/XX_ZipFolders/) |
| Investment Analysis Skill (Series A) | [skill_investment_analysis.md](Skills/15_Investment_Banking/skill_investment_analysis.md) |
| Personal Finance Skill (Series B) | [skill_personal_finance.md](Skills/14_Financial_Analysis/skill_personal_finance.md) |

---

## Hooks

Claude Code hook examples — see [`Hooks/`](Hooks/).

---

## Plugins

Claude Code plugin examples — see [`Plugins/`](Plugins/).

---

## Use Cases

Domain-specific workflow examples — see [`Use Cases/`](Use%20Cases/).

| Domain | Link |
|--------|------|
| Design | [Use Cases/Design/](Use%20Cases/Design/) |
| Finance | [Use Cases/Finance/](Use%20Cases/Finance/) |
| Operations | [Use Cases/Operations/](Use%20Cases/Operations/) |
| Project Management | [Use Cases/Project Management/](Use%20Cases/Project%20Management/) |
| Software Development | [Use Cases/Software Development/](Use%20Cases/Software%20Development/) |

---

## Resources

Curated external link collections by platform.

| Resource | Link | Status |
|----------|------|--------|
| Claude | [ClaudeResources.md](Resources/Claude/ClaudeResources.md) | Active |
| Stitch | [StitchResources.md](Resources/Stitch/StitchResources.md) | Placeholder |
| Gemini | [GeminiResources.md](Resources/Gemini/GeminiResources.md) | Placeholder |
| Obsidian | [ObsidianResources.md](Resources/Obsidian/ObsidianResources.md) | Placeholder |
| Flow | [FlowResources.md](Resources/Flow/FlowResources.md) | Placeholder |

---

#claude #ai #para/area #status/active