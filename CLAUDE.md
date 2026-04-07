# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a **reference and resource repository** for Claude AI tooling — not a software project. It contains no build system, tests, or runnable code. It is a knowledge base synced to Obsidian (note the `[[wikilink]]` syntax throughout) and organized around the Claude ecosystem.

## Repository Structure

```
ClaudeSetup/
├── README.md                          ← Master index (Obsidian MOC)
├── General Overview/                  ← Beginner-to-power-user setup guides
├── Prompts/Finance/                   ← 20 institutional finance prompts (.txt)
├── Resources/                         ← Curated external link collections
│   ├── ClaudeResources.md             ← Primary Claude reference hub
│   ├── GeminiResources.md
│   ├── ObsidianResources.md
│   ├── StitchResources.md
│   └── FlowResources.md
└── Skills/
    ├── skill_investment_analysis.md   ← Series A: 10 investment analysis prompts
    ├── skill_personal_finance.md      ← Series B: 10 personal finance prompts
    └── Skill Files/                   ← Reference docs for 20 skill categories
        ├── 01_Document_Creation/ through 20_Plugin_Management/
        ├── claude-d3js-skill-main/    ← Third-party D3.js visualization skill
        ├── stitch-skills-main/        ← Google Labs Stitch MCP skill library
        └── Zip Folders/               ← Packaged/installable skill bundles
```

## Content Conventions

- **Obsidian wikilinks** (`[[filename]]`) are used throughout for internal navigation — these are not broken links, they're intentional Obsidian syntax.
- **Skill Files** (`Skills/Skill Files/`) are reference documentation only — they describe what installed skills do, not the skills themselves. Actual skill installation happens via Claude's plugin/Cowork interfaces.
- **Finance prompts** use `[BRACKETED FIELDS]` as fill-in-the-blank placeholders the user replaces before submitting to Claude.
- All `.md` files use YAML frontmatter tags (`para/area`, `status/active`, etc.) following an Obsidian PARA system.

## Prompt Series

**Series A — Investment Analysis** (`Skills/skill_investment_analysis.md`): Goldman Sachs Stock Screener, DCF Valuation, Risk Analysis, Earnings Breakdown, Portfolio Construction, Technical Analysis, Dividend Strategy, Competitive Advantage, Pattern Recognition, Macro Impact.

**Series B — Personal Finance** (`Skills/skill_personal_finance.md`): Wealth Diagnostic, Retirement Planning, Portfolio Architecture, Tax Optimization, Debt Elimination, Emergency Fund/Cash Strategy, Insurance Audit, College Savings, Estate Planning, Real Estate Analysis.

Individual `.txt` versions of these prompts live in `Prompts/Finance/`.

## Skill Categories (20 total, 141 reference files)

Categories 01–12 cover general business (Document Creation, Sales, Product Management, Legal, Operations, Brand Voice, Finance/Accounting, Data Analytics, Marketing, Productivity, Engineering, Design). Categories 13–20 are finance-specific (Equity Research, Financial Analysis, Investment Banking, Private Equity, Wealth Management, LSEG Fixed Income, S&P Global Market Intelligence, Plugin Management).

## Third-Party Libraries

- `Skills/Skill Files/claude-d3js-skill-main/` — D3.js interactive visualization skill with chart templates and color/scale references
- `Skills/Skill Files/stitch-skills-main/` — Google Labs Stitch MCP skills: design-md, prompt enhancement, React components, Remotion video, shadcn/ui, Stitch design/loop workflows
