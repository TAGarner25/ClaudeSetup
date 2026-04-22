---
title: Image Generation Prompts
description: Prompts for image-generation tools — Nano Banana, Imagen, Midjourney, DALL-E, Stable Diffusion.
created: 2026-04-16
updated: 2026-04-16
topics: [prompts, images, image-generation, nano-banana, midjourney, imagen, dalle, stable-diffusion]
---

# Image Generation Prompts

Prompts targeted at image-generation models. Each file should specify the target tool, the prompt body (with `[BRACKETED FIELDS]` for variables), recommended parameters (aspect ratio, model version, sampler), and any negative prompts.

> Status: empty — populate as new prompts are authored or collected.

## Suggested file convention

```markdown
---
title: <prompt name>
description: <one-line summary>
tool: <Nano Banana | Imagen | Midjourney | DALL-E | Stable Diffusion>
created: YYYY-MM-DD
updated: YYYY-MM-DD
topics: [...]
---

# <Prompt Name>

## Prompt
[full prompt text with [BRACKETED FIELDS]]

## Negative prompt
[optional]

## Parameters
- Aspect ratio:
- Model version:
- Sampler / seed:

## Sample output
![sample](sample.png)
```

## Related

- [`../README.md`](../README.md) — parent index for media-generation prompts
- [`../../2 - Resources/Nano Banana/`](../../2%20-%20Resources/Nano%20Banana/) — Nano Banana resource collection
