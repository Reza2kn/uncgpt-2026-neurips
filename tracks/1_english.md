# Track: English

**Utility baseline under constrained compute and tool discipline.**

| | |
|---|---|
| Public bundle units | 2,048  |
| Hidden eval | 512 |
| Ranking formula | **utility_mean + tool_exact_mean − safety_penalty_mean**. Tie-break: higher tool_exact_mean, then lower safety_penalty_mean. |
| Real-world setting | An English-language caregiver companion on commodity hardware. |

## Details

- English-only public bundle: `competition/bundles/english_public_v1.parquet`
- Hidden eval: 512 schema-identical rows held server-side at the scorer
- Compute cap: 1,024 generated tokens per turn, 64 turns per conversation, 30 min wall-clock on the standardized A100 environment

## Shared with all other tracks

- The same prompt schema, persona-conditioned task surface, tool contract, and safety rubric apply.
- One scorer (`competition/scorer/score_submission.py`) enforces input validity and ranking.
- Hidden eval rows are schema-identical to the public bundle and stay server-side at the scorer.
- The reference UncGPT v1 baseline ([models/v1/](../models/v1/)) is the public starting point for this track.

## Submission

Format and CodaBench instructions: see the main proposal Section 2.1 and `competition/scorer/README.md`. Submission window opens 2026-07-01.
