# Somali Informal Text Normalization: Pilot Evaluation

## Overview

This pilot investigates whether normalizing informal Somali social-media text helps small open-weight language models translate its intended meaning. The motivation comes from spelling variation, abbreviations, informal expressions, and emoji use in Somali digital communication.

## Research question

Does normalizing informal Somali social-media text improve model interpretation compared with using the original text?

## Models and sample

- Qwen3-1.7B
- Qwen2.5-3B-Instruct
- 19 Somali comments, each tested in original and normalized form for both models
- 76 model predictions in total (19 comments × 2 input forms × 2 models)
- Human-reviewed English reference meanings and human judgments for each prediction

## Human evaluation method

Each prediction was judged against the reference meaning using three categories:

- **Correct** — conveys the reference meaning adequately.
- **Partially correct** — captures some meaning but misses or changes important information.
- **Incorrect** — does not convey the reference meaning, is unrelated, or does not provide a usable translation.

These judgments were supplied by the researcher. The pilot is small and the labels should be interpreted as an initial manual evaluation, not a benchmark-quality score.

## Human evaluation results

| Model | Input type | Incorrect | Partially correct | Correct | Total |
|---|---|---:|---:|---:|---:|
| Qwen3-1.7B | Original | 17 | 2 | 0 | 19 |
| Qwen3-1.7B | Normalized | 17 | 2 | 0 | 19 |
| Qwen2.5-3B-Instruct | Original | 17 | 1 | 1 | 19 |
| Qwen2.5-3B-Instruct | Normalized | 16 | 2 | 1 | 19 |
| **All predictions** | **All types** | **67** | **7** | **2** | **76** |

Across all predictions, 67/76 (88.2%) were rated incorrect, 7/76 (9.2%) partially correct, and 2/76 (2.6%) correct.

In this sample, Qwen3-1.7B had identical category counts for original and normalized inputs. For Qwen2.5-3B-Instruct, the normalized set had one fewer incorrect prediction and one additional partially correct prediction, with the number of correct predictions unchanged. This is a small descriptive result only; it does not establish that normalization generally improves performance. Paired item-level outcomes and reference quality should be checked before making stronger claims.

## Preliminary observations

Qwen3-1.7B often generated unrelated text or commentary about the translation task rather than a translation. Qwen2.5-3B-Instruct frequently expressed uncertainty about informal Somali input. The results suggest that these two models struggled on many examples in this pilot, including normalized inputs.

A separate text-based screening rule flagged possible instruction-following failures and uncertainty. Those heuristic flags are not translation accuracy scores and are distinct from the human judgments reported here.

## Files

- `qwen3_1_7b_paired_results.csv` — Qwen3-1.7B predictions.
- `qwen2_5_3b_paired_results.csv` — Qwen2.5-3B-Instruct predictions.
- `somali_model_comparison.csv` — Combined model predictions and reference meanings.
- `somali_model_screening_summary.csv` — Preliminary heuristic screening counts.
- `human_evaluation_ratings.csv` — Human judgments for the 76 unique model/input predictions. Rows are keyed by comment ID, model, and input type.

## Limitations

- The pilot includes only 19 comments and is not representative of all Somali dialects, platforms, or topics.
- Reference meanings and normalized Somali text may need further verification, especially where meaning depends on context.
- The word `saxiix` (ID 4089) is context-dependent; the supplied reference meaning reflects the particular context reviewed by the researcher.
- The sample includes mixed content, emoji tokens, code-switching, and technical language; these factors have not been isolated experimentally.
- The results are descriptive and should not be generalized to all open-weight models or to Somali NLP broadly.
- No significance test or broad causal claim about normalization is made from this small pilot.

## Future work

1. Verify reference translations and normalization decisions, ideally with an additional Somali reviewer.
2. Compare original and normalized outcomes pair by pair and analyze cases where normalization changes a model response.
3. Expand the sample and stratify examples by spelling variation, abbreviations, emoji use, and code-switching.
4. Document the prompts, inference settings, and evaluation procedure for reproducibility.
5. Explore data curation and supervised training using paired informal/normalized Somali text while preserving meaning and context.

## Research context

This pilot supports ongoing research into lexical normalization for Somali social-media text and evaluation of language models for low-resource languages. It is an exploratory study, not a claim that the current normalization method is already effective.
