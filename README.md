# Somali Informal Text Normalization: Pilot Evaluation

## Overview

This project explores whether normalizing informal Somali social-media text helps small open-weight language models interpret its intended meaning.

The work is motivated by spelling variation, abbreviations, informal expressions, and emoji use in Somali digital communication.

## Research Question

Does normalizing informal Somali social-media text improve model interpretation compared with using the original text?

## Models Evaluated

- Qwen3-1.7B
- Qwen2.5-3B-Instruct

## Pilot Methodology

A pilot sample of 19 Somali comments was selected from a larger thesis dataset. Each comment was evaluated in its original and normalized form, giving 38 inputs per model.

Human-reviewed English reference meanings were prepared for the sample. Model predictions were saved, and a simple text-based screening rule was used to flag possible instruction-following failures and expressions of uncertainty.

## Files

- `qwen3_1_7b_paired_results.csv` — Qwen3-1.7B predictions.
- `qwen2_5_3b_paired_results.csv` — Qwen2.5-3B-Instruct predictions.
- `somali_model_comparison.csv` — Combined model predictions.
- `somali_model_screening_summary.csv` — Preliminary screening counts.

## Preliminary Findings

Qwen3-1.7B frequently generated unrelated text or commentary about the translation task. Qwen2.5-3B-Instruct often expressed uncertainty about Somali inputs.

The preliminary screening flagged different numbers of outputs for original and normalized text. These flags are not translation accuracy scores, and the pilot does not establish that normalization improves performance.

## Limitations

- The pilot includes only 19 comments.
- Model predictions have not yet been systematically human-scored for translation accuracy.
- Some reference meanings and normalized Somali texts require further verification.
- The screening method is heuristic and has not been validated as an accuracy metric.

## Future Work

1. Human-score translations against reference meanings.
2. Validate normalized Somali text.
3. Evaluate results by spelling variation, abbreviation, and other text characteristics.
4. Expand the evaluation sample and document reproducible testing procedures.

## Research Context

This pilot supports ongoing research into lexical normalization for Somali social-media text and the evaluation of language models for low-resource languages.
