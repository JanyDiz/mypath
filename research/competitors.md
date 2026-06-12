# Research · Level 1 — Competitors

Three tiers of competition for **mypath**, collected June 2026 via **live page fetch (WebFetch)** + **Playwright screenshots** (see [`screens/`](./screens/)). Tiers: **Hard** (head-to-head, same job + same audience), **Soft** (same job, solved differently / adjacent), **Aspirational** (different domain, but the experience bar we want to match).

> Method note: feature/pricing claims are from each vendor's own live pages (June 2026) and are self-reported — treat user counts and quality claims as marketing. Screenshots in `screens/` are the captured state of each homepage.

---

## 🔴 Hard competitors — direct, design/PM-specific AI prep

### Mockin — `mockin.work` ([screenshot](./screens/mockin.png))
- **Audience:** UX/UI & Product Designers, Junior → Design Manager.
- **Formats:** One-Question, Screening, Assessment mock interviews; 200+ designer questions; dynamic AI follow-ups ("thinks and follows up based on your answers"); **STAR-method** oriented; multi-language voice practice.
- **Adjacent tools:** Portfolio Checker (vs "design-manager expectations"), Resume Checker/Builder, LinkedIn Checker, Job Matcher.
- **Feedback:** AI report with gaps + actionable rewrites; score (e.g. "7/10"). No video/audio recording; EU servers (GDPR).
- **Pricing:** Free = Resume Builder only; PRO = $9 day-pass / $25 mo / $45 3-mo (unlimited attempts).
- **Strength:** Broadest design career toolkit; real follow-ups; brand traction (~15k users claimed). **Weakness:** STAR/behavioral lean; feedback depth on *design judgment* unproven; no design-challenge format.

### UXMock.io — `uxmock.io` ([screenshot](./screens/uxmock.png))
- **Audience:** UX/product designers prepping **whiteboard / design challenges**, early → senior.
- **Formats:** **Real-time voice** AI interviewer (15/30/45/60 min) with dynamic follow-ups; **JD → role-specific design challenge** generator; industry prompt library (fintech, health, travel…); wireframe/sketch upload review.
- **Feedback:** 6-dimension rubric — Problem Understanding · Structure & Process · Communication · UX Thinking & Design · Product & Business · Problem Solving — each /10 + Overall; full transcripts; session history.
- **Pricing:** Free Basic = 3 sessions/mo (30 min, general prompts); Pro = $12.99/mo (15 sessions, JD targeting); credit add-ons; 1-mo trial.
- **Strength:** **Owns real-time voice + design challenge**; clean rubric; JD-tailoring. **Weakness:** Rubric is *generic* (same 6 dims for everything); no portfolio-walkthrough or behavioral focus; no PM track.

---

## 🟡 Soft competitors — same job, solved differently

| Tool | What it is | Why it's adjacent (not direct) |
|------|-----------|-------------------------------|
| **Exponent** (`tryexponent.com`, [shot](./screens/exponent.png)) | AI mock interviews w/ **hiring-rubric grading** (communication, problem-solving, structured thinking), audio + transcript, 10–20 min | Strong rubric mechanic + PM coverage, but **not design-specialized** (no portfolio/critique/challenge); paid-only AI feedback |
| **Yoodli** (`yoodli.ai`, [shot](./screens/yoodli.png)) | General AI **speaking coach**; async reports + real-time in-interview nudges | Coaches **delivery** (pacing, filler words), not design/PM *judgment*; role-agnostic |
| **Google Interview Warmup** (`grow.google`, [shot](./screens/google-warmup.png)) | Free; talk through questions (incl. UX design), AI transcribes + highlights terms/talking points/speech patterns | Free + low-friction, but shallow: terms & filler analysis, **no scoring or judgment** |
| **ADPList** (`adplist.org`, [shot](./screens/adplist.png)) | **Free human** 1:1 coaching; 133+ mentor hiring-managers; covers design portfolio + PM/case | Real senior judgment & blind-spot catching — but scheduling-bound, variable, not on-demand/scalable |

**Pricing anchor:** paid human mock coaching is **$100–300/session** (ADPList undercuts everyone at free-but-scheduled). AI tools cluster **$8–25/mo**.

---

## 🟢 Aspirational — the experience bar (different domain)

| Product | What we aspire to copy |
|---------|------------------------|
| **Grammarly** (`grammarly.com`, [shot](./screens/grammarly.png)) | **Feedback craft**: inline, categorized suggestions, each *justified* ("why"), tone/goal awareness, multi-dimensional score instead of one grade — and "without losing your authentic voice." This is the gold standard for making feedback *legible and trusted*. |
| **Speak** (`speak.com`, [shot](./screens/speak.png)) | **Voice practice + diagnostic feedback**: "talk out loud, get instant feedback"; praised for explaining the *"why" an expression is awkward* — depth over correction. Plus a personalized, adaptive curriculum. |
| **Duolingo** (no shot — reference) | **Habit & progress**: streaks, visible skill progression, low-friction daily loop — the retention model that turns burst prep into a habit. |

---

## Comparison matrix

| | **Mockin** | **UXMock** | **Exponent** | **Yoodli** | **Google Warmup** | **ADPList (human)** | **→ mypath (target)** |
|---|---|---|---|---|---|---|---|
| **Tier** | Hard | Hard | Soft | Soft | Soft | Soft | — |
| **Audience** | Designers | Designers | PM/SWE/DS | Any role | Any role | Design+PM | **Designers (then PM)** |
| **JD-tailored Qs** | Job Matcher | ✅ challenge | partial | generic | ❌ | per-mentor | **✅ core** |
| **Portfolio walkthrough** | Checker only | ❌ | ❌ | ❌ | ❌ | ✅ human | **✅ v1 focus** |
| **Behavioral** | ✅ (STAR) | ❌ | ✅ | ✅ | ✅ basic | ✅ | **✅ v1 focus** |
| **Design challenge** | ❌ | ✅ live | ❌ | ❌ | ❌ | ✅ | fast-follow |
| **Voice** | async | **real-time** | async audio | both | record | live human | **async v1**, real-time later |
| **Scoring** | score 7/10 | 6-dim /10 | rubric/attr | delivery only | none | qualitative | **per-criterion + evidence** |
| **Rubric depth** | STAR-shallow | generic 6-dim | solid, generic | n/a | n/a | senior (human) | **senior, format-specific** ← moat |
| **Progress over time** | partial | ✅ history | partial | ✅ | ❌ | ❌ | **✅** |
| **Pricing** | $9–45 | $12.99/mo | paid | $8–20/mo | free | free* | **~$12–15/mo + job pass** |
| **Threat** | 🔴 high | 🔴 high | 🟡 med | 🟢 low | 🟢 low | 🟡 med | — |

\* ADPList free but scheduling-bound.

## So what (implications for mypath)

1. **The wedge is depth, not novelty.** Rubrics already exist (UXMock, Exponent). We win by being **format-specific + senior-judgment-deep + evidence-justified** — the Grammarly/Speak "explain the *why*" bar applied to design/PM answers.
2. **Don't fight UXMock on live voice.** They own real-time + design challenge. Lead async, depth-first, on **portfolio walkthrough + behavioral** — formats no hard competitor nails.
3. **Beat Mockin on judgment.** Their portfolio/STAR feedback is the bar to clear; our criterion-level evidence-based feedback is how.
4. **Steal the experience bar from aspirational tier:** inline justified feedback (Grammarly), "why it's weak" depth (Speak), habit/progress loop (Duolingo).
