# mypath

> AI interview prep, built for designers and product managers — not generic "all roles" coaching.

Paste a job description (and optionally your resume), pick a session format, and rehearse with realistic, role-tailored questions. Answer by voice or text and get **senior-level, rubric-based feedback**: where your answer is weak, what to strengthen, how to structure it, and a score against clear criteria. Sessions are saved so you can see progress over time.

**Why it's different:** most interview tools are generic (all roles, soft skills, or delivery analytics). mypath is narrow on purpose — it focuses on **design and product interview formats** (portfolio walkthrough, behavioral, design challenge) and grades answers against a **rubric that encodes a senior designer's judgment**. That feedback quality is the product.

🚧 **Status:** early development — planning complete, building toward a first release.

---

## Repo index

This repo holds the **design & product work** for mypath. Each folder has its own README with details.

| Folder | What's inside |
|--------|---------------|
| 📄 [`CLAUDE.md`](./CLAUDE.md) | **Source of truth** — full product brief, locked decisions, stack, and v1 rubric drafts |
| 🔍 [`research/`](./research/) | Competitive landscape, pricing benchmarks, rubric frameworks → [`research.md`](./research/research.md); reference screenshots in [`screens/`](./research/screens/) |
| ✏️ [`wireframes/`](./wireframes/) | Low/mid-fidelity layouts and user flows |
| 💡 [`concept/`](./concept/) | Product concept, positioning, brand/tone direction |
| 🎨 [`tokens/`](./tokens/) | Design tokens (color, type, spacing, motion) — single source of visual primitives |
| 🧩 [`components/`](./components/) | Individual UI component designs and specs |
| 📐 [`design-system/`](./design-system/) | Assembled, documented system: tokens + components + usage rules |
| 🚚 [`handoff/`](./handoff/) | Engineering-ready specs, redlines, exported assets |

**Pipeline:** `research` → `concept` → `wireframes` → `tokens` → `components` → `design-system` → `handoff`.

---

## Product at a glance

1. **Paste a JD** (+ optional resume)
2. **Pick a format** — portfolio walkthrough, behavioral, or design challenge
3. **Get tailored questions** for that role and format
4. **Answer** by voice or text
5. **Get senior-level feedback** — per-criterion scores, evidence, and how to strengthen each answer
6. **Track progress** across saved sessions

### Roadmap (v1 → fast-follow)
- **v1:** Design discipline · portfolio walkthrough + behavioral · async (text + voice-to-text) · rubric-based scoring · saved sessions + progress
- **Next:** design challenge → product-management discipline → portfolio upload (visual review) → real-time live voice interview

### Tech stack
Next.js (App Router) + Tailwind · Supabase (auth/DB/storage) · Claude API (question gen + evaluation) · Stripe (subscription + job-cycle pass) · speech-to-text (TBD) · Vercel.

---

## License

Proprietary — all rights reserved (for now).
