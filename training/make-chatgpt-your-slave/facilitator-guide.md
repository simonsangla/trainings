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
- [ ] Screenshots of good/bad prompt outputs saved locally as an outage fallback (narrate from the images if ChatGPT is unreachable).
- [ ] NotebookLM notebook generated from `support-doc.md` ahead of time. Notebook URL pasted into slide 20 wrap text and into the closing script below. Test the share link works.
- [ ] Feedback form (`assets/feedback-form.md`) printed or linked as a short digital form.
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

Share the NotebookLM link: https://notebooklm.google.com/notebook/977f6c56-73d1-4c8a-b873-de51c86634d7 (audio overview, video, study guide, mind map, briefing doc — all generated from `support-doc.md`). Pass the optional feedback form.

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

**Demo fails / rate limit / outage:** switch to the screenshot fallback you prepared in the pre-session checklist. Narrate what the prompt would have produced. Don't apologize at length — just pivot.

**A participant dominates:** acknowledge them, then explicitly invite quieter voices. "Let's hear from someone who hasn't spoken yet."

**A beginner is lost during an exercise:** pair them with a power user as "scribe". The power user operates, the beginner directs. Both learn.

**Exercise 2 runs short on time:** extend by 5 minutes. Cut the cheat-sheet walk-through to two minutes instead. Protect the hands-on work.

**Someone pastes real client data:** pause the exercise. Remind the room of the confidentiality rule. Do not shame the person — the rule is subtle and easy to forget.

---

## Post-Session

- [ ] Send follow-up email with NotebookLM link and cheat sheet PDF.
- [ ] Post winning prompts from Exercise 2 (anonymized, with permission) as a shared internal resource.
- [ ] Collect feedback forms. Note which module needs tightening next time.
