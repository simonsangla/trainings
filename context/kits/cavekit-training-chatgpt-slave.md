---
created: "2026-04-20"
last_edited: "2026-04-20"
---

# Cavekit: training-chatgpt-slave

## Scope

This cavekit defines the requirements for the "Make ChatGPT Your Slave" training package: a single 90-minute, hands-on session for a mixed-skill audience that teaches a realistic mental model of large language models, a reusable prompt formula, a small set of chat best practices, and a non-negotiable list of limits and ethics. Scope covers all delivery artifacts (master support content, slide deck, facilitator guide, cheat sheet, exercises, feedback form) and the async distribution channel built from the master support content.

## Requirements

### R1: Session structure and timing
**Description:** The training is delivered as a single 90-minute session, divided into eight contiguous timed blocks that together cover all teaching content and both hands-on exercises, sized for a mixed-skill audience of 10–30 participants.
**Acceptance Criteria:**
- [ ] Total session length is exactly 90 minutes from start to wrap.
- [ ] The session is divided into eight contiguous, non-overlapping timed blocks.
- [ ] The eight blocks cover, in order: hook plus mental model; limits and ethics; prompt formula teaching; exercise 1; chat best practices; exercise 2; cheat sheet walk-through plus power-user teaser; Q&A and wrap.
- [ ] Each block has a defined start time, end time, and assigned slide range.
- [ ] The audience descriptor explicitly states "mixed" (beginners through power users) and a participant range of 10–30.
- [ ] Exercise 2 is allocated 20 minutes and is flagged as protected time that must not be cut short.
- [ ] Exercise 1 is allocated 15 minutes.

### R2: Mental model content
**Description:** The training teaches a concrete, non-mystical mental model of what a large language model is and isn't, including the next-token prediction mechanism, tokens, the context window, the absence of cross-session memory, and the absence of tools (web, code, private data) unless explicitly enabled.
**Acceptance Criteria:**
- [ ] The model is described as a next-token predictor (predicts the most likely next token given prior tokens) and not as a search engine, database, or reasoning oracle.
- [ ] A token is defined with a concrete approximate ratio to a word (roughly three quarters of a word).
- [ ] The context window is defined as the working memory the model can see at once, with the explicit consequence that anything outside it is forgotten.
- [ ] The absence of memory across sessions is stated, with the qualifier that prior content must be reintroduced to be visible.
- [ ] The absence of web access, code execution, and access to private data is stated, with the qualifier "unless a tool is explicitly enabled and given access".
- [ ] A reusable plain-language metaphor for the model is provided (e.g. "smart intern with amnesia") and reused at least once in delivery cues.
- [ ] A one-sentence takeaway expresses that the model produces plausible text and that plausible is not the same as true.

### R3: Limits and ethics content
**Description:** The training presents a fixed, numbered set of non-negotiable limits and ethics rules covering hallucination, confidentiality of pasted data, ownership and originality of outputs, and a fact-check rule for load-bearing claims.
**Acceptance Criteria:**
- [ ] Exactly four rules are presented and labelled non-negotiable.
- [ ] Rule 1 states that hallucination is to be assumed and that facts, citations, statistics, and quotes may be invented.
- [ ] Rule 2 prohibits pasting client data, personally identifiable information, passwords, credentials, or confidential documents into consumer ChatGPT and directs sensitive work to enterprise-approved tooling.
- [ ] Rule 3 states outputs are usable but originality is not guaranteed and directs a check for unintentional paraphrasing for public-facing work.
- [ ] Rule 4 (the fact-check rule) requires verification from a primary source for any answer whose error could cause real damage (legal, medical, financial, client-facing, regulatory).
- [ ] The confidentiality rule is reinforced verbally before any hands-on work begins.

### R4: RTF + Context prompt formula
**Description:** The training teaches a single primary prompt formula — Role, Task, Context, Format — with a definition, a bad example, and a good example for each component, plus a complete before/after demonstration.
**Acceptance Criteria:**
- [ ] All four components (Role, Task, Context, Format) are defined.
- [ ] Each of the four components has at least one paired bad and good example.
- [ ] A single end-to-end "before" prompt and "after" prompt are provided that demonstrate all four components together.
- [ ] A rule of thumb is stated that a one-line prompt is almost certainly too thin.
- [ ] The formula is referred to consistently as "RTF + Context" across all artifacts.

### R5: Chat best practices
**Description:** The training teaches a numbered list of chat best practices: the first prompt is load-bearing; don't scold — restate; garbage in, garbage out; edit upstream rather than piling on corrections; start a fresh thread when the current one drifts; show with examples rather than relying on adjectives.
**Acceptance Criteria:**
- [ ] Exactly six best practices are presented as a numbered list in the master content.
- [ ] The "first prompt is load-bearing" practice is stated with the framing that upfront investment saves downstream time.
- [ ] The "don't scold — restate" practice contrasts a wrong move ("No, that's wrong, do it again") with a right move ("My instruction was not clear. Here is what I actually need: …").
- [ ] The "garbage in, garbage out" practice attributes most bad outputs to the prompt rather than to the model.
- [ ] The "edit upstream" practice instructs editing the original message and regenerating, rather than appending corrections to a long thread.
- [ ] The "start fresh when the thread drifts" practice instructs opening a new thread with a strong first prompt when output quality decays.
- [ ] The "show, don't just tell" practice instructs pasting examples in place of style adjectives.
- [ ] The line "the fix is always upstream, in the request" is present and reinforced in delivery cues.

### R6: Ownership framing
**Description:** The training threads an ownership/agency frame — "you are the boss; the model is the worker; bad orders equal bad work" — through opening, body, and closing, and gives the participant explicit manager-style behaviours to perform.
**Acceptance Criteria:**
- [ ] The opening of the session states the provocation that the participant, not the model, is the agent in the room.
- [ ] A dedicated module presents at least four delegation behaviours (brief clearly; set acceptance criteria; iterate critically; capture and reuse winning prompts).
- [ ] A closing line restating the boss/worker frame ("bad orders equal bad work" or equivalent) is present in the wrap content.
- [ ] The cheat sheet contains a single one-line restatement of the boss/worker frame.

### R7: Exercise 1 — rewrite a bad prompt
**Description:** A 15-minute paired exercise where participants rewrite a deliberately weak prompt using RTF + Context, run both the original and the rewrite, and compare outputs.
**Acceptance Criteria:**
- [ ] Exercise duration is stated as 15 minutes and the format is stated as pairs.
- [ ] Exactly three weak prompt options are offered, covering distinct task types (a status email, a meeting summary, a launch brainstorm).
- [ ] Numbered instructions direct participants to: pick one option, rewrite using RTF + Context, run both versions, compare side by side, and prepare to share.
- [ ] At least three debrief questions are provided.
- [ ] The meeting summary option includes guidance to use a redacted real transcript or fabricate a short one (consistent with the confidentiality rule).

### R8: Exercise 2 — real work task
**Description:** A 20-minute solo exercise where participants build an RTF + Context prompt for a real task from their own week, run it, refine it once using the "restate, don't scold" rule, and optionally share.
**Acceptance Criteria:**
- [ ] Exercise duration is stated as 20 minutes and the format is stated as solo with optional sharing.
- [ ] Numbered instructions direct participants to: pick one real task, build an RTF + Context prompt, run it, identify one or two specific issues, refine once (either by editing the original prompt or by restating).
- [ ] The refinement step explicitly forbids saying "that's wrong" and requires either editing upstream or restating with the phrase "My instruction wasn't clear. What I actually need is: …" or equivalent.
- [ ] A self-check section asks at minimum: did the first prompt include all four of R, T, C, F; did the refinement restate or argue; would the prompt be reused.
- [ ] A share segment is defined for two or three volunteers.

### R9: Cheat sheet deliverable
**Description:** A single-page, two-sided printable reference. Side A holds the primary RTF + Context content with reusable templates and the best-practices summary. Side B holds the CO-STAR power-user framework, the "don't scold, restate" mini-script, a limits checklist, and the one-line ownership rule.
**Acceptance Criteria:**
- [ ] The cheat sheet is one physical page, printed double-sided.
- [ ] Side A contains: definitions of R, T, C, F; at least three reusable prompt templates (covering at minimum email, summary, and draft/plan task types); a five-item best-practices list (deliberately a condensed subset of the six practices in R5 — the cheat sheet merges "edit upstream" and "start fresh" into a single practice).
- [ ] Side B contains: the six CO-STAR letters with definitions; a "don't scold, restate" mini-script with a wrong example and a right example; a limits checklist of at least four self-check questions; a one-line ownership rule.
- [ ] The CO-STAR letters covered are exactly: Context, Objective, Style, Tone, Audience, Response.
- [ ] One copy is available per participant at the session.

### R10: Slide deck deliverable
**Description:** A 20-slide, low-text, visual-first deck where each slide carries one idea, one headline, and at most one or two supporting lines. Slide order matches the timing block sequence.
**Acceptance Criteria:**
- [ ] The deck is exactly 20 slides.
- [ ] Each slide has one headline expressing a single idea and at most two supporting body lines.
- [ ] Slides 1–5 cover title, what-the-session-is, and the mental model content.
- [ ] Slides 6–7 cover limits and ethics, including a dedicated confidentiality callout.
- [ ] Slides 8–11 cover the RTF + Context formula, including a before/after slide.
- [ ] Slide 12 introduces exercise 1; slide 17 introduces exercise 2.
- [ ] Slides 13–16 cover the chat best practices.
- [ ] Slides 18–19 cover the cheat sheet walk-through and CO-STAR teaser.
- [ ] Slide 20 is the wrap, containing a closing line and a placeholder for the async distribution link.
- [ ] The slide range allocated to each timing block in R1 matches the slide ranges defined here.

### R11: Master support document deliverable
**Description:** A single master written document that holds all teaching content and is the single source of truth for every other artifact. It is structured to be ingested standalone by an external tool and used to generate async distribution materials.
**Acceptance Criteria:**
- [ ] The document is a single file containing all teaching modules end to end.
- [ ] The document includes: core premise; mental model module; limits and ethics module; RTF + Context module; chat best practices module; ownership module; CO-STAR appendix; glossary; further reading.
- [ ] The glossary defines at minimum: token, context window, hallucination, prompt, thread, system prompt, agreement bias.
- [ ] The further reading section includes at minimum three external references with URLs.
- [ ] The document reads as a self-contained standalone artifact (does not require the slides or facilitator guide to be understandable).
- [ ] The document is identified in the package as the source from which slide outline, cheat sheet sides, and async distribution materials are propagated.

### R12: Facilitator guide deliverable
**Description:** A delivery-layer document that does not duplicate the master content but layers timing, speaker notes per block, demo cues, common Q&A, troubleshooting, and pre-/post-session checklists on top of it.
**Acceptance Criteria:**
- [ ] A timing table lists every one of the eight blocks from R1 with start/end times, slide range, and a one-line note.
- [ ] Each of the eight blocks has a dedicated speaker-notes section with at least one delivery cue or live demo instruction.
- [ ] At least one explicit "say verbatim or close" line is provided for the opening.
- [ ] A closing line is provided for the wrap block.
- [ ] A common Q&A section contains at minimum seven question/answer pairs covering: model version, model-portability of the formula, pasting company data, prompt length, politeness words, refusals, and detecting hallucinations.
- [ ] A troubleshooting section covers at minimum: demo failure or outage, a dominating participant, a lost beginner, exercise 2 running short, a participant pasting real client data.
- [ ] A pre-session checklist of at least six items is provided.
- [ ] A post-session checklist of at least three items is provided.
- [ ] The guide explicitly states it does not repeat the master content and directs the reader to read the master content first.

### R13: Exercise materials
**Description:** Stand-alone exercise files exist on disk, one per exercise, containing duration, goal, instructions, options or task framing, and debrief or self-check.
**Acceptance Criteria:**
- [ ] An exercise 1 file exists with: duration, goal, numbered instructions, the three weak prompt options, and at least three debrief questions (per R7).
- [ ] An exercise 2 file exists with: duration, goal, numbered instructions including the refine-once-via-restate step, a share segment, and a self-check (per R8).
- [ ] Both files are referenced from the facilitator guide as the source pointed to during the kickoff of each exercise.

### R14: Feedback form
**Description:** A short feedback form, available as either a printed handout or a digital short-form, asking exactly three structured questions plus an optional contact field.
**Acceptance Criteria:**
- [ ] The form contains exactly three questions.
- [ ] Question 1 asks for one concrete behaviour change the participant will make next week.
- [ ] Question 2 asks which module landed best and which was weakest.
- [ ] Question 3 asks for an overall rating on a 1–5 scale with anchors at both ends (1 = waste of time; 5 = changed how I work).
- [ ] An optional contact field for follow-up is present.
- [ ] The form is suitable for either print or short digital form delivery.

### R15: Tone
**Description:** All written and spoken content is direct, irreverent, practical, and free of corporate filler.
**Acceptance Criteria:**
- [ ] No artifact uses the words "leverage", "synergy", or "unlock" as filler verbs/nouns.
- [ ] No artifact opens or closes with hedging filler ("just wanted to", "I think maybe", "we feel that").
- [ ] The provocation in the title is preserved across artifacts (the package title is "Make ChatGPT Your Slave" and is not softened).
- [ ] Imperatives are used in instructions and best practices (e.g. "rewrite", "verify", "start fresh") rather than passive constructions.

### R16: Async distribution
**Description:** The master support document is set up to be fed into an external knowledge-notebook tool that produces a defined set of async-consumption artifacts, and the resulting share link is referenced in the session wrap and post-session follow-up.
**Acceptance Criteria:**
- [ ] The package documents that the master support document is the input ingested for async distribution.
- [ ] The set of async artifacts to be generated is enumerated and includes at minimum: an audio overview, a video overview, a study guide, a mind map, and a briefing doc.
- [ ] The wrap slide (slide 20) reserves a placeholder for the share link.
- [ ] The pre-session checklist requires the notebook to be generated and the share link to be tested before the session.
- [ ] The post-session checklist requires the share link to be sent in the follow-up email along with the cheat sheet.

## Out of Scope

The following are explicitly NOT covered by this cavekit and must not be added without an explicit scope expansion:

- Custom GPTs (creation, configuration, or distribution of GPT Store-style assistants).
- API or code integrations (using ChatGPT or any LLM via API, SDK, or programmatic access).
- Agentic workflows (multi-step autonomous agents, tool-use orchestration, function-calling pipelines).
- Model comparisons (head-to-head benchmarking of ChatGPT against Claude, Gemini, Mistral, or others beyond the single Q&A note that the formula is portable).
- Multi-session training series (this kit defines a single 90-minute session only).
- Image generation, voice mode, and Canvas-style features of ChatGPT.

## Cross-References

This kit currently stands alone in the project. As future kits are added, link them here. Within this kit, requirements cross-reference each other as follows:

- R1 (timing) anchors block sequencing referenced by R10 (slide ranges) and R12 (facilitator timing table).
- R3 (limits and ethics) is reinforced operationally by R7 (exercise 1 redaction guidance) and by the troubleshooting entry in R12.
- R4 (formula) is the content reused by R7, R8, R9 (side A), and R10 (slides 8–11).
- R5 (best practices) is reused by R8 (refine-once-via-restate), R9 (side A list and side B mini-script), and R10 (slides 13–16).
- R6 (ownership) bookends R1 (opening and wrap blocks) and is summarised on R9 (side B one-line rule).
- R11 (master support doc) is the source artifact referenced by R10, R9, and R16.
- R13 (exercise materials) is referenced operationally by R12 (kickoff cues for each exercise).
- R16 (async distribution) consumes R11 and is referenced in R10 (slide 20) and R12 (pre/post checklists).

## Source Traceability

Requirements were derived by reverse-engineering these existing artifacts in the working repository:

- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/README.md` → R11 (artifact relationships), R16 (async distribution pipeline).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/support-doc.md` → R2 (mental model module), R3 (limits & ethics module), R4 (RTF + Context module), R5 (best practices module), R6 (ownership module), R9 (CO-STAR appendix content), R11 (master document structure, glossary, further reading), R15 (tone exemplars).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/facilitator-guide.md` → R1 (timing table and audience), R12 (speaker notes, Q&A, troubleshooting, pre/post checklists), R3 (verbal confirmation cue), R6 (opening provocation, closing line).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/slides/outline.md` → R10 (20 slides, headlines, slide-to-block mapping).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/cheat-sheet/side-a.md` → R9 (side A: RTF + Context, three templates, five best practices).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/cheat-sheet/side-b.md` → R9 (side B: CO-STAR, mini-script, limits checklist, one-line rule).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/exercises/exercise-1-prompts.md` → R7 (exercise 1), R13 (exercise material file).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/exercises/exercise-2-instructions.md` → R8 (exercise 2), R13 (exercise material file).
- `/Users/simonsangla/projects/trainings/training/make-chatgpt-your-slave/assets/feedback-form.md` → R14 (feedback form).

## Changelog

- 2026-04-20 — Initial draft. Reverse-engineered from the existing training package on disk.
