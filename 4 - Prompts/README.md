---
title: Prompts
description: Text prompt templates organized by domain. Each prompt uses [BRACKETED FIELDS] as fill-in-the-blank placeholders.
created: 2026-04-07
updated: 2026-04-16
topics: [prompts, claude, ai, finance, design, excel, powerpoint, data-analysis, document-generation]
---

# Prompts

Reusable text prompt templates organized by domain. Drop them into Claude (or any LLM) after replacing the `[BRACKETED FIELDS]` placeholders with your own values.

> Looking for image, video, or visualization prompts instead? See [`8 - Prompts/`](../8%20-%20Prompts/).

## How to use

1. Open the prompt file for your task.
2. Copy the full prompt body.
3. Replace every `[BRACKETED FIELD]` with your specific input (company name, ticker, date range, etc.).
4. Paste into Claude. For long, multi-section prompts, paste into a fresh conversation so the system has full context.

## Contents

| Domain | Folder | Description |
|--------|--------|-------------|
| Data Analysis | [Data Analysis/](Data%20Analysis/) | Prompts for exploratory analysis, statistical workflows, dataset Q&A |
| Design | [Design/](Design/) | Diagram generation, visual layout, design critique prompts |
| Document Generation | [Document Generation/](Document%20Generation/) | Long-form document drafting and structured writing prompts |
| Excel | [Excel/](Excel/) | Spreadsheet workflows, including [Financial Modelling/](Excel/Financial%20Modelling/) (Three-Statement Model) |
| Finance | [Finance/](Finance/) | 20 institutional-grade finance prompts (see [Finance/README.md](Finance/README.md)) |
| PowerPoint | [PowerPoint/](PowerPoint/) | Slide structuring, deck-quality, presentation outlines |

## Finance prompt series

Two ten-prompt series modeled after major institutions live in [`Finance/Insitutional Finance/`](Finance/Insitutional%20Finance/):

- **Series A — Investment & Trading Analysis** (01–10): Stock Screener, DCF, Risk, Earnings, Portfolio, Technical, Dividend, Competitive Advantage, Pattern Finder, Macro Impact.
- **Series B — Personal Finance & Wealth Planning** (11–20): Wealth Diagnostic, Retirement, Portfolio Architect, Tax Optimization, Debt Elimination, Emergency Fund, Insurance Audit, College Savings, Estate Planning, Real Estate.

Both series are also packaged as installable skill bundles — see [`5 - Skills/15_Investment_Banking/skill_investment_analysis.md`](../5%20-%20Skills/15_Investment_Banking/skill_investment_analysis.md) and [`5 - Skills/14_Financial_Analysis/skill_personal_finance.md`](../5%20-%20Skills/14_Financial_Analysis/skill_personal_finance.md).
