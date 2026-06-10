# DesignPrep

> AI interview prep, built for designers and product managers — not generic "all roles" coaching.

Paste a job description (and optionally your resume), pick a session format, and rehearse with realistic, role-tailored questions. Answer by voice or text and get **senior-level, rubric-based feedback**: where your answer is weak, what to strengthen, how to structure it, and a score against clear criteria. Sessions are saved so you can see progress over time.

## Why it's different

Most interview tools are generic — all roles, general soft skills, or delivery analytics (pacing, filler words). DesignPrep is narrow on purpose: it focuses on **design and product interview formats** (portfolio walkthrough, behavioral, design challenge) and grades answers against a **rubric that encodes a senior designer's judgment** of what makes a strong answer. That feedback quality is the product.

## Status

🚧 Early development — planning complete, building toward a first release. Working name; subject to change.

## How it works

1. **Paste a JD** (+ optional resume)
2. **Pick a format** — portfolio walkthrough, behavioral, or design challenge
3. **Get tailored questions** generated for that role and format
4. **Answer** by voice or text
5. **Get senior-level feedback** — per-criterion scores, evidence, and how to strengthen each answer
6. **Track progress** across saved sessions

## Roadmap (v1 → fast-follow)

- **v1:** Design discipline · portfolio walkthrough + behavioral · async (text + voice-to-text) · rubric-based scoring · saved sessions + progress
- **Next:** design challenge → product-management discipline → portfolio upload (visual review) → real-time live voice interview

## Tech stack

- **Frontend:** Next.js (App Router) + Tailwind CSS
- **Auth / DB / storage:** Supabase
- **AI:** Claude API (question generation + answer evaluation)
- **Speech-to-text:** TBD (voice answers)
- **Payments:** Stripe (subscription + job-cycle pass)
- **Hosting:** Vercel

## License

Proprietary — all rights reserved (for now).
