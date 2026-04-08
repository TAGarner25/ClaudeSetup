# The DESIGN.md Format

**Source**: Google Stitch - Docs  
**Purpose**: The sections, tokens, and structure of a DESIGN.md file

---

## Overview

A DESIGN.md file has two faces. The markdown is what you read and edit — a human-friendly summary of your design system. Underneath, Stitch maintains structured tokens, the precise values it uses to enforce consistency during generation.

This page documents what goes in the markdown.

---

## Sections

Every DESIGN.md follows the same structure. Sections can be omitted if they're not relevant to your project, but the order should be preserved.

---

### Overview

A holistic description of the design's look and feel. This is where you describe the personality: is it playful or professional? Dense or spacious? This section guides the agent's high-level decisions when no specific token applies.

```markdown
## Overview
A calm, professional interface for a healthcare scheduling platform.
Accessibility-first design with high contrast and generous touch targets.
```

---

### Colors

The primary, secondary, tertiary, and neutral palettes. Each color should include its hex value and its role describing what the agent should use it for.

```markdown
## Colors
- **Primary** (#2665fd): CTAs, active states, key interactive elements
- **Secondary** (#6074b9): Supporting actions, chips, toggle states
- **Tertiary** (#bd3800): Accent highlights, badges, decorative elements
- **Neutral** (#757681): Backgrounds, surfaces, non-chromatic UI
```

The agent also generates named colors from these base values: surface, on-primary, error, outline, and dozens more. These follow Material color role conventions and are available in the structured tokens.

---

### Typography

The font families and their roles across the typographic hierarchy: display, headline, title, body, and label levels.

```markdown
## Typography
- **Headline Font**: Inter
- **Body Font**: Inter
- **Label Font**: Inter

Headlines use semi-bold weight. Body text uses regular weight at 14-16px.
Labels use medium weight at 12px with uppercase for section headers.
```

The relationship between headline and body fonts matters. Using the same family (like Inter) conveys uniformity. Mixing families (e.g., a serif headline with a sans-serif body) creates visual contrast the agent will intentionally carry through.

---

### Elevation

How the design conveys depth and hierarchy. Some designs use shadows; others stay flat.

```markdown
## Elevation
This design uses no shadows. Depth is conveyed through border contrast
and surface color variation (surface, surface-container, surface-bright).
```

If elevation is used, specify the shadow properties (spread, blur, color) and which components should be elevated.

---

### Components

Style guidance for component atoms. Focus on the components most relevant to your application.

| Component | What to specify |
|-----------|----------------|
| Buttons | Variants (primary, secondary, tertiary), sizing, padding, corner radius, states |
| Chips | Selection, filter, and action variants |
| Lists | Item styling, dividers, leading/trailing elements |
| Inputs | Text fields, text areas, labels, helper text, error states |
| Checkboxes | Checked, unchecked, indeterminate states |
| Radio buttons | Selected and unselected states |
| Tooltips | Positioning, colors, timing |

```markdown
## Components
- **Buttons**: Rounded (8px), primary uses brand blue fill, secondary uses outline
- **Inputs**: 1px border, surface-variant background, 12px padding
- **Cards**: No elevation, 1px outline border, 12px corner radius
```

You can suggest components based on your project's context. For example, a navigation bar for a mobile app or a data table for a dashboard.

---

### Do's and Don'ts

Practical guidelines and common pitfalls. These act as guardrails when creating designs.

```markdown
## Do's and Don'ts
- Do use the primary color only for the single most important action per screen
- Don't mix rounded and sharp corners in the same view
- Do maintain WCAG AA contrast ratios (4.5:1 for normal text)
- Don't use more than two font weights on a single screen
```

---

## The Dual Representation

The markdown you see is one side. Stitch also stores a structured version of the same information: hex values, font enums, spacing scales, and the full named color palette. When you edit the markdown, Stitch reconciles both representations.

This means you can be approximate in the markdown ("warm colors, rounded feel") and Stitch will translate that into precise tokens. Or you can be exact (#2665fd, 8px radius) and Stitch will respect those values literally.

Both representations describe the same design system. The markdown is for collaboration. The tokens are for enforcement.
