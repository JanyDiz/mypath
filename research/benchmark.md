# Research · Level 2 — Benchmark

## Chosen dimension: **Feedback quality & depth**

Of every dimension mypath could compete on (voice realism, question breadth, price, polish), **feedback quality is the moat** — it's the one thing the brief says *is the product*. Voice, JD-parsing, and pricing are table stakes that competitors already match; the quality of senior, rubric-anchored judgment is where the product is won or lost. So that's what we benchmark.

## Criteria (8) — what "great feedback" means here

Each scored **0–4** (0 = absent · 1 = token · 2 = basic · 3 = good · 4 = excellent).

1. **Criterion-level scoring** — score broken into named, weighted dimensions (not one number).
2. **Evidence & justification** — feedback cites the *specific* thing said and *why* it's weak/strong (the Grammarly/Speak "why").
3. **Actionability** — concrete "how to strengthen": rewrites, models, next steps — not just "be clearer."
4. **Format-specificity** — feedback differs meaningfully for portfolio walkthrough vs behavioral vs design challenge.
5. **Seniority of judgment** — assesses *reasoning, trade-offs, decision rationale* — not just delivery or STAR completeness.
6. **Rubric transparency** — the user can see the criteria/standards they're judged against.
7. **Progress over time** — improvement tracked across sessions per criterion.
8. **Constructive tone** — empowering and honest, not punitive or empty-encouraging.

## Exemplars (5) + ceilings

Benchmarked: the two hard competitors (Mockin, UXMock), the strongest soft rubric tool (Exponent), the delivery-coach baseline (Yoodli), and the aspirational craft leader (Grammarly). **Human coach (ADPList)** is shown as the judgment ceiling, not scored head-to-head.

| # | Criterion | Mockin | UXMock | Exponent | Yoodli | Grammarly | **Human coach** |
|---|-----------|:------:|:------:|:--------:|:------:|:---------:|:---------------:|
| 1 | Criterion-level scoring | 1 | 3 | 3 | 1 | 3 | 4 |
| 2 | Evidence & justification | 2 | 2 | 2 | 2 | **4** | 4 |
| 3 | Actionability | 3 | 2 | 2 | 2 | **4** | 4 |
| 4 | Format-specificity | 2 | 2 | 2 | 0 | 1 | 4 |
| 5 | Seniority of judgment | 2 | 2 | 2 | 1 | 1 | **4** |
| 6 | Rubric transparency | 1 | 3 | 2 | 1 | 2 | 3 |
| 7 | Progress over time | 1 | 3 | 2 | 3 | 3 | 1 |
| 8 | Constructive tone | 3 | 3 | 2 | 3 | **4** | 3 |
| | **Total / 32** | **15** | **20** | **17** | **13** | **22** | **27** |

*(Scores are a calibrated estimate from the live pages + research, not hands-on grading — see open question below.)*

## Reading the scores

- **No AI tool clears 22/32.** Grammarly (22) leads on *feedback craft* (justification, actionability, tone) but is domain-blind (format-specificity 1, seniority 1).
- **UXMock (20)** is the strongest *design* tool, but its rubric is generic — it scores well on transparency/progress, mid on seniority and evidence.
- **The market's two weakest columns are #4 format-specificity and #5 seniority of judgment** — exactly the moat. Nobody is above 2 on seniority. The human coach (27) wins precisely there (4/4 on both).
- **The opportunity = AI craft (Grammarly's 4s on evidence/action/tone) × human-coach judgment (4s on seniority/format).** No product combines them.

## The bar for mypath

To win the dimension, v1 must hit:

| Criterion | Target | How |
|-----------|:------:|-----|
| Criterion-level scoring | **4** | Per-criterion weighted scores from versioned rubrics (CLAUDE.md §4) |
| Evidence & justification | **4** | Every point quotes the candidate's words + names the rubric criterion it violates/meets (NN/g model) |
| Actionability | **4** | Each weakness paired with a concrete "stronger version" |
| Format-specificity | **4** | Separate rubric per (discipline × format) — the structural differentiator |
| Seniority of judgment | **4** | Senior-authored rubrics weighting *decision rationale* highest; the proprietary layer |
| Rubric transparency | **3–4** | Show the rubric + where the answer landed on it |
| Progress over time | **3** | Per-criterion trend across saved sessions |
| Constructive tone | **4** | Honest + empowering voice (Grammarly bar) |

**Target total: ≥30/32** — i.e. beat every AI tool and approach the human-coach ceiling on the two criteria the market can't do (seniority + format-specificity). That, not feature count, is the win condition.

## Open question
These are *estimated* scores from marketing pages. Before locking the bar, **hands-on test** Mockin / UXMock / Exponent feedback on a real answer to verify criteria #2 and #5 in practice (flagged in [`research.md`](./research.md)).
