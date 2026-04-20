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
