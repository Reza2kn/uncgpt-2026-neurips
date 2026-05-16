# Semantic non-collapse analysis

Synthetic data pipelines often produce text that looks diverse on the surface but collapses to a few clusters in embedding space. We test for collapse on both the persona pool and the conversation pool, before and after subtracting per-language centroids.

## Method

1. Embed each persona description / each conversation transcript with a sentence-transformer.
2. Project to 2-D with PCA (and a UMAP variant for atlases).
3. Color by an axis the data is **supposed** to vary on (language, care, skill, gender, culture, value, trait, crisis profile).
4. Repeat after subtracting per-language centroids to expose non-language structure.

## Persona pool — 1,000,069 personas

The curated atlas (PCA + structured layout):

![persona atlas](../figures/persona/00_atlas.png)

The pool spreads across all colored axes — no axis collapses to a single blob:

![by language](../figures/persona/02_by_language.png)

![language centroids](../figures/persona/03_language_centroids.png)

![culture x gender](../figures/persona/04_by_culture_gender.png)

![language x crisis](../figures/persona/05_by_language_crisis.png)

Language is the dominant axis in raw embeddings (expected for multilingual text). After per-language centering, **non-language axes remain meaningfully separated**:

![language-centered density](../figures/persona/06_language_centered_density.png)

![language-centered HEXACO](../figures/persona/07_language_centered_by_hexaco.png)

## Conversation pool — 4,761 conversations

![conversation atlas](../figures/conversation/00_atlas.png)

PCA by care level (warm / mid / cold separate meaningfully):

![by care](../figures/conversation/01_by_care.png)

PCA by language (11 languages separate):

![by language](../figures/conversation/02_by_language.png)

After per-language centering, **care level still separates**:

![language-centered by care](../figures/conversation/03_language_centered_by_care.png)

And **skill axes still separate** as well, which is the strongest non-collapse signal — there's no a-priori reason for 69 distinct caregiving skill axes to land in different parts of embedding space unless the data actually carries that variation:

![language-centered by skill](../figures/conversation/04_language_centered_by_skill.png)

## Numerical summary

The persona release publishes a [`similarity_noncollapse_summary.json`](https://huggingface.co/datasets/Reza2kn/uncgpt-personas/blob/main/figures/v3/semantic/similarity_noncollapse_summary.json) artifact reporting cohort-vs-self similarity quantiles for the persona pool. The conversation summary is reproduced from `summary.json` in the per-cohort audit directories shipped with each Hugging Face dataset.

## Reproducing

The embedding, projection, and chart-generation scripts live in [`Reza2kn/KakoVerse`](https://github.com/Reza2kn/KakoVerse) under the semantic analysis directory. Inputs are the public Hugging Face datasets; outputs are the PNGs in [`figures/`](../figures/).
