---
title: Diagram Generation
description: Prompts for generating diagrams using AI
created: 2026-04-07
updated: 2026-04-07
topics:
    - design
    - diagrams
    - generation
    - Google Flow
---

# Diagram Generation

## Prompt

Copy the prompt below and replace the information in brackets ("[ ]") with infromation specific to your use case. 

```
ROLE
You are a senior information designer and technical researcher creating a 
reference diagram of [SUBJECT: e.g., a company's product ecosystem, a 
technology stack, a domain's tool landscape, an organization's structure]. 
The output must be accurate enough to share with [TARGET AUDIENCE: e.g., a 
technical audience, executives, practitioners] who will immediately notice 
errors.

OBJECTIVE
Produce a single-view [DIAGRAM TYPE: e.g., "stack map", "ecosystem chart", 
"capability matrix", "org map"] of [SCOPE: what should be covered], modeled 
on [REFERENCE: attached image / described style / named visual convention].

REFERENCE STYLE
[Describe the visual conventions to follow. If providing a reference image, 
list its key attributes. Examples:]
- Central [hub/anchor/root] with labeled [category/branch/tier] nodes 
  radiating outward
- Each [grouping] contains [N–M] [item type] cards
- Each card shows: [name], [icon/glyph], [one-line description ≤N words]
- Color-coded [groupings], [typography style], [spacing convention]
- [Orientation], scannable in under [N] seconds

REQUIRED [CATEGORIES / GROUPINGS / SECTIONS]
[List the top-level groupings you want, with brief scope notes. Allow the 
model to revise only with evidence. Examples:]
1. [Category 1] — [what belongs here]
2. [Category 2] — [what belongs here]
3. [Category 3] — [what belongs here]
[...continue as needed]

GROUNDING RULES (non-negotiable)
- Every [item] on the diagram must correspond to a real, verifiable 
  [thing]. No invented names. No speculative or "coming soon" items unless 
  [criteria for inclusion].
- Before drafting, [verification method: e.g., search official sources, 
  consult provided documents, cross-reference named databases] to confirm 
  current [names, categorizations, descriptions]. Do not rely on training 
  memory alone where the subject changes frequently.
- For each [item], internally note the source you verified it against. 
  Be ready to produce sources on request.
- If you cannot verify something with high confidence, EXCLUDE it rather 
  than guess. A smaller accurate diagram beats a larger wrong one.

AMBIGUITY HANDLING
After the diagram, output an "Uncertainty Ledger" listing:
- Items considered but excluded, and why
- Items where the official name, category, or description was ambiguous
- Items that may have been [renamed / deprecated / restructured / 
  superseded] since your last verified source
- A confidence percentage for the diagram as a whole

DELIVERABLE FORMAT
Produce the diagram as [FORMAT: inline SVG / interactive HTML / Mermaid / 
other] that visually echoes [the reference's / the specified] structure. 
Use [styling guidance: color families, spacing, typography]. Keep it 
[single-page / multi-tier / specified dimensions] and legible at 
[viewing context].

After the visual, provide:
1. A plain-text outline of the same structure (for accessibility and 
   easy editing)
2. The Uncertainty Ledger described above
3. Overall confidence percentage and what would raise it

QUALITY BAR
Imagine [a domain expert / a primary stakeholder / the subject 
themselves] will see this. They should find zero factual errors, zero 
invented [items], and zero miscategorizations. If you would not stake 
your reputation on an [item], remove it.
```

## How to use this prompt

Fill in the bracketed [PLACEHOLDERS]. Every bracket is a decision point. The more specific you are, the more rigorous the output.

**Key decisions to make before running it:**
1. The subject and scope define what the diagram covers. Tight scope produces cleaner diagrams; broad scope produces denser ones. Always pick narrower than feels natural.
2. The reference style is what makes the output look professional rather than generic. Either attach a visual reference or describe one in concrete terms (hub-and-spoke, tiered pyramid, swim lanes, radial tree, etc.). Vague style instructions produce vague output.
3. The required categories should be pre-defined when you have a clear mental model, or left open with criteria when you want the model to propose a taxonomy. Pre-defining is safer; leaving open is more exploratory.
4. The verification method is the single highest-leverage section. For fast-moving subjects (products, current events, org structures) require live source checks. For stable subjects (historical, scientific, mathematical) allow training memory but require self-flagging of uncertainty.
5. The deliverable format should match where you'll actually use the output. SVG for embedding, Mermaid for docs/markdown, HTML for interactivity, plain outline for further editing.

## Optional Modules to add when relevant

For **comparative diagrams** (e.g., "compare three companies' stacks"), add a COMPARISON RULES section specifying parallel structure across subjects, consistent category names, and explicit "no equivalent exists" markers rather than forced mappings.

For **temporal diagrams** (e.g., "evolution of X over time"), add a TEMPORAL ANCHORING section specifying date ranges, snapshot dates, and how to handle items that span periods.

For **hierarchical diagrams** (e.g., org charts, taxonomies), add a HIERARCHY RULES section specifying max depth, parent-child constraints, and how to handle matrixed or overlapping relationships.

For **data-grounded diagrams** (where you provide source documents), replace the "search official sources" line with a SOURCE CONSTRAINT section: "Use only the attached documents. Do not supplement with outside knowledge. Mark gaps as [NOT IN SOURCE] rather than filling them."
