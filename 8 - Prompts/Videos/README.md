---
title: Video Generation Prompts
description: Prompts for video-generation tools — Veo, Sora, Runway, Pika.
created: 2026-04-16
updated: 2026-04-16
topics: [prompts, videos, video-generation, veo, sora, runway, pika]
---

# Video Generation Prompts

Prompts for text-to-video and image-to-video tools. Each file should describe the target tool, prompt body, duration, aspect ratio, motion intensity, and any reference images.

> Status: empty — populate as new prompts are authored or collected.

## Suggested file convention

```markdown
---
title: <prompt name>
description: <one-line summary>
tool: <Veo | Sora | Runway | Pika>
duration: <seconds>
aspect_ratio: <16:9 | 9:16 | 1:1>
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# <Prompt Name>

## Prompt
[full prompt text]

## Reference image
[optional path or URL]

## Parameters
- Camera motion:
- Style:
- Negative prompt:

## Sample output
[link to generated clip]
```

## Related

- [`../README.md`](../README.md) — parent index for media-generation prompts
