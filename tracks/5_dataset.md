# Track: Dataset

**Data-only submissions evaluated via a fixed retrain runner with frozen seeds.**

| | |
|---|---|
| Public bundle units | 2,000  |
| Hidden eval | shared hidden |
| Ranking formula | **mean_lift**, then variance, then safety floor, then provenance-rejection rate. |
| Real-world setting | Data-recipe research for tiny caregiving models. |

## Details

- Submissions are data bundles + a YAML recipe overlay against the frozen retrain config
- Retrain runner and seeds: `proposal/dataset_retrain_config_v12.yaml`
- Five-seed panel: `proposal/dataset_signal_check_v12.md`
- Public starter: `competition/bundles/dataset_starter_public_v1.parquet`

## Shared with all other tracks

- The same prompt schema, persona-conditioned task surface, tool contract, and safety rubric apply.
- One scorer (`competition/scorer/score_submission.py`) enforces input validity and ranking.
- Hidden eval rows are schema-identical to the public bundle and stay server-side at the scorer.
- The reference UncGPT v1 baseline ([models/v1/](../models/v1/)) is the public starting point for this track.

## Submission

Format and CodaBench instructions: see the main proposal Section 2.1 and `competition/scorer/README.md`. Submission window opens 2026-07-01.
