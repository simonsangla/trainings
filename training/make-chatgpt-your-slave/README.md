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
