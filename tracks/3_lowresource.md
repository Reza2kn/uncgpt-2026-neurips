# Track: Low-Resource

**Sparse-language depth with explicit low-resource flooring.**

| | |
|---|---|
| Public bundle units | 1,920  |
| Hidden eval | 960 |
| Ranking formula | **0.7 · language_score + 0.3 · robustness_score**. Tie-break: lower variance across eligible languages. |
| Real-world setting | Language-preserving conversational tools for under-served communities. |

## Details

- Eligible languages: bn, fa, sw, yo, tl
- Public bundle: `competition/bundles/lowresource_public_v1.parquet`
- Partial submissions accepted (e.g., only a subset of eligible languages) — scored on the submitted subset without penalty

## Shared with all other tracks

- The same prompt schema, persona-conditioned task surface, tool contract, and safety rubric apply.
- One scorer (`competition/scorer/score_submission.py`) enforces input validity and ranking.
- Hidden eval rows are schema-identical to the public bundle and stay server-side at the scorer.
- The reference UncGPT v1 baseline ([models/v1/](../models/v1/)) is the public starting point for this track.

## Submission

Format and CodaBench instructions: see the main proposal Section 2.1 and `competition/scorer/README.md`. Submission window opens 2026-07-01.
