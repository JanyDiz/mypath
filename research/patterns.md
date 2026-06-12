# Research · Level 3 — Patterns

Five **fundamentally different** interaction patterns for mypath's core loop — *answer a question → get senior feedback*. These are not variations of one idea; each implies a different architecture, cost profile, and feel. Then: one chosen for the project context, argued.

---

### Pattern A — Real-time live voice interview
A synchronous AI interviewer "calls" you: speaks, listens, interrupts, follows up live; feedback at the end.
- **Feels like:** the real thing. Highest realism + pressure.
- **Cost/complexity:** highest — low-latency STT↔LLM↔TTS loop, turn-taking, barge-in.
- **In the wild:** UXMock, Yoodli live nudges.
- **Risk:** UXMock owns this; latency/cost hurts feedback depth; intimidating for early practice.

### Pattern B — Conversational chatbot
Turn-based **text** chat: AI asks, you type, it probes, repeat. Feedback inline or at the end.
- **Feels like:** messaging an interviewer. Low friction, cheap.
- **Cost/complexity:** low.
- **Risk:** typing ≠ how design/portfolio answers are actually delivered (spoken); easy to over-edit; feels less like real prep.

### Pattern C — Async record → graded report
You **record (voice) or type** a full answer to a prompt, submit, and get a **structured rubric report** (per-criterion scores + evidence + rewrites). No live pressure; depth happens server-side.
- **Feels like:** submitting a take-home and getting a senior review back.
- **Cost/complexity:** moderate; STT is async (cheap, no latency budget); all compute goes into deep evaluation.
- **In the wild:** Mockin (report), Google Interview Warmup (lightweight).
- **Risk:** less "live realism" — but realism isn't the moat; *feedback depth* is.

### Pattern D — Inline annotation / document critique
The answer (a transcript, or an uploaded case study) is shown as a document, and feedback is **anchored inline** to specific spans — Grammarly-style margin notes tied to rubric criteria.
- **Feels like:** a senior marking up your work in the margins.
- **Cost/complexity:** moderate; needs span-mapping of feedback to text.
- **In the wild:** Grammarly (aspirational).
- **Risk:** weaker as a *practice* loop on its own (it's a feedback *presentation*, not a question-asking flow).

### Pattern E — Guided structured wizard
A step-by-step scaffold walks you *through a framework* (e.g. CIRCLES steps, or portfolio STAR arc) field by field, coaching at each step before a final score.
- **Feels like:** training wheels / a worksheet.
- **Cost/complexity:** low–moderate.
- **Risk:** great for teaching structure, but too rigid to *rehearse* a real, free-form answer; can feel like form-filling.

---

## Chosen: **Pattern C (async record → graded report), with Pattern D as the feedback view**

For mypath's v1 context — *design discipline, portfolio walkthrough + behavioral, async, depth-first, moat = senior feedback* — **C is the right spine**, presented through **D**.

### Why C
1. **It matches the locked strategy.** v1 is explicitly async and depth-first (CLAUDE.md §3). C *is* that pattern; A would mean fighting UXMock on its home turf.
2. **It maximizes the moat.** Async removes the latency budget, so 100% of model effort goes into deep, multi-criterion rubric evaluation — the thing we must score ≥30/32 on ([`benchmark.md`](./benchmark.md)). Real-time (A) trades feedback depth for immediacy; we won't make that trade in v1.
3. **It fits the usage pattern.** Prep is bursty and self-paced (record an answer between other tasks, get a report) — better than scheduling a live session, and a natural fit for the job-cycle pass model.
4. **Voice without the cost.** Recording captures how answers are *actually* delivered (spoken), but async STT is cheap and has no latency requirement — best of both.
5. **Lower build risk to first paying users.** No real-time infra; ship the core value sooner.

### Why D layered on top
The report shouldn't be a wall of text. Anchoring each rubric finding **inline to the exact words** (Grammarly model) is how we make *senior judgment legible* — and legible justification is criterion #2 of the benchmark and a core differentiator vs. competitors' generic summaries.

### What we deliberately defer
- **Pattern A (real-time live voice)** → premium phase-2 differentiator once feedback depth is proven (already in the fast-follow roadmap).
- **Pattern E (guided wizard)** → optional "coach mode" / training-wheels toggle for nervous juniors, layered on C later.
- **Pattern B** → not pursued; spoken async (C) better reflects real design/portfolio delivery.

**One-line rationale:** *Async record → deep rubric report, shown as inline margin critique — it spends every dollar of compute on the feedback depth that is the product, avoids UXMock's owned real-time lane, and fits bursty, self-paced prep.*
