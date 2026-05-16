# UncGPT 2026 — NeurIPS Competition

**Six preregistered tracks on one persona-conditioned caregiving benchmark, evaluated on a shared scorer and a hidden eval cohort.**

- Submission identity: [openreview.net/profile?id=~Reza_Sayar1](https://openreview.net/profile?id=~Reza_Sayar1)
- Hugging Face collection (datasets, reference checkpoints, browser demo Space): [Reza2kn/uncgpt-2026-neurips-competition](https://huggingface.co/collections/Reza2kn/uncgpt-2026-neurips-competition-6a081d4a2a5645643dc999b4)
- Hugging Face org: [huggingface.co/Reza2kn](https://huggingface.co/Reza2kn)
- WebGPU browser demo: [Reza2kn/uncgpt-69-hybrid-demo](https://huggingface.co/spaces/Reza2kn/uncgpt-69-hybrid-demo)

## Tracks

| # | Track | Public bundle | Hidden units |
|---|---|---:|---:|
| 1 | English | 2,048 | 512 |
| 2 | Multilingual (11 languages) | 2,816 | 1,408 |
| 3 | Low-Resource (bn, fa, sw, yo, tl) | 1,920 | 960 |
| 4 | Empathic / Disability-Care | 1,024 | 512 (192 manual-review cap) |
| 5 | Dataset (fixed retrain recipe) | 2,000 | shared hidden |
| 6 | Federated (5 clients, DP) | 2,000 | shared hidden |

## Substrate

- **Personas**: 1,000,069 rows (public; `Reza2kn/uncgpt-personas`)
- **Names**: 15,000 with zero gaps (public; same dataset)
- **Live gold conversations**: 4,761 across 11 languages, 69 skill axes, 1,587 each warm/mid/cold care, mean 17.89 turns, 85,194 total turns (public; `Reza2kn/uncgpt-conversations-v7-69-total`)
- **Reference small model**: **UncGPT v1** — 71M-parameter hybrid (Hymba parallel attention + Mamba2 + BitNet-quantized MoE), 12 layers, d_model 448, 6 routed experts + 1 shared, top-k 2. Sub-100M, browser-runnable. Smoke checkpoint public; full-pass weights mirror at launch.

## Status

This repository is the GitHub companion to the NeurIPS 2026 Competition Track proposal. Starter notebooks, the public scorer, baseline scorecards, and reproduction scripts will be released here at acceptance.

For active generation/training infrastructure, see [`Reza2kn/KakoVerse`](https://github.com/Reza2kn/KakoVerse).

## License

Datasets: see individual Hugging Face dataset cards. Code: Apache-2.0. Documentation: CC-BY-4.0.
