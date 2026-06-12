# mypath — Project Brief & Decisions

> Interview-prep web app, narrowly focused on **design (UX/UI/product) and product-management** roles.
> Project name: mypath. Status: planning complete; design repo structured and pushed to GitHub (SSH). Last updated: 2026-06-12.

## 1. Product

The user pastes a **job description** (+ optional resume), picks a **session format**, gets **AI-generated tailored questions**, answers by **voice or text**, and receives **senior-level, rubric-based feedback with per-criterion scoring**. Sessions are saved; progress is tracked over time.

**Goal:** Take the product from zero to production and get the first paying users.

**Audience:** Designers (and PMs) looking for full-time or part-time jobs. English UI, global market.

## 2. Differentiator (the moat)

The **deepest, most senior, criterion-justified feedback** across all three design/PM formats in one JD-driven flow. The quality of the rubric *is* the product — not grammar polishing, not delivery analytics, not STAR templating.

Competitive reality (from research, June 2026): competitors already have *some* rubric, so the bet is **DEPTH of judgment**, not "rubrics exist nowhere."
- **UXMock.io** — design-challenge focus, real-time voice, generic 6-dimension rubric. *Owns live voice.*
- **Mockin** — UX/UI & product designers, STAR/behavioral lean, portfolio checker, voice. ~15k users.
- **Exponent** — strong rubric-based AI grading, but not design-specialized; PM-strong.
- **Yoodli** — general AI speaking coach; delivery analytics only (pacing, filler words).
- **ADPList** — free human 1:1 coaching (design portfolio + PM cases) — the "good enough and free" alternative.
- Paid human coaching: $100–300/session — the value anchor.

## 3. Locked decisions

### Scope by phase
- **v1 (first shippable, payable):** Design discipline only · **Portfolio walkthrough + Behavioral** · **async** (text + voice-to-text) · versioned criterion-level rubric feedback · saved sessions · simple progress view.
- **Fast-follow order:** Design challenge (async, NN/g-anchored) → PM discipline (CIRCLES-anchored) → Portfolio *upload* (multimodal, factors in actual visuals) → Real-time live voice call (premium).
- Lead with judgment depth, **not** live voice (UXMock already owns live voice).

### Pressure mechanics
The product trains **delivery under constraint**, not edited writing.
- **Per-question timer** with format-specific defaults: portfolio walkthrough **5 min/question**, behavioral **3 min/question**.
- **Voice answers committed on submit** — no re-record within a session.
- **Text answers committed on submit** — no infinite editing.
- **"Practice mode"** (no timer, re-record allowed) available for the first 1–2 sessions of a new user, then locked behind an explicit toggle.

### Monetization
- **Free tier:** 1 full session per format, with the rubric visible **read-only** — users feel the depth of judgment without getting the value loop for free. Progress view shows lifetime trends only **after the first paid session**.
- **Subscription** ~$12–15/mo + discounted annual.
- **Job-cycle one-time pass** ~$30–45 — because prep is burst usage (intense for weeks, then abandoned); a pure sub would churn hard.
- Market benchmark: AI tools cluster $8–25/mo, free tiers everywhere, annual is the discount lever.

### Stack
- **Frontend/host:** Next.js (App Router) + Tailwind on Vercel.
- **Auth/DB/storage:** Supabase (Postgres + Auth + storage for resumes/portfolio files); row-level security for user isolation.
- **LLM:** Claude API (question generation + rubric evaluation).
- **Payments:** Stripe (subscription + one-time pass as separate products; webhook → entitlement flag).
- **STT:** TBD — decide Deepgram vs Whisper at the voice phase. Async transcription only in v1 (no real-time).
- **Privacy:** JD/resume are sensitive — encrypt at rest, clear deletion path, exclude from model training.

## 4. The rubric (proprietary core)

Stored as **versioned, structured data** (NOT buried in prompts). One rubric per **(discipline × format)**. Each rubric = weighted **criteria**, each with name, weight, and strong-vs-weak descriptors. The evaluator returns, per criterion: **score + evidence quote from the answer + a specific "strengthen-this" note**, then a weighted overall.

Public anchors: **NN/g heuristic evaluation** (design challenge — every critique justified against a named principle) and **CIRCLES Method** (PM cases — 7 steps + 6 evaluation criteria). These are *answer-structuring* frameworks, not validated scoring rubrics — adapting them into a scoring engine is the user's senior judgment layer. The user is a senior designer and refines all AI-drafted rubric content.

### Open rubric questions (pending user's senior review)
1. Decision rationale weighted highest (25%) in both rubrics — confirm or re-weight.
2. STAR demoted to a 10% "floor" in behavioral, with judgment (25%) as the real bar — confirm.
3. Scoring scale: 0–4 per criterion (Missing/Weak/Adequate/Strong/Exceptional) rolled to weighted /100 + letter band — vs. /10 per criterion. Decide.
4. Any missing criteria the user would probe (handling pushback, design-craft depth, systems thinking).

### Rubric draft 1 — Design · Portfolio Walkthrough
*Narration-only in v1 (visuals not scored).*

| # | Criterion | Weight | Strong | Weak |
|---|-----------|--------|--------|------|
| 1 | Problem framing | 20% | Frames real user/business problem, constraints, what success meant — before solution | "So I designed…", no context, success undefined |
| 2 | Role & ownership clarity | 15% | Crisp on what *they* did vs. team; honest about collaboration | Vague "we"; over-claims or hides contribution |
| 3 | Decision rationale | 25% | *Why* over *what*; alternatives + trade-offs; tied to goals | Describes screens with no reasoning; "it looked better" |
| 4 | Impact & metrics | 20% | Concrete outcomes (quant/qual), honest attribution | No outcome, or inflated/unmeasured claims |
| 5 | Reflection & growth | 10% | What they'd change, what failed, what they learned | "It went great, no issues" |
| 6 | Communication & structure | 10% | Clear arc, right depth, doesn't ramble | Disorganized, too deep or too shallow |

### Rubric draft 2 — Design · Behavioral
*Senior judgment, not just STAR completeness — STAR is the floor, not the bar.*

| # | Criterion | Weight | Strong | Weak |
|---|-----------|--------|--------|------|
| 1 | Situation relevance & stakes | 15% | Relevant, appropriately hard situation; stakes set fast | Trivial example, or rambling setup |
| 2 | Specificity & ownership | 20% | Concrete first-person actions; real detail | Generic/hypothetical; hides behind team |
| 3 | Judgment & reasoning | 25% | Shows *how they thought* — tensions weighed, why this call | Recites events with no insight |
| 4 | Collaboration & influence | 15% | Navigates stakeholders/conflict; influences without authority | Avoids conflict, blames, or "I just told them" |
| 5 | Outcome & accountability | 15% | Honest result incl. what went wrong; owns it | Only wins; no accountability |
| 6 | Structure & clarity (STAR floor) | 10% | Easy to follow; complete arc, not robotic | Missing pieces or mechanical recitation |

### Rubric iteration loop (the actual moat)
Every evaluation is stamped with `rubric_version`. Users can flag per-criterion disagreement on any evaluation ("this score is wrong"); flags + internal review feed a **weekly rubric review by the senior designer**. New rubric versions are published as **v1.1, v1.2…** (immutable history); old evaluations remain visible against the rubric they were scored under.

**Why this is the moat, not the rubric content.** The rubric document itself is replicable by any senior designer in ~2 weeks. What is *not* replicable is the **closed-loop machinery** that detects evaluator drift, surfaces edge cases, and ships rubric updates faster than competitors can react. Without this, the depth advantage decays to zero within ~6 months.

## 5. Architecture sketch

Data model: `users` · `rubrics` (versioned) · `sessions` (user, JD, resume ref, format, status) · `questions` (session, prompt, source rubric) · `answers` (question, text/transcript, audio ref) · `evaluations` (answer, per-criterion scores JSON, overall, feedback, **`rubric_version`**) · `flags` (evaluation, criterion, user note — feeds the rubric iteration loop) · `subscriptions/entitlements` (Stripe).

### Build order to first paying users
1. Scaffold + auth + DB schema
2. JD/resume intake → question generation (one format first)
3. Answer capture (text, then voice→STT)
4. **Rubric engine + evaluation UI** ← most effort here; it's the product
4b. **Evaluator review tooling (internal)** — per-criterion flagging on the user side, override + rubric-diff interface on the admin side, so the v1.0 → v1.1 cycle is operational *before* public launch. **Don't ship without this** — feedback-quality bug-fixing is otherwise blind.
5. Session save + progress view
6. Second format (behavioral)
7. Stripe (sub + pass) + free-tier gating
8. Polish, responsive pass, landing page → ship → recruit first users

## 6. Repository

- **Local path:** `/Users/user/mypath/`
- **GitHub remote (origin):** `https://github.com/JanyDiz/mypath.git`
- **Default branch:** `main`
- **Git identity:** jonyyug <jonyyug@gmail.com> (GitHub username: `JanyDiz`)
- **Tooling:** Homebrew available; `gh` (GitHub CLI) NOT installed.

### Structure (design repo)
`research/` (research.md + screens/) · `wireframes/` · `concept/` · `tokens/` · `components/` · `design-system/` · `handoff/`. README.md is the living index. Pipeline: research → concept → wireframes → tokens → components → design-system → handoff.

### Auth & push
- **Pushed to GitHub over SSH.** Remote is `git@github.com:JanyDiz/mypath.git`; `main` tracks `origin/main`.
- Auth uses the local `~/.ssh/id_rsa` key (RSA), registered on the `JanyDiz` GitHub account. Normal `git push` works from `/Users/user/mypath`.
