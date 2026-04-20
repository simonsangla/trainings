# Make ChatGPT Your Slave — Training Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Produce a complete 90-minute training package ("Make ChatGPT Your Slave") — facilitator guide, slide deck, one-page cheat sheet, and a NotebookLM-ready master support doc — from the approved design spec at `docs/superpowers/specs/2026-04-20-make-chatgpt-your-slave-design.md`.

**Architecture:** Single source of truth is `support-doc.md`. All other artifacts derive from it — slide deck, cheat sheet, and facilitator guide. Content flows one-way: spec → support-doc → derivatives. This prevents drift and duplicated body copy across deliverables.

**Tech Stack:** Markdown (authoring), `anthropic-skills:pptx` (slides), `anthropic-skills:pdf` (cheat sheet), `anthropic-skills:doc-coauthoring` (support doc and facilitator guide discipline), `design:ux-copy` (microcopy polish). No code runtime required.

---

## File Structure

```
training/make-chatgpt-your-slave/
├── README.md                       # overview + how to use this package
├── support-doc.md                  # MASTER: full written content, NotebookLM-ready
├── facilitator-guide.md            # delivery layer: timing, cues, demos, Q&A, troubleshooting
├── slides/
│   ├── outline.md                  # slide-by-slide text + layout notes
│   └── slides.pptx                 # compiled deck
├── cheat-sheet/
│   ├── side-a.md                   # content for side A (formula + templates)
│   ├── side-b.md                   # content for side B (CO-STAR + scripts)
│   └── cheat-sheet.pdf             # compiled single page, two-sided
├── exercises/
│   ├── exercise-1-prompts.md       # 3 weak prompts for Ex 1
│   └── exercise-2-instructions.md  # instructions for Ex 2
└── assets/
    └── (placeholders for any images/diagrams the slide deck needs)
```

**Responsibility per file:**
- `README.md` — entry point. Explains what's in the package, how to run the session, how to regenerate artifacts.
- `support-doc.md` — canonical narrative of all content. Every word in slides or cheat sheet traces back here.
- `facilitator-guide.md` — only contains delivery material (timing, speaker notes, demo scripts, Q&A). Does not duplicate support-doc body.
- `slides/outline.md` — source-of-truth for slide text, before compiling to pptx.
- `slides/slides.pptx` — compiled artifact.
- `cheat-sheet/side-{a,b}.md` — authored content per side.
- `cheat-sheet/cheat-sheet.pdf` — compiled artifact.
- `exercises/*.md` — exercise prompts and instructions, referenced by slides and facilitator guide.

---

## Task 1: Scaffold Package Directory

**Files:**
- Create: `training/make-chatgpt-your-slave/` (directory and subdirectories)
- Create: `training/make-chatgpt-your-slave/README.md`

- [ ] **Step 1: Create directory tree**

```bash
mkdir -p training/make-chatgpt-your-slave/{slides,cheat-sheet,exercises,assets}
```

- [ ] **Step 2: Write README.md**

Create `training/make-chatgpt-your-slave/README.md` with exactly this content:

```markdown
# Make ChatGPT Your Slave — Training Package

A 90-minute hands-on training for mixed audiences (beginners to power users).
Core message: you are the boss; fix the prompt, not the worker.

## Contents

- `support-doc.md` — master written content (single source of truth; NotebookLM-ready).
- `facilitator-guide.md` — delivery layer: timing, speaker notes, demos, Q&A.
- `slides/slides.pptx` — presentation deck (outline in `slides/outline.md`).
- `cheat-sheet/cheat-sheet.pdf` — one-page printable reference (sources in `cheat-sheet/side-a.md` and `side-b.md`).
- `exercises/` — prompts and instructions for the two hands-on exercises.
- `assets/` — diagrams and images used in the deck.

## How to Run the Session

1. Open `facilitator-guide.md`. Follow the timing table top to bottom.
2. Have `slides/slides.pptx` open on the projector.
3. Print `cheat-sheet/cheat-sheet.pdf` double-sided, one copy per participant.
4. Brief participants to bring a laptop with ChatGPT access.

## How to Regenerate Artifacts

When content changes, edit `support-doc.md` first. Then propagate:
- Update `slides/outline.md` → regenerate `slides/slides.pptx`.
- Update `cheat-sheet/side-{a,b}.md` → regenerate `cheat-sheet/cheat-sheet.pdf`.
- Update `facilitator-guide.md` only for delivery-layer changes (timing, cues).

## NotebookLM Distribution

Feed `support-doc.md` into a NotebookLM notebook. Generate:
- Audio overview (podcast-style recap)
- Video overview
- Study guide (Q&A)
- Mind map
- Briefing doc

Share the NotebookLM link in the session wrap slide and post-session email.
```

- [ ] **Step 3: Commit**

```bash
git add training/make-chatgpt-your-slave/README.md
git commit -m "feat: scaffold training package directory and README"
```

---

## Task 2: Write Support Doc — Section 1 (Front Matter + Mental Model)

**Files:**
- Create: `training/make-chatgpt-your-slave/support-doc.md`

- [ ] **Step 1: Create support-doc.md with front matter and Module 1**

Create `training/make-chatgpt-your-slave/support-doc.md` with:

```markdown
# Make ChatGPT Your Slave

**A 90-minute training on commanding ChatGPT like a worker, not worshipping it like an oracle.**

## Core Premise

You are the boss. The model is the worker. Bad orders equal bad work. Fix the order, not the worker.

This training teaches four moves:
1. A realistic mental model of what a large language model is and isn't.
2. A repeatable prompt formula: Role, Task, Context, Format (RTF + Context).
3. A discipline of restating unclear instructions instead of arguing with the output.
4. A short list of limits and ethical guardrails you never break.

---

## Module 1 — What Is a Large Language Model

**Mental model:** a smart intern with amnesia. Trained on a massive pile of text. Its only job is to predict the most likely next token given everything before it.

Not a search engine. Not a database. Not a reasoning oracle. A plausibility machine.

### How it actually works

- It reads your prompt and predicts the next token. Then the next. Then the next. That is the entire mechanism.
- A token is roughly three quarters of a word. "Understanding" is one token. "Comprehension-focused" might be three.
- The context window is the working memory — everything the model can see at once when predicting. What falls outside is forgotten. There is no memory across sessions unless you reintroduce it.
- It does not browse the web, run code, or access private data unless a tool is explicitly enabled and given access.

### Hallucination

Hallucination is not a bug. It is how the model works when it doesn't know. It produces confident, plausible text because confident plausible text is what it was trained to produce.

Rule: plausibility is not truth. If the answer could damage something when wrong, verify from a primary source.

### One-sentence takeaway

**It predicts plausible text. Plausible is not the same as true.**
```

- [ ] **Step 2: Verify file created**

Run: `wc -l training/make-chatgpt-your-slave/support-doc.md`
Expected: roughly 40–50 lines.

- [ ] **Step 3: Commit**

```bash
git add training/make-chatgpt-your-slave/support-doc.md
git commit -m "feat(support-doc): add front matter and Module 1 (LLM mental model)"
```

---

## Task 3: Write Support Doc — Module 1.5 (Limits & Ethics)

**Files:**
- Modify: `training/make-chatgpt-your-slave/support-doc.md` (append)

- [ ] **Step 1: Append Module 1.5 to support-doc.md**

Append to `training/make-chatgpt-your-slave/support-doc.md`:

```markdown

---

## Module 1.5 — Limits and Ethics

Four rules. Non-negotiable.

### 1. Assume it hallucinates

Facts, citations, statistics, and quotes may be invented. The model has no mechanism to say "I don't know" unless trained or prompted to. Treat every load-bearing fact as suspect until you've checked a primary source.

### 2. Never paste sensitive data

Do not put client data, personally identifiable information, passwords, credentials, or confidential documents into consumer ChatGPT. Use your organization's approved enterprise tooling for anything sensitive. When in doubt, treat the prompt box as public.

### 3. Ownership and licensing

Outputs are yours to use, but originality is not guaranteed. For public-facing work — marketing, publishing, client deliverables — check for unintentional paraphrasing of existing material.

### 4. The fact-check rule

If the answer could cause real damage when wrong — legal, medical, financial, client-facing, regulatory — verify from a primary source before using. No exceptions.
```

- [ ] **Step 2: Commit**

```bash
git add training/make-chatgpt-your-slave/support-doc.md
git commit -m "feat(support-doc): add Module 1.5 (limits and ethics)"
```

---

## Task 4: Write Support Doc — Module 2 (RTF + Context Formula)

**Files:**
- Modify: `training/make-chatgpt-your-slave/support-doc.md` (append)

- [ ] **Step 1: Append Module 2**

Append to `training/make-chatgpt-your-slave/support-doc.md`:

```markdown

---

## Module 2 — The RTF + Context Formula

RTF — Role, Task, Format — is the established beginner framework for structured prompts. Add Context and you have a working prompt that beats 95% of what people type.

### Role

Who the model should be. The role defines voice, vocabulary, and priorities.

Bad: "Help me write something."
Good: "You are a senior B2B copywriter with seven years of experience in SaaS. You write direct, short-sentence prose and you hate jargon."

### Task

What it should actually do. One action, unambiguous.

Bad: "Make my LinkedIn better."
Good: "Rewrite the LinkedIn post below so it opens with a concrete claim and ends with one sharp question."

### Context

What the model needs to know to do the task well. Audience, constraints, prior attempts, product facts, tone, red lines.

Good: "The audience is CTOs at mid-market fintechs in Europe. Our product is a compliance automation tool that cuts audit prep time by 60%. Do not use the words 'leverage', 'synergy', or 'unlock'."

### Format

How to deliver. Length, structure, layout, tone markers.

Good: "Return three variants. Each under 280 characters. Use line breaks between sentences. End each variant with a single question mark."

### Before and after

**Before:**
> Write me a LinkedIn post about our product.

**After:**
> You are a senior B2B copywriter with experience in SaaS. Rewrite the LinkedIn post below so it opens with a concrete claim and ends with one sharp question. Audience: CTOs at mid-market fintechs. Product: compliance automation tool that cuts audit prep by 60%. Avoid the words "leverage", "synergy", "unlock". Return three variants, each under 280 characters, line breaks between sentences.

### Rule of thumb

If your prompt fits on one line, it is almost certainly too thin. The cost of a longer prompt is thirty seconds of typing. The cost of a bad output is however long you waste arguing with the model.
```

- [ ] **Step 2: Commit**

```bash
git add training/make-chatgpt-your-slave/support-doc.md
git commit -m "feat(support-doc): add Module 2 (RTF + Context formula)"
```

---

## Task 5: Write Support Doc — Module 3 (Chat Best Practices)

**Files:**
- Modify: `training/make-chatgpt-your-slave/support-doc.md` (append)

- [ ] **Step 1: Append Module 3**

Append to `training/make-chatgpt-your-slave/support-doc.md`:

```markdown

---

## Module 3 — Chat Best Practices

Six rules. Learn them once, use them every day.

### 1. The first prompt is load-bearing

Everything downstream rests on it. The role, the task framing, the constraints, the tone — the whole thread inherits from prompt one. Invest thirty extra seconds here and you save ten minutes later.

### 2. Don't scold — restate

When the output is wrong, the wrong move is:

> No, that's wrong. Do it again.

This fights the model's agreement bias without fixing the underlying input. The model will apologize, then produce a slightly different version of the same problem.

The right move:

> My instruction was not clear. Here is what I actually need: [clearer version].

Treat the model like a junior employee who did exactly what you asked. The fix is always upstream, in the request.

### 3. Garbage in, garbage out

If the answer is bad, nine times out of ten the prompt is the cause. Before blaming the model, reread what you actually wrote. You will be surprised how often the ambiguity is obvious in hindsight.

### 4. Edit upstream, not downstream

Most chat interfaces let you edit your original message and regenerate. Use this. Adding "actually wait, I meant" to a long thread piles bad context on top of bad context. Editing the first prompt gives you a clean retry.

### 5. Start fresh when the thread drifts

Long threads accumulate stale role definitions, contradictory instructions, and half-applied corrections. When you notice the output getting worse instead of better, start a new thread with a strong first prompt. A clean thread beats a twenty-turn argument almost every time.

### 6. Show, don't just tell

Examples beat adjectives. Instead of "make it punchy", paste a punchy example and say "in this style". Instead of "professional tone", paste two professional emails. The model learns formats from examples faster than from descriptions.
```

- [ ] **Step 2: Commit**

```bash
git add training/make-chatgpt-your-slave/support-doc.md
git commit -m "feat(support-doc): add Module 3 (chat best practices)"
```

---

## Task 6: Write Support Doc — Module 4 (You Are the Boss) + CO-STAR Appendix + Glossary

**Files:**
- Modify: `training/make-chatgpt-your-slave/support-doc.md` (append)

- [ ] **Step 1: Append Module 4, CO-STAR appendix, and glossary**

Append to `training/make-chatgpt-your-slave/support-doc.md`:

```markdown

---

## Module 4 — You Are the Boss

The provocation in the title is not about disrespecting the model. It's about killing passivity.

"It gave me a bad answer" is a phrase used by someone who thinks the model has agency. It doesn't. You do.

Delegate like a manager:

- **Brief clearly.** Role, task, context, format. Every time.
- **Set acceptance criteria.** What does "done" look like? Length, depth, must-include, must-avoid.
- **Iterate.** Read the output critically. Identify the one or two things that are off. Restate and regenerate.
- **Close the loop.** When the output is good, capture the winning prompt. Reuse it.

"Make ChatGPT your slave" means: own the direction. Stop asking the model what it thinks you should ask. Tell it exactly what you need and what "good" looks like.

---

## Appendix — CO-STAR for Power Users

Once RTF + Context feels automatic, graduate to CO-STAR. Developed by a Singaporean data scientist who won Singapore's first GPT-4 Prompt Engineering Competition.

- **C**ontext — background the model needs.
- **O**bjective — the specific goal.
- **S**tyle — writing style (e.g. business, academic, tabloid).
- **T**one — emotional register (e.g. formal, playful, urgent).
- **A**udience — who will read or use the output.
- **R**esponse — the exact output format.

Use CO-STAR for high-stakes or customer-facing prompts where tone and audience fit matter as much as content.

---

## Glossary

- **Token** — chunk of text the model processes. About ¾ of a word on average.
- **Context window** — maximum tokens the model can consider at once. Everything outside is invisible to it.
- **Hallucination** — the model producing confident, plausible, but false output.
- **Prompt** — the input you give the model. Includes role, task, context, and format.
- **Thread** — the full conversation history in one chat session.
- **System prompt** — hidden instructions set before the conversation starts (not all interfaces expose this).
- **Agreement bias** — the model's tendency to concede to the user rather than push back.

---

## Further Reading

- OpenAI official prompt engineering best practices: https://help.openai.com/en/articles/10032626-prompt-engineering-best-practices-for-chatgpt
- CO-STAR framework: https://portkey.ai/blog/what-is-costar-prompt-engineering/
- CLEAR framework (Texas A&M): https://guides.library.tamucc.edu/prompt-engineering/clear
```

- [ ] **Step 2: Verify completeness**

Run: `grep -c "^## Module" training/make-chatgpt-your-slave/support-doc.md`
Expected: at least 4 module headings. (Module 1, 1.5, 2, 3, 4 = 5 `## Module` lines.)

- [ ] **Step 3: Commit**

```bash
git add training/make-chatgpt-your-slave/support-doc.md
git commit -m "feat(support-doc): add Module 4, CO-STAR appendix, glossary, further reading"
```

---

## Task 7: Write Exercise Materials

**Files:**
- Create: `training/make-chatgpt-your-slave/exercises/exercise-1-prompts.md`
- Create: `training/make-chatgpt-your-slave/exercises/exercise-2-instructions.md`

- [ ] **Step 1: Write Exercise 1 prompts file**

Create `training/make-chatgpt-your-slave/exercises/exercise-1-prompts.md`:

```markdown
# Exercise 1 — Rewrite a Bad Prompt

**Duration:** 15 minutes (pairs)
**Goal:** Turn a weak prompt into a structured one using RTF + Context.

## Instructions

1. In pairs, pick one weak prompt from the list below.
2. Rewrite it using **Role, Task, Context, Format**.
3. Run both the original and the rewrite in ChatGPT.
4. Compare the outputs side by side.
5. Be ready to share what changed, and why.

## Weak Prompts (pick one)

### Option A — Status email

> Write me an email about the project status.

### Option B — Meeting summary

> Summarize this meeting. [Participants paste a meeting transcript of their choice, or use the sample on the following slide.]

### Option C — Launch brainstorm

> Give me ideas for the product launch.

## Debrief Questions

- What did you add in Role that changed the output most?
- Did Context or Format make a bigger difference?
- What would you remove if you had to cut the prompt in half?
```

- [ ] **Step 2: Write Exercise 2 instructions file**

Create `training/make-chatgpt-your-slave/exercises/exercise-2-instructions.md`:

```markdown
# Exercise 2 — Your Real Work Task

**Duration:** 20 minutes (solo, then share)
**Goal:** Apply RTF + Context + the "restate, don't scold" rule to something you actually need to do.

## Instructions

1. Pick one real task from your week. Examples: an email you need to write, a document to summarize, a plan to draft, an analysis to structure.
2. Build an RTF + Context prompt. Take three minutes on this step — don't rush it.
3. Run it in ChatGPT.
4. Read the output critically. What is off? Pick one or two specific issues.
5. Refine. Either:
   - **Edit the original prompt** and regenerate, or
   - **Restate the instruction** clearly ("My instruction wasn't clear. What I actually need is: …"). Do not say "that's wrong".
6. Run the refined prompt. Note what improved.

## Share (5 minutes)

Two or three volunteers walk through:
- The original prompt.
- The refined prompt.
- What the refinement fixed.

## Self-check

- Did your first prompt include all four of R, T, C, F?
- Did your refinement restate the instruction, or did it argue with the model?
- Would you reuse this prompt next week?
```

- [ ] **Step 3: Commit**

```bash
git add training/make-chatgpt-your-slave/exercises/
git commit -m "feat(exercises): add Exercise 1 prompts and Exercise 2 instructions"
```

---

## Task 8: Write Facilitator Guide

**Files:**
- Create: `training/make-chatgpt-your-slave/facilitator-guide.md`

- [ ] **Step 1: Write facilitator guide**

Create `training/make-chatgpt-your-slave/facilitator-guide.md`:

```markdown
# Facilitator Guide — Make ChatGPT Your Slave

**Session length:** 90 minutes.
**Audience:** mixed (beginners, casual, power users). 10–30 participants.
**Room:** projector, Wi-Fi, participants bring laptops.

This guide layers delivery on top of `support-doc.md`. It does not repeat the written content. Read `support-doc.md` first, then use this for timing, cues, and demos.

---

## Pre-Session Checklist

- [ ] Slides loaded on the projector (`slides/slides.pptx`).
- [ ] Cheat sheets printed double-sided, one per participant.
- [ ] ChatGPT open in a tab on the demo machine, signed in.
- [ ] Pre-recorded demo clips ready as fallback (in case of outage or rate-limit).
- [ ] NotebookLM link ready to share in the wrap slide.
- [ ] Timer visible (your watch, phone, or on-screen).

---

## Timing Table

| Time | Block | Slides | Notes |
|------|-------|--------|-------|
| 0:00–0:08 | Hook + Module 1 (LLM mental model) | 1–5 | Open with the "slave" provocation. Demo: show a one-line prompt vs a full one. |
| 0:08–0:12 | Module 1.5 (limits & ethics) | 6–7 | Say the confidentiality rule explicitly before any hands-on. |
| 0:12–0:25 | Module 2 (RTF + Context) | 8–11 | Live before/after demo on the LinkedIn post example. |
| 0:25–0:40 | Exercise 1 (rewrite a bad prompt) | 12 | Circulate. Listen for pairs stuck on Context — it's the hardest letter. |
| 0:40–0:55 | Module 3 (chat best practices) | 13–16 | Demo the "restate, don't scold" flip live. |
| 0:55–1:15 | Exercise 2 (real work task) | 17 | Protect this time. Do not cut it short. |
| 1:15–1:22 | Cheat sheet walk-through + CO-STAR teaser | 18–19 | Flip cheat sheet to side B. |
| 1:22–1:30 | Q&A + wrap + NotebookLM link | 20 | Share link. Optional: pass a feedback form. |

---

## Speaker Notes by Block

### 0:00–0:08 — Hook + Module 1

**Opening line (say verbatim or close):**
> "The title is a provocation. The slave in this room is not the AI. The slave is your workflow. By the end of today, ChatGPT will do what you tell it — because you'll know how to tell it."

**Demo 1:** In ChatGPT, type:
> "Write me an email about the project."

Let it produce something generic. Then say: "That's the output of zero thought. Let's do better."

**Key beat:** land the "smart intern with amnesia" metaphor. Repeat it once or twice across the session.

### 0:08–0:12 — Limits & Ethics

Do not rush this. The confidentiality rule must land before the hands-on exercises. Say explicitly: "In the next hour, you will be tempted to paste a real email or a real client document. If it's sensitive, redact or invent a substitute. The prompt box is not private."

### 0:12–0:25 — RTF + Context

**Demo 2:** Live rewrite of the bad LinkedIn prompt. Use the exact example from `support-doc.md` Module 2. Show both outputs side by side. Let the quality difference do the talking.

**Watch for:** beginners writing the words "role" "task" "context" "format" literally in their prompts. That's fine at first. Tell them they don't need the labels once the habit is internalized.

### 0:25–0:40 — Exercise 1

**Kickoff:** Point to `exercises/exercise-1-prompts.md`. Each pair picks one. Fifteen minutes.

**Circulate:** listen for pairs that wrote a good Role and Task but thin Context. Ask them: "Who is going to read this? What do they already know? What should they absolutely not see?"

**Debrief:** two pairs share. Highlight the specific Context additions that changed the output.

### 0:40–0:55 — Chat Best Practices

**Demo 3:** Start from a deliberately vague prompt. When the output is off, first say "no, that's wrong, do it again" — show that the second output is still off. Then demonstrate the restate move: "My instruction wasn't clear. Here's what I actually need…" Let the quality jump.

**Key beat:** "The fix is always upstream, in the request." Say it twice.

### 0:55–1:15 — Exercise 2

**Kickoff:** Point to `exercises/exercise-2-instructions.md`. Twenty minutes. Solo work, then share.

**Protect this time.** This is the exercise that makes the training stick. If you're running long, cut Module 3 examples or the cheat-sheet walk-through, not this.

**Debrief:** two or three volunteers. For each, ask: "Did your refinement restate, or did it argue?" Call it out when they argued. Reinforce.

### 1:15–1:22 — Cheat Sheet + CO-STAR

Walk through side A quickly. Flip to side B, land CO-STAR as the "next level" for people who already feel fluent with RTF + Context.

### 1:22–1:30 — Q&A + Wrap

**Closing line:**
> "You are the boss. The model is the worker. Bad orders equal bad work. Go give better orders."

Share the NotebookLM link. Pass the optional feedback form.

---

## Common Q&A

**Q: Which ChatGPT version should I use?**
A: Any recent version works for this training. Paid versions have longer context windows and better instruction-following, but RTF + Context applies identically.

**Q: Does this work for Claude / Gemini / Mistral?**
A: Yes. The formula is model-agnostic. Small quirks per model, but the structure transfers.

**Q: Can I paste my company's data?**
A: Only into enterprise-approved tools. Consumer ChatGPT is not a confidential environment.

**Q: How long should my prompts be?**
A: As long as they need to be. A good prompt for a complex task may run 200 words. That's normal. The cost of typing is small; the cost of a wasted output is larger.

**Q: Should I end prompts with "please" or "thank you"?**
A: It doesn't hurt. It doesn't meaningfully help either. The model isn't offended. Spend those tokens on Context instead.

**Q: What if the model refuses a request?**
A: Usually because the request looks harmful or is ambiguous enough to trip a safety classifier. Rephrase with clearer intent. If it still refuses and the request is legitimate, move to a tool better suited to the task.

**Q: How do I know when an output is a hallucination?**
A: Assume every fact could be. Verify anything load-bearing. Watch especially for specific numbers, citations, quotes, and names — these hallucinate most often.

---

## Troubleshooting

**Demo fails / rate limit / outage:** use the pre-recorded demo clip. Don't apologize at length — just pivot.

**A participant dominates:** acknowledge them, then explicitly invite quieter voices. "Let's hear from someone who hasn't spoken yet."

**A beginner is lost during an exercise:** pair them with a power user as "scribe". The power user operates, the beginner directs. Both learn.

**Exercise 2 runs short on time:** extend by 5 minutes. Cut the cheat-sheet walk-through to two minutes instead. Protect the hands-on work.

**Someone pastes real client data:** pause the exercise. Remind the room of the confidentiality rule. Do not shame the person — the rule is subtle and easy to forget.

---

## Post-Session

- [ ] Send follow-up email with NotebookLM link and cheat sheet PDF.
- [ ] Post winning prompts from Exercise 2 (anonymized, with permission) as a shared internal resource.
- [ ] Collect feedback forms. Note which module needs tightening next time.
```

- [ ] **Step 2: Commit**

```bash
git add training/make-chatgpt-your-slave/facilitator-guide.md
git commit -m "feat(facilitator): add facilitator guide with timing, demos, Q&A, troubleshooting"
```

---

## Task 9: Write Slide Outline

**Files:**
- Create: `training/make-chatgpt-your-slave/slides/outline.md`

- [ ] **Step 1: Write slide outline**

Create `training/make-chatgpt-your-slave/slides/outline.md`:

```markdown
# Slide Outline — Make ChatGPT Your Slave

20 slides. Visual-first. One idea per slide. Minimal text per slide (headline + max 1–2 supporting lines). Speaker notes carry the rest.

## Slide 1 — Title

**Headline:** Make ChatGPT Your Slave
**Subhead:** You are the boss. Fix the prompt, not the worker.
**Visual:** bold typographic treatment, provocative but clean.

## Slide 2 — What This Is

**Headline:** 90 minutes. Hands-on. Mixed-level.
**Body:** Two exercises. One formula. One rule you'll never forget.

## Slide 3 — Mental Model

**Headline:** It's a smart intern with amnesia.
**Visual:** intern at desk with a filing cabinet crossed out.

## Slide 4 — How It Works

**Headline:** It predicts the next token. That's it.
**Body:** Token ≈ ¾ word. Context window = working memory. No memory between sessions.

## Slide 5 — Plausibility ≠ Truth

**Headline:** It produces plausible text. Plausible is not true.
**Visual:** two outputs side by side — one correct, one confidently wrong.

## Slide 6 — Limits & Ethics

**Headline:** Four rules. Non-negotiable.
**Body:**
1. Assume it hallucinates.
2. Never paste sensitive data.
3. Outputs are yours — verify originality.
4. Fact-check anything load-bearing.

## Slide 7 — Confidentiality Callout

**Headline:** The prompt box is not private.
**Body:** No client data. No PII. No credentials. Use enterprise tools for sensitive work.

## Slide 8 — The Formula

**Headline:** RTF + Context
**Body:** Role. Task. Context. Format.

## Slide 9 — Role + Task

**Headline:** Who + What
**Body:**
- Role: "You are a senior B2B copywriter…"
- Task: "Rewrite the post below so…"

## Slide 10 — Context + Format

**Headline:** Why + How to Deliver
**Body:**
- Context: audience, constraints, red lines.
- Format: length, structure, tone.

## Slide 11 — Before / After

**Headline:** Watch the difference.
**Visual:** one-line prompt vs RTF+Context prompt, outputs side by side.

## Slide 12 — Exercise 1

**Headline:** Your turn. Pairs. 15 minutes.
**Body:** Pick a weak prompt. Rewrite with RTF + Context. Run both. Compare.

## Slide 13 — Best Practices (1/2)

**Headline:** First prompt is load-bearing.
**Body:** Invest 30 seconds. Save 10 minutes.

## Slide 14 — Don't Scold — Restate

**Headline:** Wrong: "No, you're wrong."
**Body:** Right: "My instruction wasn't clear. Here's what I actually need: …"

## Slide 15 — GIGO + Edit Upstream

**Headline:** Garbage in, garbage out.
**Body:** Edit the first prompt. Regenerate. Don't pile fixes into a long thread.

## Slide 16 — Fresh Threads + Examples

**Headline:** Start fresh. Show, don't tell.
**Body:** When a thread drifts, start over. When describing a style, paste an example.

## Slide 17 — Exercise 2

**Headline:** Your real work. Solo. 20 minutes.
**Body:** Pick a task from your week. Build an RTF + Context prompt. Refine once — restate, don't scold.

## Slide 18 — Cheat Sheet (Side A)

**Headline:** RTF + Context + Templates
**Visual:** cheat sheet preview.

## Slide 19 — CO-STAR (Side B)

**Headline:** Next level — CO-STAR.
**Body:** Context. Objective. Style. Tone. Audience. Response.

## Slide 20 — Wrap

**Headline:** You are the boss. Go give better orders.
**Body:** NotebookLM link: [placeholder URL]. Questions?
```

- [ ] **Step 2: Commit**

```bash
git add training/make-chatgpt-your-slave/slides/outline.md
git commit -m "feat(slides): add 20-slide outline with headlines, body, visuals"
```

---

## Task 10: Compile Slide Deck to PPTX

**Files:**
- Create: `training/make-chatgpt-your-slave/slides/slides.pptx`

- [ ] **Step 1: Invoke the pptx skill**

Use `anthropic-skills:pptx` to generate `slides.pptx` from `slides/outline.md`.

The prompt to the skill:
> Generate a 20-slide presentation from `training/make-chatgpt-your-slave/slides/outline.md`. Use a clean, modern theme with strong typography. Low text per slide (headline + 1–2 lines maximum). Use title slides, two-column layouts for Role/Task and Context/Format, and a simple wrap slide. Save output to `training/make-chatgpt-your-slave/slides/slides.pptx`.

- [ ] **Step 2: Verify file exists and opens**

Run: `ls -la training/make-chatgpt-your-slave/slides/slides.pptx`
Expected: file exists, size > 20 KB.

Manual check: open the pptx in Keynote, PowerPoint, or Google Slides. Confirm all 20 slides rendered, headlines match the outline, no overflow.

- [ ] **Step 3: Commit**

```bash
git add training/make-chatgpt-your-slave/slides/slides.pptx
git commit -m "feat(slides): compile 20-slide deck from outline"
```

---

## Task 11: Write Cheat Sheet Content (Side A)

**Files:**
- Create: `training/make-chatgpt-your-slave/cheat-sheet/side-a.md`

- [ ] **Step 1: Write Side A content**

Create `training/make-chatgpt-your-slave/cheat-sheet/side-a.md`:

```markdown
# Cheat Sheet — Side A

## RTF + Context

**R — Role.** Who the model is. Specific > generic.
**T — Task.** One clear action.
**C — Context.** Audience, constraints, red lines.
**F — Format.** Length, structure, tone.

---

## Three Reusable Templates

### 1. Email

> You are a [role]. Write an email to [audience] about [subject].
> Context: [key facts, prior history, tone required, things to avoid].
> Format: [length], [structure: greeting + 2 paragraphs + close], [tone].

### 2. Summary

> You are an analyst writing for [audience]. Summarize the text below.
> Context: [what decision this supports, what the reader already knows].
> Format: [bullet points | one paragraph | table], maximum [N words].
> Highlight [what matters most].

### 3. Draft or Plan

> You are a [role]. Draft a [doc type] for [purpose].
> Context: [goal, audience, constraints, prior attempts, must-include, must-avoid].
> Format: [sections], [length per section], [tone].

---

## Five Best Practices

1. First prompt is load-bearing.
2. Don't scold — restate.
3. Garbage in, garbage out.
4. Edit upstream. Start fresh when a thread drifts.
5. Show, don't just tell. Examples beat adjectives.
```

- [ ] **Step 2: Commit**

```bash
git add training/make-chatgpt-your-slave/cheat-sheet/side-a.md
git commit -m "feat(cheat-sheet): add side A — formula, templates, practices"
```

---

## Task 12: Write Cheat Sheet Content (Side B)

**Files:**
- Create: `training/make-chatgpt-your-slave/cheat-sheet/side-b.md`

- [ ] **Step 1: Write Side B content**

Create `training/make-chatgpt-your-slave/cheat-sheet/side-b.md`:

```markdown
# Cheat Sheet — Side B

## CO-STAR — For Power Users

Use when tone and audience fit matter as much as content.

- **C — Context.** What the model needs to know.
- **O — Objective.** The specific goal.
- **S — Style.** Writing style (business / academic / tabloid / conversational).
- **T — Tone.** Emotional register (formal / playful / urgent / calm).
- **A — Audience.** Who reads or uses the output.
- **R — Response.** Exact output format.

---

## "Don't Scold, Restate" Mini-Script

**When output is wrong, do not say:**
> "No, that's wrong. Do it again."

**Say instead:**
> "My instruction wasn't clear. What I actually need is: [clearer version]."

The fix is always upstream, in the request.

---

## Limits Checklist

Before pasting into ChatGPT, ask:

- [ ] Would I email this to a random address? If not, don't paste it.
- [ ] Is this a load-bearing fact? Then I will verify from a primary source.
- [ ] Am I about to argue with the output? Stop. Restate the instruction.
- [ ] Is this thread drifting? Start a new one with a strong first prompt.

---

## One-Line Rule

**You are the boss. Bad orders equal bad work. Fix the order, not the worker.**
```

- [ ] **Step 2: Commit**

```bash
git add training/make-chatgpt-your-slave/cheat-sheet/side-b.md
git commit -m "feat(cheat-sheet): add side B — CO-STAR, restate script, limits, one-liner"
```

---

## Task 13: Compile Cheat Sheet to PDF

**Files:**
- Create: `training/make-chatgpt-your-slave/cheat-sheet/cheat-sheet.pdf`

- [ ] **Step 1: Invoke the pdf skill**

Use `anthropic-skills:pdf` to generate a two-sided, single-page PDF combining side A and side B.

The prompt to the skill:
> Generate a single-page, double-sided PDF cheat sheet. Side A content from `training/make-chatgpt-your-slave/cheat-sheet/side-a.md`. Side B from `side-b.md`. Layout: two columns per side for density, clean sans-serif typography, strong hierarchy (headlines ~18pt, body ~10pt, code blocks monospace), generous whitespace. Paper size A4. Save to `training/make-chatgpt-your-slave/cheat-sheet/cheat-sheet.pdf`.

- [ ] **Step 2: Verify PDF**

Run: `ls -la training/make-chatgpt-your-slave/cheat-sheet/cheat-sheet.pdf`
Expected: file exists.

Manual check: open the PDF. Confirm exactly 2 pages (one per side), content fits without overflow, readable at printed size.

- [ ] **Step 3: Commit**

```bash
git add training/make-chatgpt-your-slave/cheat-sheet/cheat-sheet.pdf
git commit -m "feat(cheat-sheet): compile two-sided PDF"
```

---

## Task 14: Cross-Artifact Review

**Files:**
- All files under `training/make-chatgpt-your-slave/`

- [ ] **Step 1: Verify content consistency**

Run these checks:

```bash
# All artifacts exist
ls training/make-chatgpt-your-slave/support-doc.md \
   training/make-chatgpt-your-slave/facilitator-guide.md \
   training/make-chatgpt-your-slave/slides/outline.md \
   training/make-chatgpt-your-slave/slides/slides.pptx \
   training/make-chatgpt-your-slave/cheat-sheet/side-a.md \
   training/make-chatgpt-your-slave/cheat-sheet/side-b.md \
   training/make-chatgpt-your-slave/cheat-sheet/cheat-sheet.pdf \
   training/make-chatgpt-your-slave/exercises/exercise-1-prompts.md \
   training/make-chatgpt-your-slave/exercises/exercise-2-instructions.md
```

Expected: all files listed.

- [ ] **Step 2: Terminology consistency check**

Run: `grep -r "RTF + Context\|RTCF\|R-T-C-F" training/make-chatgpt-your-slave/`
Expected: only "RTF + Context" appears. No stray "RTCF" or "R-T-C-F".

Fix any variants found.

- [ ] **Step 3: Timing consistency check**

Run: `grep -E "0:[0-9]{2}" training/make-chatgpt-your-slave/facilitator-guide.md training/make-chatgpt-your-slave/slides/outline.md`

Compare the timing blocks in the facilitator guide's timing table against the spec's Section 4 table. Confirm they match block-for-block.

Fix any drift.

- [ ] **Step 4: Spec coverage check**

Open `docs/superpowers/specs/2026-04-20-make-chatgpt-your-slave-design.md`. For each section (Success Criteria, Modules, Exercises, Artifacts), confirm an artifact implements it. Note any gap.

If a gap is found, add a task here and close the gap before proceeding.

- [ ] **Step 5: Commit any fixes**

```bash
git add training/make-chatgpt-your-slave/
git commit -m "fix: cross-artifact consistency (terminology, timing)"
```

If no fixes are needed, skip the commit.

---

## Task 15: Final Polish Pass — UX Copy

**Files:**
- Modify: `training/make-chatgpt-your-slave/slides/outline.md`
- Modify: `training/make-chatgpt-your-slave/cheat-sheet/side-a.md`
- Modify: `training/make-chatgpt-your-slave/cheat-sheet/side-b.md`

- [ ] **Step 1: Invoke ux-copy skill**

Use `design:ux-copy` to review and tighten microcopy on:
- Slide headlines (outline.md): should be punchy, under 8 words each where possible.
- Cheat sheet headings and bullets: scannable, parallel structure, no filler.

The prompt to the skill:
> Review microcopy in these files for clarity, tone (direct, irreverent, practical), and punch. Tighten where possible without changing meaning. Flag any line that hedges or uses corporate filler ("leverage", "synergy", "unlock", "empower", "holistic"). Files: slides/outline.md, cheat-sheet/side-a.md, cheat-sheet/side-b.md.

- [ ] **Step 2: Apply suggested edits**

Apply the tightenings that match the established tone (direct, irreverent, concrete).

- [ ] **Step 3: Regenerate compiled artifacts if outline or cheat-sheet changed**

If `slides/outline.md` changed, re-run Task 10 Step 1 to regenerate `slides.pptx`.
If either `cheat-sheet/side-{a,b}.md` changed, re-run Task 13 Step 1 to regenerate `cheat-sheet.pdf`.

- [ ] **Step 4: Commit**

```bash
git add training/make-chatgpt-your-slave/
git commit -m "polish: tighten microcopy on slides and cheat sheet"
```

---

## Task 16: NotebookLM Readiness Check

**Files:**
- Read: `training/make-chatgpt-your-slave/support-doc.md`

- [ ] **Step 1: Verify support-doc is standalone**

Read through `support-doc.md` start to finish. Ask:
- Could someone who never saw the live session learn from this doc alone? Yes / no.
- Are all module headings clear and scannable? Yes / no.
- Are there any references to "the slide" or "the exercise" that would confuse a reader? If yes, rephrase.
- Is the opening (Core Premise) strong enough that NotebookLM's audio overview will open with a clear hook?

Fix any gaps.

- [ ] **Step 2: Word count check**

Run: `wc -w training/make-chatgpt-your-slave/support-doc.md`
Expected: between 1500 and 3500 words. (Under 1500 is too thin for NotebookLM audio. Over 3500 bloats the audio overview.)

If out of range, expand or compress.

- [ ] **Step 3: Commit any refinements**

```bash
git add training/make-chatgpt-your-slave/support-doc.md
git commit -m "polish: make support-doc standalone and NotebookLM-ready"
```

---

## Task 17: Final Spec Coverage Audit

**Files:**
- All spec sections vs all artifacts.

- [ ] **Step 1: Walk the spec**

Open `docs/superpowers/specs/2026-04-20-make-chatgpt-your-slave-design.md`. For each spec section 1–13, confirm coverage:

| Spec Section | Covered By |
|--------------|------------|
| 1. Purpose | support-doc.md (Core Premise) |
| 2. Audience | facilitator-guide.md (pre-session, room setup) |
| 3. Success Criteria | exercise outputs + debriefs |
| 4. Session Structure | facilitator-guide.md (timing table) |
| 5. Content Modules | support-doc.md (Modules 1–4 + 1.5) |
| 6. Exercises | exercises/*.md + Exercise slides (12, 17) |
| 7. Artifacts to Produce | All four exist |
| 8. Tone & Style | ux-copy pass complete |
| 9. Architecture & Boundaries | README.md documents the flow |
| 10. Dependencies | README.md references NotebookLM + pptx/pdf skills |
| 11. Out of Scope | Not implemented (correctly) |
| 12. Risks & Mitigations | facilitator-guide.md (troubleshooting) |
| 13. Open Questions | Resolved inline during implementation |

- [ ] **Step 2: Resolve any gap**

For any row where coverage is thin, add or update content. Commit.

- [ ] **Step 3: Final commit**

```bash
git add training/make-chatgpt-your-slave/
git commit -m "feat: complete Make ChatGPT Your Slave training package"
```

---

## Self-Review

Before handing off to execution:

1. **Spec coverage** — Task 17 is the explicit audit. Every spec section is mapped.
2. **Placeholder scan** — no TBD / TODO / "fill in later" in any task. Every task body contains the concrete content the agent will produce.
3. **Type / terminology consistency** — "RTF + Context" used uniformly (checked in Task 14 Step 2). Slide count consistent (20 slides in outline → 20 slides in pptx). Session length consistent (90 min everywhere). Artifact filenames consistent across plan, spec, and README.

No issues found.

---

## Execution Handoff

Plan complete and saved to `docs/superpowers/plans/2026-04-20-make-chatgpt-your-slave.md`. Two execution options:

1. **Subagent-Driven (recommended)** — dispatch a fresh subagent per task, review between tasks, fast iteration.
2. **Inline Execution** — execute tasks in this session using executing-plans, batch execution with checkpoints.

Which approach?
