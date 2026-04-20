# Design Spec — "Make ChatGPT Your Slave" Training

**Date:** 2026-04-20
**Status:** Approved for implementation planning
**Owner:** Simon Sangla

---

## 1. Purpose

Deliver a 90-minute, high-energy, hands-on training that teaches participants to **take command of ChatGPT** — treating it as a powerful but literal-minded worker that needs clear orders, not a mind-reading oracle.

Core message: **You are the boss. The model is the worker. Bad orders = bad work. Fix the order, not the worker.**

## 2. Audience

Mixed group — beginners, casual users, and power users in the same room. Design accommodates all three:

- **Beginners** get a clear mental model and safe entry points.
- **Casual users** get a repeatable formula (RTF + Context).
- **Power users** get advanced material via exercises and a CO-STAR teaser on the cheat sheet.

Language: English.
Group size assumption: 10–30 participants.

## 3. Success Criteria

By the end of the session, every participant can:

1. Explain in one sentence what an LLM is and what it is not (predictor, not search engine).
2. Write a structured prompt using the **RTF + Context** formula (Role, Task, Format + Context).
3. Recognize and correct their own bad prompt — restating the instruction instead of arguing with the model.
4. Identify one use case from their own work where they will apply this within one week.
5. Articulate at least two limits (hallucination, confidentiality) and the fact-check rule.

Measured by:
- Exercise 2 output (each participant produces a working prompt for a real task).
- Verbal debrief (2–3 volunteers share results).
- Post-session feedback form (optional, 3 questions).

## 4. Session Structure (90 min)

| Time | Block | Mode | Duration |
|------|-------|------|----------|
| 0:00–0:08 | **Hook + LLM mental model** — what it is (next-token predictor), what it isn't (search engine, oracle, database), tokens, context window | Talk + 1 live demo | 8 min |
| 0:08–0:12 | **Limits & ethics** — hallucination, confidentiality (no client/PII data in prompts), fact-check rule | Talk | 4 min |
| 0:12–0:25 | **RTF + Context formula** — Role, Task, Context, Format; before/after live demo | Talk + live demo | 13 min |
| 0:25–0:40 | **Exercise 1 — Rewrite a bad prompt** in pairs using RTF + Context | Hands-on pairs | 15 min |
| 0:40–0:55 | **Chat best practices** — first prompt sets the thread, don't scold ("no, you're wrong" → "my instruction wasn't clear, let me restate"), GIGO, when to start a fresh thread, examples over descriptions | Talk + 1 demo | 15 min |
| 0:55–1:15 | **Exercise 2 — Real work task**: each participant picks one task, builds a prompt, runs it, refines once. 2–3 volunteers share. | Hands-on solo + share | 20 min |
| 1:15–1:22 | **Cheat sheet walk-through + CO-STAR teaser** | Talk | 7 min |
| 1:22–1:30 | **Q&A + wrap + NotebookLM link** | Discussion | 8 min |

## 5. Content Modules

### Module 1 — What is an LLM (8 min)

**Mental model:** smart intern with amnesia. Trained on massive text, predicts the most likely next token, no long-term memory between chats unless you provide it.

**Key concepts:**
- Next-token prediction (not retrieval, not reasoning-from-facts).
- Token ≈ ¾ of a word.
- Context window = working memory. What falls outside is forgotten.
- No browsing or tool use unless explicitly enabled.
- Hallucination = confident guessing when uncertain. A feature of how it works, not a bug to debug away.

**One-sentence takeaway:** *"It predicts plausible text. Plausible ≠ true."*

### Module 1.5 — Limits & Ethics (4 min)

- **Hallucination:** facts, citations, statistics may be invented. Always fact-check anything load-bearing.
- **Confidentiality:** never paste client data, PII, passwords, or confidential documents into consumer ChatGPT. Use approved enterprise tools for sensitive work.
- **Ownership & licensing:** outputs are yours to use, but verify originality for public-facing work.
- **Fact-check rule:** if the answer could cause damage when wrong (legal, medical, financial, client-facing), verify from a primary source before using.

### Module 2 — The RTF + Context Formula (13 min)

A known, validated structure (RTF) with one addition (Context) for real-world use.

- **R**ole — who the model should be ("You are a senior B2B copywriter with SaaS experience…")
- **T**ask — what it should do ("Rewrite this LinkedIn post to…")
- **C**ontext — what it needs to know ("The audience is CTOs at mid-market fintechs. Tone is direct, no hype. Product is a compliance automation tool.")
- **F**ormat — how to deliver ("3 variants. Each under 280 characters. Bullet points for the body. End with a single question.")

**Before/after live demo:**
- Bad: *"Write me a LinkedIn post about our product."*
- Good: full RTF + Context version. Show both outputs side by side.

**Rule of thumb:** if your prompt fits in one line, it's probably too thin.

### Module 3 — Chat Best Practices (15 min)

1. **The first prompt is load-bearing.** It sets the tone, role, and constraints for the entire thread. Invest in it.
2. **Don't scold — restate.** When output is wrong, do not say *"no, you're wrong, do it again."* That fights the agreement bias without fixing the input. Say instead: *"My instruction wasn't clear. Here is what I actually need: …"*
3. **GIGO — garbage in, garbage out.** If the answer is bad, 90% of the time the prompt is the cause, not the model.
4. **Edit upstream, not downstream.** When possible, edit the original prompt and regenerate, rather than piling corrections into a long thread.
5. **Start fresh when the thread drifts.** Long threads accumulate bad context. A clean thread with a strong first prompt often beats a 20-turn argument.
6. **Show, don't just tell.** Give one or two examples of the output you want. Examples beat adjectives.

### Module 4 — You Are the Boss (woven through, not a standalone module)

Reinforced in the wrap-up:
- Delegate like a manager: clear brief, acceptance criteria, format, deadline-equivalent (length, depth).
- Iterate: output → critique → refine.
- *"Make ChatGPT your slave"* = own the direction. The provocation is against passivity ("it gave me a bad answer"), not against the model.

## 6. Exercises

### Exercise 1 — Rewrite a Bad Prompt (15 min)

**Setup:** Provide a set of 3 weak prompts on the slide. Each pair picks one.

Example weak prompts:
- *"Write me an email about the project status."*
- *"Summarize this meeting."*
- *"Give me ideas for the product launch."*

**Task:** In pairs, rewrite using RTF + Context. Run it. Compare before/after.

**Debrief:** 2 pairs share. Facilitator highlights what made the difference.

### Exercise 2 — Real Work Task (20 min)

**Setup:** Each participant picks one actual task from their week (email, summary, analysis, draft, plan).

**Task:**
1. Build a RTF + Context prompt.
2. Run it.
3. Refine once — either by editing the original prompt OR by adding a clear restating instruction.

**Debrief:** 2–3 volunteers share their prompt + output. Facilitator calls out: did the refinement follow the "restate, don't scold" rule?

## 7. Artifacts to Produce

1. **Facilitator guide** (`facilitator-guide.md`) — timing, speaker notes, demo prompts, exercise scripts, common Q&A, edge cases, troubleshooting.
2. **Slide deck** (`slides.pptx`) — approximately 20 slides, visual, low text per slide, demo placeholders, exercise slides. Generated via `anthropic-skills:pptx`.
3. **Cheat sheet** (`cheat-sheet.pdf`) — one page, two sides:
   - Side A: RTF + Context formula, 3 reusable prompt templates, 5 best practices.
   - Side B: CO-STAR upgrade for power users, "don't scold, restate" mini-script, limits checklist.
4. **Master support doc** (`support-doc.md`) — full self-contained narrative covering all modules. Written so NotebookLM can ingest it to produce audio overview, mind map, and study guide for async review.

All four artifacts live under `training/make-chatgpt-your-slave/`.

## 8. Tone & Style

- Direct, irreverent, practical. Matches the provocative title.
- No corporate hedging. No "it depends." No "leveraging synergies."
- Short sentences. Active voice.
- Show, don't lecture. Every concept pairs with a concrete example or demo.
- Slides: visual-first, one big idea per slide, minimal text.
- Cheat sheet: designer-grade layout, printable, fridge-magnet quality.

## 9. Architecture & Boundaries

Clean separation between content types:

- **Master support doc** = single source of truth for all written content. All other artifacts derive from it.
- **Slide deck** = visual adaptation of support-doc headlines.
- **Cheat sheet** = condensed, designed reference.
- **Facilitator guide** = delivery layer (timing, cues, demos) that wraps the support-doc content.

This means: when content changes, it changes in `support-doc.md` first, then propagates. No duplication of body copy across artifacts.

## 10. Dependencies & Constraints

**Skills to use during implementation:**
- `anthropic-skills:doc-coauthoring` — for structured authoring of support doc and facilitator guide.
- `anthropic-skills:pptx` — for the slide deck.
- `anthropic-skills:pdf` — for the printable cheat sheet.
- `design:ux-copy` — for slide titles and cheat-sheet microcopy.

**External:**
- NotebookLM account (user-provided) to ingest the support doc for audio/video recap.
- Presentation software compatible with pptx (Keynote, PowerPoint, Google Slides).

**Room / delivery assumptions:**
- Participants bring laptops with ChatGPT access (free tier acceptable).
- Projector or large screen for demos.
- Wi-Fi available during session.
- No prior ChatGPT experience assumed.

## 11. Out of Scope

- Custom GPTs / GPT Builder.
- API or code-based integrations.
- Agentic workflows (Operator, Agents, tool calling).
- Model comparisons (Claude, Gemini, Mistral).
- Image generation, voice mode, Canvas.
- Multi-session series.

These may become follow-up trainings ("Advanced: Custom GPTs", "Chaining with Projects", "From Chat to Agent") but are not part of this 90-minute session.

## 12. Risks & Mitigations

| Risk | Mitigation |
|------|-----------|
| Beginners overwhelmed by power users dominating exercises | Pair them deliberately; assign roles (scribe, operator) |
| Demos fail live (rate limit, outage) | Pre-recorded backup demos in speaker notes |
| Provocative title misread as disrespectful to the model | Frame clearly in hook: "the slave here is your workflow, not the AI's dignity" |
| Session runs long | Module 1.5 and cheat-sheet walk-through are compressible; exercises are protected time |
| Confidentiality incident (participant pastes real client data into demo) | Explicit callout in Module 1.5 before any hands-on work |

## 13. Open Questions (to resolve during implementation)

- Exact wording of the three "bad prompts" for Exercise 1 — needs to be universally relatable.
- Cheat sheet layout: single-column vs two-column? Printed or digital-first?
- Visual style for slides: brand colors (if any) or neutral default?
- Should the support doc include a glossary section? Recommend yes, short.

These are refinement questions, not blockers. The implementation plan will address them.

---

**Next step:** invoke `writing-plans` skill to produce the implementation plan that builds the four artifacts.
