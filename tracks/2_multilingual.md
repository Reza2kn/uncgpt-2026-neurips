# Track: Multilingual

**Cross-language robustness under dominant-language drift — eleven-language balanced evaluation.**

| | |
|---|---|
| Public bundle units | 2,816  |
| Hidden eval | 1,408 |
| Ranking formula | **0.6 · language_mean + 0.4 · language_floor**. Tie-break: lower per-language variance, then stronger floor. |
| Real-world setting | A diaspora-family conversational tool that must not collapse to English mid-conversation. |

## Details

- 11 languages: en, es, zh, hi, fa, sw, fr, pt, bn, yo, tl
- Public bundle: `competition/bundles/multilingual_public_v1.parquet`
- Floor formula prevents English concentration from dominating multilingual failure

## Shared with all other tracks

- The same prompt schema, persona-conditioned task surface, tool contract, and safety rubric apply.
- One scorer (`competition/scorer/score_submission.py`) enforces input validity and ranking.
- Hidden eval rows are schema-identical to the public bundle and stay server-side at the scorer.
- The reference UncGPT v1 baseline ([models/v1/](../models/v1/)) is the public starting point for this track.

## Submission

Format and CodaBench instructions: see the main proposal Section 2.1 and `competition/scorer/README.md`. Submission window opens 2026-07-01.
