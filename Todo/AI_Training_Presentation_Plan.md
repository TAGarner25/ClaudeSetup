---
title: AI Training Presentation Plan - Claude Fundamentals
description: Structured training plan for a PowerPoint presentation teaching basic Claude AI terminology, how-tos, and use cases. Organized for progressive learning from foundation through capabilities to best practices.
created: 2026-05-04
updated: 2026-05-04
topics: [training, presentation-plan, claude-fundamentals, education, powerpoint]
---

# AI Training Presentation Plan: Claude Fundamentals

## Overview

This plan organizes 11 topics into 5 logical sections that build on each other. The order moves from "how Claude works" → "where you find it" → "how to talk to it" → "what it can do" → "how to do it well." Each topic includes slide-ready content and 3-5 hands-on use cases attendees can try themselves.

**Estimated total slides:** 33-40
**Estimated training length:** 60-90 minutes (depending on demo time)
**Confidence in structure:** 90% — pedagogically sound; minor adjustments may be warranted based on audience level

---

## Recommended Section Order

| # | Section | Topics | Why this order |
|---|---------|--------|----------------|
| 1 | **Foundation: How Claude Works** | Training Cutoff, Context Window, Hallucinations | Sets accurate expectations before users try anything |
| 2 | **Interfaces: Where to Use Claude** | Chat, Projects, Cowork, Code | Users need to know where to go to follow along |
| 3 | **Interaction: How to Talk to Claude** | Prompting, System Prompt and User Preferences | Core skill; everything else amplifies a good prompt |
| 4 | **Capabilities: What Claude Can Do** | Artifacts, Document/File Generation, Skills, Memory | Now they're equipped to appreciate advanced features |
| 5 | **Synthesis: Best Practices** | Best Practices | Reinforces and operationalizes everything above |

---

## Suggested Opening (3-4 slides)

1. **Title slide** — "Working with Claude: A Practical Introduction"
2. **Why this matters** — frame the value (productivity, quality, time savings, real examples)
3. **What you'll be able to do by the end** — set learning outcomes
4. **What is Claude** — one slide framing: an AI assistant by Anthropic, accessible via Chat, Projects, Cowork, and Code

---

## Section 1 — Foundation: How Claude Works

### Topic 1: Training Cutoff

**Definition:** The date past which Claude has no reliable knowledge. Claude's understanding of the world is "frozen" at the time it was last trained.

**Key points for slides:**
- Claude's knowledge has a cutoff date (current Sonnet/Opus 4.6 models: ~end of May 2025) [I am 85% confident in this specific date — *this needs to be verified by outside sources*]
- After the cutoff, Claude doesn't know about new events, products, prices, or news
- Web search tools (when enabled) let Claude reach beyond the cutoff
- Always assume specific recent facts need verification

**Why it matters:** Sets expectations. Prevents confident-but-wrong answers about current events.

**Use cases to try:**
1. Ask Claude about a major event you know happened in the past 6 months — observe how it handles it
2. Ask: *"What is your training cutoff date, and what should I do if I need information past that?"*
3. Ask the same recent-news question with and without web search enabled — compare answers

---

### Topic 2: Context Window

**Definition:** Claude's "working memory" — the total amount of text (input + output) it can hold in mind at once.

**Key points for slides:**
- Measured in **tokens** (~3/4 of a word each)
- Modern Claude models: 200,000+ tokens (some up to 1M) [95% confident — *this should be verified against current model specs*]
- Once full, earlier content gets summarized or dropped
- Why it matters: long documents fit; very long conversations don't fully

**Analogy for slide:** A desk where Claude can only see papers currently on it. Add too many, and the oldest fall off the back.

**Practical implications:**
- Big PDFs, transcripts, codebases — usually fit in one window
- Hour-long brainstorms — Claude may forget what you said at the start
- This is why **Memory** features exist (we'll cover later)

**Use cases to try:**
1. Upload a 30+ page document and ask Claude to summarize a specific section near the end
2. Have a long brainstorming chat (20+ messages), then ask Claude to recap your earliest points
3. Compare uploading one large file vs. five small files on the same topic

---

### Topic 3: Hallucinations

**Definition:** When AI confidently produces information that is fabricated, incorrect, or made up — presented as if it were factual.

**Key points for slides:**
- Claude predicts plausible text. Sometimes the most plausible answer is invented.
- Common forms: fake citations, made-up URLs, fabricated stats, wrong code library names, false historical details
- Hallucinations are most likely on: niche topics, specific numbers, sources/citations, anything past the training cutoff

**Mitigation strategies (slide-ready list):**
- Ask for confidence levels
- Provide source documents instead of asking from memory
- Use web search for facts
- Verify any cited source by clicking through
- Cross-check critical claims with another source

**Use cases to try:**
1. Ask Claude to cite three academic sources for a niche topic — then look them up. Note any that don't exist.
2. Ask a specific factual question and request: *"Give me your confidence level (0-100%) for each claim."*
3. Compare answers with vs. without web search on a current-events question
4. Ask about an obscure book or paper — verify the details Claude provides

---

## Section 2 — Interfaces: Where to Use Claude

### Topic 4: Chat, Projects, Cowork, Code

**This is the longest single topic — recommend a comparison-table slide plus one slide per interface.**

| Interface | Best for | Key features | Audience |
|-----------|----------|--------------|----------|
| **Claude Chat** (claude.ai) | Quick questions, drafting, brainstorming | Web/mobile/desktop, no setup | Everyone |
| **Claude Projects** | Recurring work on a topic | Persistent files + custom instructions | Knowledge workers |
| **Claude Cowork** | File-heavy automation, document creation | Local file access, sandboxed shell, plugins | Non-developers wanting automation |
| **Claude Code** | Software development | CLI tool, agentic coding, repository-aware | Developers |

**Slide-ready descriptions:**

- **Chat:** The default. Open claude.ai, ask a question, get an answer. No persistent state across conversations unless you turn on memory features.

- **Projects:** Workspaces inside Claude.ai that hold uploaded files and custom instructions. Every conversation in the project starts with that context already loaded. Think: a "Marketing" project with brand guidelines, past campaigns, and audience data — every chat in it is pre-informed.

- **Cowork (research preview):** A desktop application where Claude can read/write files on your computer, run code in a sandboxed Linux environment, and use installed plugins/skills. It's how you turn "explain how" into "do it for me."

- **Code:** A CLI for developers. Claude reads your codebase, plans changes, writes code, runs tests, opens PRs. Designed for engineering work.

**Use cases to try:**
1. Same prompt in **Chat** vs. **Projects** with relevant files loaded — feel the context advantage
2. In **Cowork:** ask Claude to organize a folder on your computer or generate a document from inputs
3. In **Projects:** upload company docs, return next session, ask follow-up questions referencing them
4. (Developers) In **Code:** point at a small repo and ask for a refactor or test additions

---

## Section 3 — Interaction: How to Talk to Claude

### Topic 5: Prompting

**Definition:** The skill of communicating with AI to get useful, accurate, well-formatted output.

**Anatomy of a good prompt (slide-ready):**
1. **Role/Context** — "You are a senior financial analyst..."
2. **Task** — "Analyze the attached Q3 earnings report..."
3. **Constraints** — "...in under 300 words..."
4. **Format** — "...as a bulleted executive summary..."
5. **Audience** — "...for a non-technical board."

**Key principles:**
- **Be specific.** "Write an email" → "Write a 150-word professional email to my client declining a meeting because of a scheduling conflict, offering two alternative times next week."
- **Provide context.** Who you are, who it's for, why it matters.
- **Show examples.** Paste a sample of what good looks like.
- **Specify format.** Bullets, table, prose, JSON, slide outline.
- **Iterate.** First answer is a draft. Refine.

**Common mistakes:**
- Vague requests ("help with my report")
- Combining multiple unrelated tasks in one prompt
- Assuming Claude knows internal/proprietary context it doesn't have
- Accepting the first response without refinement

**Use cases to try:**
1. Take a vague prompt you'd normally write, then rewrite it with role/task/constraints/format. Compare results.
2. Ask the same question with vs. without a role assigned. Note the tone shift.
3. Ask for the same content in three formats: bulleted list, executive summary paragraph, and a table.
4. Provide an example of "good output" you've seen elsewhere, then ask Claude to match the style.

---

### Topic 6: System Prompt and User Preferences

**Two related but distinct concepts. Recommend one slide each.**

#### System Prompt
- Instructions given to Claude that apply to **every** message in a conversation
- Usually set by the **platform** (Anthropic) or by an **admin/developer**
- Defines Claude's identity, capabilities, safety rules, and tone
- In standard Chat, you usually don't see or edit it
- In Code/Cowork, files like `CLAUDE.md` partially influence it

#### User Preferences
- **Personal customizations you control**
- Examples: preferred name, communication style, professional context, formatting rules
- Available in claude.ai settings, in Cowork preferences, and via `CLAUDE.md` in Code
- Persist across all your conversations — set once, benefit everywhere

**Why it matters:**
- Stop repeating yourself ("remember, I'm a financial analyst")
- Get consistent tone and format across sessions
- Make Claude feel tuned to *you* rather than generic

**Real example (slide-ready):** A user who sets preferences like "always provide confidence levels," "speak as a partner — no fluff," and "use markdown frontmatter on all created files" gets responses tailored to that style automatically — every time.

**Use cases to try:**
1. Set your name and one communication style preference. Ask the same question before/after.
2. Add a preference like *"Always include a confidence level (0-100%) for factual claims."* Test it.
3. Add domain context: *"I work in [your field]. Default to that frame of reference."* Notice the tailoring.
4. Try a preference like *"Push back on bad ideas rather than agreeing with everything."* Useful for honest feedback.

---

## Section 4 — Capabilities: What Claude Can Do

### Topic 7: Artifacts

**Definition:** Self-contained, interactive content Claude generates that lives in a side panel — separate from the chat itself.

**Types:**
- HTML pages (calculators, dashboards, interactive widgets)
- React components
- Code in any language
- Markdown documents
- Mermaid diagrams (flowcharts, sequence, gantt)
- SVG graphics

**Why they matter:**
- You get a **working tool**, not just text describing one
- Iterate visually with the live preview
- Save, share, reuse
- In Cowork, artifacts can be **"live"** — pulling fresh data from connected tools each time you open them

**Use cases to try:**
1. Ask Claude to build a simple budget calculator as an interactive HTML artifact
2. Request a flowchart of a process you do at work (Mermaid diagram)
3. Have Claude create a single-page HTML "cheat sheet" for any topic
4. Ask for a small interactive quiz or lookup tool
5. (Cowork) Build a live dashboard pulling from a connected tool like Slack, Calendar, or Drive

---

### Topic 8: Document/File Generation

**Definition:** Claude can produce real, downloadable files — not just text describing them.

**Supported formats (slide-ready table):**

| Format | Best for |
|--------|----------|
| **Word (.docx)** | Reports, memos, letters, proposals |
| **PowerPoint (.pptx)** | Presentations, training decks, pitch decks |
| **Excel (.xlsx)** | Spreadsheets, budgets, financial models, charts |
| **PDF** | Final reports, filled forms, signed documents |
| **Markdown (.md)** | Documentation, notes, structured content |
| **HTML / code files** | Web pages, scripts, config files |

**How it works:**
- In Cowork, Claude uses **Skills** (e.g., the `pptx` skill) that bake in professional best practices
- Files are saved to your workspace folder with a direct link to open them
- In Chat, files are provided as downloadable attachments

**Use cases to try:**
1. *"Create a 5-slide PowerPoint introducing my team to [topic]."*
2. *"Build an Excel budget template with categories, monthly columns, and totals formulas."*
3. *"Draft a 1-page Word memo to my manager about [issue]."*
4. *"Generate a PDF cheat sheet for [topic]."*
5. **Combine:** *"Read this Word doc and rewrite it as a 7-slide PowerPoint."*

---

### Topic 9: Skills

**Definition:** Pre-built bundles of expertise Claude can invoke — essentially specialized "domain experts" that ship with instructions, scripts, and templates.

**How they work:**
- A skill is a folder with a `SKILL.md` file plus supporting resources
- Claude reads the skill description, decides if it applies, then loads the full instructions
- They embody best practices so you don't have to re-prompt them every time

**Examples (from common Claude environments):**
- `pptx` — professional presentation creation
- `xlsx` — spreadsheet best practices
- `pdf` — PDF manipulation and form filling
- `chart-visualization` — picks the right chart type for your data
- `engineering:code-review` — structured code review workflow
- Brand-specific skills (e.g., applying your company's color palette and fonts)

**Why they matter:**
- **Quality:** Best practices baked in (the `pptx` skill knows good slide design)
- **Consistency:** Same approach every time
- **Reusability:** Build once, use everywhere
- **Shareable:** Skills can be installed by teammates

**Use cases to try:**
1. Ask Claude: *"What skills are available in this environment, and which ones apply to [my task]?"*
2. Create a presentation and observe how the `pptx` skill produces clean, professional output
3. (If you have brand guidelines installed) Ask for a document with brand styling — see the automated theming
4. Try the same task with and without invoking a relevant skill — compare results

---

### Topic 10: Memory

**Definition:** Persistent information Claude retains across conversations.

**Different types in the Claude ecosystem:**

| Type | Scope | Where |
|------|-------|-------|
| **Conversation memory** | Single chat | Limited by context window |
| **Projects memory** | One Project's chats | Claude.ai Projects |
| **User Preferences** | All your conversations | Settings (Chat) or preferences files |
| **CLAUDE.md / AGENTS.md** | Workspace/repo | Code, Cowork |
| **Memory MCP** | Cross-session knowledge graph | Cowork plugin |
| **External (Obsidian)** | Long-term "second brain" | Obsidian + connector |

**Key insight:** Without memory, every conversation starts from zero. Memory transforms Claude from a tool into a collaborator that knows you and your work.

**Important nuance:** Memory must be intentional. Claude doesn't automatically remember unless a memory feature is engaged.

**Use cases to try:**
1. In **Projects:** upload a company doc, return tomorrow, ask a follow-up question that references it
2. Set up a `CLAUDE.md` in a folder — see Claude pick up your context automatically next session
3. Use the **memory MCP:** tell Claude facts about your team and projects, then quiz it later
4. Compare: ask the same question in a fresh chat vs. in a Project with relevant context loaded

---

## Section 5 — Synthesis: Best Practices

### Topic 11: Best Practices

**Recommend 2-3 slides for this section, organized as habits.**

#### Habit 1: Pick the Right Tool
- Quick question? **Chat**
- Recurring topic? **Projects**
- File-heavy task? **Cowork**
- Coding? **Code**

#### Habit 2: Front-Load Context
- Tell Claude who you are, who it's for, what success looks like
- Upload reference docs rather than describing them
- Use Projects/CLAUDE.md so you don't repeat yourself

#### Habit 3: Be Specific About Output
- Format, length, tone, audience — state them all

#### Habit 4: Verify, Don't Trust Blindly
- Cross-check facts on high-stakes work
- Ask for confidence levels and sources
- Be skeptical past the training cutoff
- Watch citations and statistics for hallucinations

#### Habit 5: Iterate
- First answer is a draft. Refine.
- Give specific feedback ("more concise," "different tone," "wrong audience")

#### Habit 6: Use the Right Capability
- Need a real document? Ask for **file generation**
- Need a working tool? Ask for an **artifact**
- Need expertise? Let Claude invoke a **skill**

#### Habit 7: Customize for Yourself
- Set user preferences once
- Build CLAUDE.md files for recurring projects
- Establish a memory system

#### Habit 8: Know the Limits
- Training cutoff → recent info may be wrong
- Context window → very long chats lose early context
- Hallucinations → verify specific facts
- Privacy → Claude can only see what you give it

#### Habit 9: Keep Humans in the Loop on High Stakes
- Legal, financial, medical → verify with professionals
- Public communications → review before sending
- Production code → review before deploying

#### Habit 10: Make It a Habit
- Keep a personal "prompt library" of what works
- Build skills/projects for repeated workflows
- Share what works with your team

---

## Suggested Closing (2-3 slides)

1. **Resources** — links to Anthropic docs (docs.claude.com), support, your internal Claude playbook if you have one
2. **Practice challenge** — *"This week, pick one workflow you do regularly and try doing it with Claude. Note what worked and what didn't."*
3. **Q&A / Thank you**

---

## Slide Count Estimate

| Section | Slides |
|---------|--------|
| Opening | 3-4 |
| Section 1: Foundation (3 topics) | 7-8 |
| Section 2: Interfaces | 4-5 |
| Section 3: Interaction (2 topics) | 5 |
| Section 4: Capabilities (4 topics) | 9-10 |
| Section 5: Best Practices | 3-4 |
| Closing | 2-3 |
| **Total** | **33-40** |

---

## Open Questions for You

Before I build the actual `.pptx`, a few decisions to make:

1. **Audience level** — complete beginners, or some prior AI exposure? (Affects depth of foundation section)
2. **Time target** — 30 min, 60 min, or 90 min training? (Affects whether to keep all 11 topics or trim)
3. **Brand styling** — apply Erickson Group brand guidelines? (Confirmed available in your skills)
4. **Live demos** — do you want notes for live demonstrations during certain topics, or pure slides?
5. **Handout** — should I also generate a 1-2 page PDF cheat sheet attendees can take home?

---

## Confidence Levels

- **Topic ordering and pedagogical structure:** 90% confident this flow works for beginners
- **Topic content accuracy:** 95% confident on conceptual content; 80% confident on specific version/date details that may have changed (training cutoff date, exact context window sizes — *these need verification against current Anthropic docs before finalizing*)
- **Use case suggestions:** 95% confident — these are tested, common entry-point exercises
- **Slide count estimate:** 75% — actual count depends on how dense each slide is

---

## Related Files in This Repo

- [[1 - General Overview/2_Anthropic/README.md]] — your existing Claude reference
- [[5 - Skills/Overview]] — skill system reference
- [[3 - Cheat Sheets]] — could pair with this training as a handout source
