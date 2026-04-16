---
title: Media-Generation Prompts
description: Prompts for image, video, and visualization generation tools (Nano Banana, Veo, Sora, etc.). Distinct from `4 - Prompts/`, which is for text prompts.
created: 2026-04-16
updated: 2026-04-16
topics: [prompts, images, videos, visualizations, media, nano-banana, veo, sora]
---

# Media-Generation Prompts

Prompt templates aimed at **media generation** — image, video, and visualization tools. Text-only prompt templates live in [`4 - Prompts/`](../4%20-%20Prompts/).

## Folders

| Folder | Tools / formats | Status |
|--------|-----------------|--------|
| [Images/](Images/) | Nano Banana, Imagen, Midjourney, DALL-E, Stable Diffusion | Empty — to be populated |
| [Videos/](Videos/) | Veo, Sora, Runway, Pika | Empty — to be populated |
| [Visualizations/](Visualizations/) | Infographics, charts, diagram-as-art | Empty — to be populated |
| [Security/](Security/) | Prompt-injection tests, jailbreak research, red-teaming examples | Empty — to be populated |
| [Meta/](Meta/) | Prompt-engineering meta-prompts (prompt that generates prompts) | Empty — to be populated |

## Convention

- Each prompt file uses YAML frontmatter (`title`, `description`, `tool`, `topics`) and includes:
  - The full prompt text with `[BRACKETED FIELDS]` for variables
  - The target tool / model
  - A sample output (image link or short description)
  - Negative prompts and parameter notes when relevant

## Related

- [`2 - Resources/Nano Banana/`](../2%20-%20Resources/Nano%20Banana/) — Nano Banana resource collection
- [`4 - Prompts/Design/`](../4%20-%20Prompts/Design/) — text prompts for design tasks (diagram generation, etc.)
- [`5 - Skills/12_Design/`](../5%20-%20Skills/12_Design/) — design skills bundled in this repo
