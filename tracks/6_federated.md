# Track: Federated

**Fixed five-client federated protocol with required DP-accounting fields.**

| | |
|---|---|
| Public bundle units | 2,000  |
| Hidden eval | shared hidden |
| Ranking formula | **0.5 · U₁ + 0.3 · U₄ + 0.2 · U₈** with mandatory `(delta, sigma, clipping, eps)` disclosure; submissions failing DP-accounting validation are rejected without scoring. |
| Real-world setting | Privacy-preserving caregiving copilots that cannot exfiltrate session content. |

## Details

- 5 client shards: `competition/bundles/federated_client_shards_v1/`
- Submissions: per-client weight-delta tarball + DP accountant report
- Per-round compute cap published in this track's README at launch

## Shared with all other tracks

- The same prompt schema, persona-conditioned task surface, tool contract, and safety rubric apply.
- One scorer (`competition/scorer/score_submission.py`) enforces input validity and ranking.
- Hidden eval rows are schema-identical to the public bundle and stay server-side at the scorer.
- The reference UncGPT v1 baseline ([models/v1/](../models/v1/)) is the public starting point for this track.

## Submission

Format and CodaBench instructions: see the main proposal Section 2.1 and `competition/scorer/README.md`. Submission window opens 2026-07-01.
