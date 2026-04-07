# What is DESIGN.md?

**Source**: Google Stitch - Docs  
**Purpose**: A design system document that AI agents read to generate consistent UI across your project

---

## Overview

Every project has a visual identity: colors, fonts, spacing, component styles. Traditionally, this lives in a Figma file, a brand PDF, or a designer's head. None of these are readable by an AI agent.

DESIGN.md changes that. It's a plain-text design system document that both humans and agents can read, edit, and enforce. Think of it as the design counterpart to AGENTS.md:

| File | Who reads it | What it defines |
|------|-------------|-----------------|
| README.md | Humans | What the project is |
| AGENTS.md | Coding agents | How to build the project |
| DESIGN.md | Design agents | How the project should look and feel |

---

## What It Gives You

When a design agent like Stitch reads your DESIGN.md, every screen it generates follows the same visual rules: your color palette, your typography, your component patterns. Without it, each screen stands alone. With it, they look like they belong together.

DESIGN.md is a living artifact, not a static config file. It evolves as your design evolves. The agent generates it, you refine it, and it's re-applied to screens as you iterate.

---

## How They're Created

There are three paths to a DESIGN.md, from effortless to precise.

### 1. Let the Agent Generate It

Describe the vibe. The agent translates your aesthetic intent into tokens and guidelines.

```
PROMPT: "A playful coffee shop ordering app with warm colors, rounded corners, 
and a friendly feel."
```

Stitch generates a complete design system (colors, typography, spacing, component styles) and summarizes it as a DESIGN.md.

### 2. Derive from Branding

If you already have a brand, provide a URL or image. The agent extracts your palette, typography, and style patterns to build the DESIGN.md from what already exists.

### 3. Write It by Hand

Advanced users can author a DESIGN.md directly, encoding exact design preferences. Every section is just markdown. No special syntax, no tooling required.

---

## Example

Below is a minimal DESIGN.md for a dark-themed productivity app:

```markdown
# Design System

## Overview
A focused, minimal dark interface for a developer productivity tool.
Clean lines, low visual noise, high information density.

## Colors
- **Primary** (#2665fd): CTAs, active states, key interactive elements
- **Secondary** (#475569): Supporting UI, chips, secondary actions
- **Surface** (#0b1326): Page backgrounds
- **On-surface** (#dae2fd): Primary text on dark backgrounds
- **Error** (#ffb4ab): Validation errors, destructive actions

## Typography
- **Headlines**: Inter, semi-bold
- **Body**: Inter, regular, 14-16px
- **Labels**: Inter, medium, 12px, uppercase for section headers

## Components
- **Buttons**: Rounded (8px), primary uses brand blue fill
- **Inputs**: 1px border, subtle surface-variant background
- **Cards**: No elevation, relies on border and background contrast

## Do's and Don'ts
- Do use the primary color sparingly, only for the most important action
- Don't mix rounded and sharp corners in the same view
- Do maintain 4:1 contrast ratio for all text
```

This is what the agent reads when generating your next screen.
