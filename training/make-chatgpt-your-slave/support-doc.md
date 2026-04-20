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
