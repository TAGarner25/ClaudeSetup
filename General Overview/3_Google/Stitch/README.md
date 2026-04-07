---
title: Google Stitch - Complete Guide
description: A comprehensive overview of Google's AI-native UI design platform that turns natural language, sketches, and images into high-fidelity interface designs and production-ready frontend code.
created: 2026-04-06
updated: 2026-04-06
topics:
  - Google
  - AI
  - UI Design
  - Frontend Development
  - Prototyping
  - Design Systems
  - Stitch
---

# Google Stitch — Complete Guide

> **What it is**: An AI-native UI design platform from Google Labs that turns natural language, sketches, and images into high-fidelity interface designs and production-ready frontend code — entirely in the browser.
>
> **URL**: [stitch.withgoogle.com](https://stitch.withgoogle.com)
>
> **Cost**: Free (Google Labs experiment). No waitlist, no subscription. Sign in with any Google account.

---

## Table of Contents

- [[#Background and Origin]]
- [[#What Stitch Does]]
- [[#AI Modes]]
- [[#Step-by-Step Workflow]]
- [[#Key Concepts]]
- [[#The DESIGN.md Format]]
- [[#Export Options]]
- [[#MCP Integration (Design-to-Code)]]
- [[#Stitch Skills]]
- [[#Strengths]]
- [[#Weaknesses and Limitations]]
- [[#Alternatives and Competitors]]
- [[#Prompting Tips]]
- [[#Pricing and Limits]]
- [[#Who Should Use Stitch]]
- [[#Files in This Folder]]
- [[#Further Reading]]

---

## Background and Origin

Google acquired **Galileo AI** (a startup founded in 2022 by Arnaud Benard and Helen Zhou) in early 2025. The technology was rebranded as **Stitch**, integrated with Google's Gemini models, and publicly launched at **Google I/O on May 20, 2025** as a Google Labs experiment.

A major update in **March 2026** introduced an AI-native infinite canvas, voice interaction, an agent manager for parallel tasks, and new AI modes — sometimes referred to informally as "Stitch 2.0."

Stitch remains an experimental Labs product as of April 2026 — actively developed, free to use, and subject to change.

---

## What Stitch Does

Stitch generates complete, high-fidelity UI layouts from various inputs:

| Input Method | Description |
|---|---|
| **Text prompts** | Describe what you want in natural language |
| **Image uploads** | Upload wireframes, screenshots, or sketches (Experimental mode) |
| **Voice commands** | Speak to the canvas for real-time design critiques and updates (March 2026+) |
| **URL extraction** | Pull design system values from any live website |

From these inputs, Stitch produces:

- Pixel-level UI designs for mobile and web
- Multiple variant options from a single prompt
- Multi-page interactive prototypes with screen-to-screen transitions
- Exportable HTML/CSS/TailwindCSS code
- One-click Figma exports with preserved layers

Stitch is *not* a full-stack builder — it generates **static UI designs and frontend markup**, not functional applications with backend logic, databases, or authentication.

---

## AI Modes

Stitch offers several generation modes, each powered by different Gemini models:

| Mode | Model | Best For | Limit |
|---|---|---|---|
| **Ideate** | — | Early exploration when you don't know what you want | Shared with Standard |
| **Flash** (Standard) | Gemini 2.5 Flash | Fast generation when you know what you're building | ~350/month |
| **Thinking** | Gemini 2.5 Pro | Higher-quality output for final polish | Shared with Experimental |
| **Redesign** | — | Transforming existing designs | — |
| **Experimental** | Gemini 2.5 Pro | Cutting-edge features (image input, etc.) | ~200/month |

**Practical guidance**: Start with **Ideate** or **Flash** for rapid exploration, then switch to **Thinking** for the screens you plan to export. Reserve **Experimental** for image-to-design workflows.

---

## Step-by-Step Workflow

### 1. Create a Project
Sign in at [stitch.withgoogle.com](https://stitch.withgoogle.com) and click **New Project**. Projects are containers that hold screens and a shared design system.

### 2. Choose an AI Mode
Pick based on your stage — Ideate for exploration, Flash for speed, Thinking for quality.

### 3. Write a Prompt
Be specific. Compare:
- Weak: *"A dashboard"*
- Strong: *"A B2B analytics dashboard with a dark sidebar, card-based KPI layout at the top, a line chart for revenue trends in the center, and a sortable data table below. Use Inter font, blue primary color (#2665fd), and 8px corner radius."*

Include: purpose, layout structure, components, styling, content type, and branding.

### 4. Generate and Review
Stitch produces the UI in seconds. Review the output and note what needs adjustment.

### 5. Iterate via Chat
Refine with follow-up prompts:
- *"Make the sidebar narrower"*
- *"Switch to a light theme"*
- *"Add a notifications panel in the top-right"*
- *"Replace the bar chart with a line chart"*

### 6. Set Up a Design System
Select screen(s) > click **Modify** > choose **Design System**. Options:
- **Theme**: Create a color palette from scratch
- **DESIGN.md**: Import or create custom design rules (see [[#The DESIGN.md Format]])
- **URL extraction**: Pull design tokens from any live website

### 7. Generate More Screens
Subsequent screens automatically inherit the design system, ensuring visual consistency across the project.

### 8. Connect Screens
Create interactive prototypes by linking screens with transitions — useful for stakeholder demos and usability testing.

### 9. Export
Choose your output path (see [[#Export Options]]).

**Total time for an initial prototype**: 5–15 minutes.

---

## Key Concepts

### Projects
Top-level containers. Each project holds multiple screens and one design system.

### Screens
Individual pages or views. Can be generated independently and later connected into flows with transitions.

### Design Systems
Reusable visual rules (colors, typography, spacing, components) that enforce consistency across all screens in a project. Three ways to create one:
1. **Manually** — describe it in a prompt or configure via the UI
2. **URL extraction** — point Stitch at a live website
3. **DESIGN.md import** — upload a markdown file with design tokens

### Variants
Multiple alternative designs generated from a single prompt. Use these to explore different directions before committing.

### Agent Manager (March 2026+)
Tracks progress across multiple parallel design tasks on the infinite canvas. Useful when generating several screens or flows simultaneously.

---

## The DESIGN.md Format

DESIGN.md is a plain markdown file that stores your brand's design tokens as persistent context. Stitch reads it every time it generates a UI, applying your specific values without re-specification.

See [[stitch-design-md-format]] for the full specification. Summary of sections:

| Section | Purpose |
|---|---|
| **Overview** | Personality and look/feel ("calm, professional, accessibility-first") |
| **Colors** | Primary, secondary, tertiary, neutral palettes with hex values and roles |
| **Typography** | Font families, hierarchy (display → label), weights, sizes |
| **Elevation** | Shadow properties or flat design specification |
| **Components** | Style guidance for buttons, inputs, cards, chips, etc. |
| **Do's and Don'ts** | Guardrails and common pitfalls |

**Dual representation**: The markdown you edit is one side. Stitch also maintains structured tokens underneath (hex values, font enums, spacing scales). You can be approximate (*"warm colors, rounded feel"*) or exact (*#2665fd, 8px radius*) — Stitch reconciles both.

### Example Minimal DESIGN.md

```markdown
## Overview
A clean, modern SaaS dashboard. Professional but approachable.
Generous whitespace, clear hierarchy, accessible contrast ratios.

## Colors
- **Primary** (#2665fd): CTAs, active states, key interactive elements
- **Secondary** (#6074b9): Supporting actions, chips, toggle states
- **Neutral** (#757681): Backgrounds, surfaces, non-chromatic UI

## Typography
- **Headline Font**: Inter (semi-bold)
- **Body Font**: Inter (regular, 14-16px)
- **Label Font**: Inter (medium, 12px, uppercase for section headers)

## Elevation
No shadows. Depth conveyed through border contrast and surface color variation.

## Components
- **Buttons**: Rounded (8px), primary uses brand blue fill, secondary uses outline
- **Inputs**: 1px border, surface-variant background, 12px padding
- **Cards**: No elevation, 1px outline border, 12px corner radius

## Do's and Don'ts
- Do use the primary color only for the single most important action per screen
- Don't mix rounded and sharp corners in the same view
- Do maintain WCAG AA contrast ratios (4.5:1 for normal text)
```

---

## Export Options

| Destination | How | Notes |
|---|---|---|
| **Figma** | One-click "Copy to Figma" button, Ctrl/Cmd+V to paste | Preserves layers and components. Standard mode only (not available in Experimental) |
| **HTML/CSS/TailwindCSS** | Download ZIP or copy to clipboard | Production-quality markup. Only web languages — no SwiftUI, React Native, or Flutter |
| **Google AI Studio** | One-click export | Instantly host a live preview |
| **Antigravity** | One-click export | Google's deployment tool |
| **Shareable Prototype** | Generate a public preview URL | For stakeholder demos |
| **DESIGN.md** | Export/import | Portable design system for use across projects or with MCP agents |

---

## MCP Integration (Design-to-Code)

Stitch exposes an **MCP server** that connects your designs directly to coding agents (Claude Code, Cursor, Gemini CLI) via the Model Context Protocol.

### Setup

Add to your MCP configuration (e.g., `.mcp.json` or Claude Code settings):

```json
{
  "mcpServers": {
    "stitch": {
      "command": "npx",
      "args": ["@_davideast/stitch-mcp", "proxy"]
    }
  }
}
```

### Available MCP Tools

| Tool | Purpose |
|---|---|
| `list_projects` | List all Stitch projects |
| `get_project` | Get project details |
| `list_screens` | List screens in a project |
| `get_screen` | Get a specific screen's details |
| `generate_screen_from_text` | Generate a new screen from a text prompt |
| `edit_screens` | Edit existing screens |
| `generate_variants` | Generate design variants |
| `create_project` | Create a new project |
| `list_design_systems` | List available design systems |
| `create_design_system` | Create a new design system |
| `update_design_system` | Update an existing design system |
| `apply_design_system` | Apply a design system to screens |

### Workflow Example

With MCP configured, you can prompt Claude Code:

> *"Use Stitch to generate a login screen and a dashboard for a fitness tracking app, then export the HTML and build a Next.js project from it."*

The agent calls Stitch's MCP tools to generate the designs, downloads the code, and scaffolds your project — no copy-pasting between browser tabs.

---

## Stitch Skills

Google provides an open-source **Stitch Skills** library ([google-labs-code/stitch-skills](https://github.com/google-labs-code/stitch-skills)) — agent skills compatible with Claude Code, Cursor, and Gemini CLI:

| Skill | Purpose |
|---|---|
| **stitch-design** | Unified entry point for design work, prompt enhancement, design system synthesis |
| **stitch-loop** | Generates complete multi-page websites from a single prompt |
| **design-md** | Analyzes projects and produces comprehensive DESIGN.md documentation |
| **enhance-prompt** | Transforms basic concepts into polished, Stitch-optimized prompts |
| **react-components** | Converts Stitch screens into React component systems |
| **remotion** | Creates walkthrough videos from Stitch projects |
| **shadcn-ui** | Integrates shadcn/ui components into Stitch-generated designs |

### Install a Skill

```bash
npx skills add google-labs-code/stitch-skills --skill stitch-design --global
```

---

## Strengths

- **Speed**: Complete UI layouts in seconds, full prototypes in minutes
- **Zero friction**: No installation, no downloads, no learning curve, no cost
- **Clean code output**: Production-quality HTML/CSS/TailwindCSS that you can actually ship
- **Figma integration**: One-click export with preserved layers — fits into existing design workflows
- **Design system enforcement**: DESIGN.md ensures every screen follows the same visual rules automatically
- **Multi-modal input**: Text, images, voice, URLs — meet users where they are
- **MCP pipeline**: Seamless design-to-code via coding agents — the most developer-friendly AI design tool
- **Infinite canvas** (March 2026+): Room for ideas to grow from napkin sketch to full prototype
- **Eliminates blank-canvas paralysis**: Generate a starting point and refine, rather than building from nothing

---

## Weaknesses and Limitations

- **Static designs only**: No functional logic, live components, animations, or advanced interactions — it produces mockups, not apps
- **Generic output without specific prompts**: Vague prompts produce vague designs. You must invest in prompt quality
- **Limited precision control**: Natural language is inherently imprecise — *"move it up slightly"* may not do what you mean. No pixel-level control
- **Image input inconsistency**: Sketch-to-design (Experimental mode) can struggle to interpret wireframes, sometimes asking you to describe them in text instead
- **No real-time collaboration**: Single-user tool — no commenting, multi-user editing, or team features
- **Export format limitations**: HTML/TailwindCSS only — no React, SwiftUI, React Native, Flutter, or Compose output. Figma export unavailable in Experimental mode
- **Spacing and alignment issues**: Generated layouts often need manual refinement
- **Placeholder content**: Icons and labels sometimes appear as generic placeholders rather than contextual content
- **Generation caps**: ~550 total generations/month (350 standard + 200 experimental) — can run out during heavy exploration
- **Experimental status**: Features change, things break, nothing is guaranteed long-term

---

## Alternatives and Competitors

| Tool | Best For | How It Differs from Stitch |
|---|---|---|
| **Vercel v0** | Production React/Next.js components | Developer-focused; outputs real React code but locked to React/Next.js ecosystem. Better for production code, worse for exploration |
| **Bolt** | Rapid full-stack prototypes | Full-stack builder (frontend + backend), not just UI. Faster iteration, especially for mobile |
| **Lovable** | Non-technical builders wanting working apps | Full-stack from idea to deployed product. More capability, less design focus |
| **Figma** (+ Figma AI) | Professional design teams | Industry standard with superior precision, collaboration, design systems, and plugin ecosystem. Stitch is faster; Figma is more capable |
| **UXPin** | Interactive prototyping | Conditional logic, advanced interactions, and deeper prototyping features than Stitch |
| **Framer** | Marketing sites with design polish | Better animations, interactions, and CMS integration. More polished output |

### When to Use What

- **Exploring ideas fast?** Stitch
- **Need production React code?** v0
- **Building a full working app without coding?** Lovable or Bolt
- **Professional design team workflow?** Figma
- **Marketing site with animations?** Framer
- **Stitch + Figma together**: Use Stitch for rapid ideation, export to Figma for refinement and handoff

---

## Prompting Tips

Good prompts are the single biggest lever for quality output in Stitch. Structure them around:

1. **Purpose**: What is this screen for? (*"A settings page for a SaaS project management tool"*)
2. **Layout**: How should elements be arranged? (*"Left sidebar navigation, main content area with tabs"*)
3. **Components**: What specific UI elements? (*"Data table with sortable columns, search bar, pagination"*)
4. **Styling**: Visual direction (*"Dark theme, blue accents, Inter font, 8px border radius"*)
5. **Content**: What data or text should appear? (*"Show 5 rows of sample project data with status badges"*)
6. **Branding**: Colors, fonts, personality (*"Professional but approachable, similar to Linear's aesthetic"*)

### Example Prompts

**Weak**: *"Make a dashboard"*

**Strong**: *"A project management dashboard with a dark sidebar showing navigation (Projects, Tasks, Calendar, Settings). Main area has a greeting header with the user's name, 4 KPI cards (tasks completed, overdue, in progress, team members), a Gantt chart preview, and a recent activity feed. Use a dark theme with #1a1a2e background, #6c63ff primary accent, Inter font, and 12px corner radius on cards."*

**Iterating**: After initial generation, refine with targeted follow-ups:
- *"Add a notification bell icon with a red badge showing '3' in the top bar"*
- *"Make the KPI cards use a gradient background from #1e1e3f to #2a2a4f"*
- *"The sidebar should collapse to icons only on mobile"*

---

## Pricing and Limits

### Current (April 2026)
Completely **free**. No paid tiers, no credit card required.

| Mode | Monthly Limit |
|---|---|
| Standard (Gemini 2.5 Flash) | ~350 generations |
| Experimental (Gemini 2.5 Pro) | ~200 generations |
| **Total** | **~550 generations** |

### Expected Future Pricing
Analyst predictions suggest eventual tiered pricing:
- **Free tier**: Likely to remain with reduced limits (~50–100 standard generations/month)
- **Paid tier**: Expected ~$10–15/month (positioned below Figma's $15/editor/month)
- **Enterprise**: Custom pricing with team management, SSO, priority support

---

## Who Should Use Stitch

### Ideal Users
- **Solo founders and startup teams** — rapid MVP prototyping without hiring a designer
- **Frontend developers** — quick UI scaffolding before writing code
- **Product managers** — visualize concepts for stakeholder alignment
- **Designers** — rapid ideation before moving to Figma for refinement
- **Developers using MCP workflows** — design-to-code pipelines via Claude Code or Cursor
- **Non-designers** — anyone who needs a UI but doesn't know Figma

### Less Suitable For
- Complex design systems requiring pixel-perfect precision
- Projects needing animations, micro-interactions, or complex state management
- Large collaborative design teams needing real-time co-editing
- Native mobile development (no SwiftUI, React Native, Flutter, or Compose export)
- Brand-heavy projects without willingness to set up DESIGN.md

---

## Files in This Folder

| File | Description |
|---|---|
| `README.md` | This guide — comprehensive overview of Google Stitch |
| [[stitch-design-md-format]] | Detailed specification of the DESIGN.md format: sections, tokens, dual representation, and examples |

**Related resources**: See [[StitchResources]] in the Resources folder for curated links.

---

## Further Reading

- [Official Stitch site](https://stitch.withgoogle.com) — the tool itself
- [Google Blog announcement](https://blog.google/innovation-and-ai/models-and-research/google-labs/stitch-ai-ui-design/) — launch post from Google I/O 2025
- [Google Developers Blog](https://developers.googleblog.com/stitch-a-new-way-to-design-uis/) — technical deep dive
- [Stitch MCP server](https://github.com/davideast/stitch-mcp) — MCP integration source code
- [Stitch Skills library](https://github.com/google-labs-code/stitch-skills) — official agent skills
- [Stitch Docs: DESIGN.md](https://stitch.withgoogle.com/docs/design-md/overview/) — official DESIGN.md documentation
- [Stitch Docs: MCP setup](https://stitch.withgoogle.com/docs/mcp/setup/) — official MCP configuration guide
- [Codecademy tutorial](https://www.codecademy.com/article/google-stitch-tutorial-ai-powered-ui-design-tool) — step-by-step beginner walkthrough
