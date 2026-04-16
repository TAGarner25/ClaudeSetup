# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **reference and resource repository** for Claude AI tooling — not a software project. It contains no build system, tests, or runnable code. It is a knowledge base synced to Obsidian (note the `[[wikilink]]` syntax throughout) and organized around the Claude ecosystem.

## Repository Structure

Top-level folders use a numeric prefix (`0 - News/`, `1 - General Overview/`, …) for ordering in Obsidian. Always reference them by their full prefixed names.

```
ClaudeSetup/
├── README.md                          ← Master index (Obsidian MOC)
├── 0 - News/                          ← AI news feed + archive
├── 1 - General Overview/
│   ├── 1_Setup/                       ← Installation & configuration guides (incl. .pptx)
│   ├── 2_Anthropic/                   ← Claude product deep-dives
│   │   ├── Claude Chat/
│   │   ├── Claude Code/
│   │   ├── Claude Computer Use/
│   │   ├── Claude Cowork/
│   │   ├── Claude Desktop/
│   │   ├── Claude For Excel/
│   │   ├── Claude For PowerPoint/
│   │   └── Claude Projects/
│   ├── 3_Google/                      ← Google AI product overview (Gemini, Stitch)
│   └── 4_Use Cases/                   ← Domain-specific workflow examples (Finance, etc.)
├── 2 - Resources/                     ← Curated external link collections by platform
│   ├── 0_OtherTools/
│   ├── Claude/
│   ├── Flow/
│   ├── Gemini/
│   ├── Nano Banana/
│   ├── NotebookLM/
│   ├── Obsidian/
│   └── Stitch/
├── 3 - Cheat Sheets/                  ← Quick-reference guides
├── 4 - Prompts/                       ← Text prompt templates by domain
│   ├── Data Analysis/
│   ├── Design/
│   ├── Document Generation/
│   ├── Excel/                         ← Financial Modelling/
│   ├── Finance/                       ← Insitutional Finance/ (20 prompts)
│   └── PowerPoint/
├── 5 - Skills/                        ← Skill reference docs & prompt series
│   ├── 01_Document_Creation/ through 20_Plugin_Management/  ← 20 skill categories
│   ├── 21_D3js_Skills/                ← D3.js visualization skill (third-party)
│   ├── 22_EricksonGroup_BrandGuidelines/
│   ├── 23_GoogleStitch_Skills/        ← Google Stitch MCP skills
│   ├── Overview/                      ← What skills are & how they work
│   └── XX_ZipFolders/                 ← Packaged/installable skill bundles
├── 6 - Plugins/                       ← Claude Code plugin examples
├── 7 - Hooks/                         ← Claude Code hook examples + Examples/
├── 8 - Prompts/                       ← Media-generation prompts (distinct from 4 - Prompts)
│   ├── Images/
│   ├── Meta/
│   ├── Security/
│   ├── Videos/
│   └── Visualizations/
└── Todo/                              ← Repository TODO list and Instagram backlog
```

## Content Conventions

- **Obsidian wikilinks** (`[[filename]]`) are used throughout for internal navigation — these are not broken links, they're intentional Obsidian syntax.
- **YAML frontmatter** — all `.md` files use frontmatter with `title`, `description`, `created`, `updated`, and `topics` fields.
- **New files** — when creating content, always include YAML frontmatter. Use `README.md` as the index file for any new directory. Place text prompts in `4 - Prompts/<Domain>/`, media prompts in `8 - Prompts/<Domain>/`, use cases in `1 - General Overview/4_Use Cases/<Domain>/`, and skill docs in the appropriate `5 - Skills/##_*` folder.
- **Skill categories** (`5 - Skills/01_*` through `5 - Skills/20_*`) are reference documentation only — they describe what installed skills do. Actual skill installation happens via Claude's plugin/Cowork interfaces.
- **Prompts** use `[BRACKETED FIELDS]` as fill-in-the-blank placeholders the user replaces before submitting to Claude.
- Date format in frontmatter: `MM/DD/YYYY` or `YYYY-MM-DD` (both are used; prefer `YYYY-MM-DD` for new content).
- **Two prompt folders**: `4 - Prompts/` is for text/document prompts (finance, Excel, PowerPoint, design). `8 - Prompts/` is for media-generation prompts (images, videos, visualizations).

## Prompt Series

**Series A — Investment Analysis** (`5 - Skills/15_Investment_Banking/skill_investment_analysis.md`): Goldman Sachs Stock Screener, DCF Valuation, Risk Analysis, Earnings Breakdown, Portfolio Construction, Technical Analysis, Dividend Strategy, Competitive Advantage, Pattern Recognition, Macro Impact.

**Series B — Personal Finance** (`5 - Skills/14_Financial_Analysis/skill_personal_finance.md`): Wealth Diagnostic, Retirement Planning, Portfolio Architecture, Tax Optimization, Debt Elimination, Emergency Fund/Cash Strategy, Insurance Audit, College Savings, Estate Planning, Real Estate Analysis.

Individual `.md` versions of these prompts live in `4 - Prompts/Finance/Insitutional Finance/`.

## Skill Categories (23 total)

Categories 01–12 cover general business (Document Creation, Sales, Product Management, Legal, Operations, Brand Voice, Finance/Accounting, Data Analytics, Marketing, Productivity, Engineering, Design). Categories 13–20 are finance-specific (Equity Research, Financial Analysis, Investment Banking, Private Equity, Wealth Management, LSEG Fixed Income, S&P Global Market Intelligence, Plugin Management). Categories 21–23 are third-party integrations (D3.js, Erickson Group Brand Guidelines, Google Stitch).

## General Overview Content

`1 - General Overview/2_Anthropic/README.md` is the main Anthropic Claude reference (models, features, comparisons). Each subdirectory under `2_Anthropic/` has a dedicated guide per Claude product.

## Environment

- **Platform**: Windows 11 — Claude Code uses bash shell (Unix syntax), but native tools use backslash paths.
- **No runnable code** — no `npm`, `pip`, or build commands apply. All work is content authoring/editing.
