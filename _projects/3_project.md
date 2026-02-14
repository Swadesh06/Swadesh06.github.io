---
layout: page
title: Reproducing UPoP
description: Full reimplementation and ablation of Unified Progressive Pruning for Vision Transformers
img: assets/img/upop.png
importance: 12
category: research
github: https://github.com/Swadesh06/BYOP_Repro_UPop
---

## Overview

A reproducibility study of "UPop: Unified and Progressive Pruning for Compressing Vision-Language Transformers" (ICML 2023) under the DSG BYOP Reproducibility Track 2024. Since the original authors' code proved unsuitable for reproduction, the **entire algorithm and model pipeline was implemented from scratch**, followed by an extensive ablation study that went beyond the original paper's experiments.

**Duration:** December 2023 -- February 2024 | **Track:** BYOP Reproducibility Track 2024  
**Model:** DeiT-base-distilled (`facebook/deit-base-distilled-patch16-224`) | **Dataset:** CIFAR-10  
**Compute:** ~200 GPU hours across 5 Kaggle P100 instances

## UPop Algorithm: The Two Pillars

### Unified Pruning

Instead of separately pruning different structures (attention heads, FFN dimensions), UPop searches across all compressible components jointly in a continuous optimization space, automatically determining the pruning ratio for each. Z-score normalization is applied to trainable masks to handle magnitude variance across structures -- without it, the sparsity loss drives weights to exceptionally low values causing random, uncontrolled pruning.

### Progressive Pruning

Traditional two-stage pruning (search then retrain) fails at high compression ratios because pruned neurons' mask magnitudes don't converge to 0, making the sliced subnet hard to train. Progressive Pruning addresses this with a custom optimizer that gradually drives eliminated neurons' masks to zero as a function of the current iteration, ensuring stable convergence even at 90% compression.

## Key Results

**Achieved 90% model compression with only 5.5% accuracy drop** -- closely matching the original paper's reported 5.2%.

### Progressive Pruning with Different Schedules

| Compression | Linear | Sigmoid | Exp. Decay | Improvement over Mask Pruning |
| ------------- | -------- | --------- | ------------ | ------------------------------- |
| 50% | ~-3% | ~-3% | ~-4.5% | ~+3% |
| 80% | ~-6% | ~-6% | ~-5% | ~+5% |
| 90% | ~-7% | ~-7% | ~-5.5% | ~+5.5% |

Mask-based pruning became ineffective beyond 50% compression, while Progressive Pruning maintained stable convergence up to 90%.

### Component Analysis

| Configuration | Accuracy Change (0.5 comp.) | vs. Mask Pruning |
| --------------- | ---------------------------- | ------------------ |
| Progressive Only | -5% | +4% |
| Unified + Progressive | -4% | +3% |

## Ablation Study (8+ Configurations)

Experiments conducted beyond the original paper's scope:

- **Exclusion of normalization:** Caused uncontrolled sparsity loss, pushing weights to near-zero with unbounded pruning ratios reaching ~0.995
- **Exclusion of sparsity loss:** Weights retained high values past the threshold, reducing effective pruning magnitude
- **Fixed threshold binarization:** Performed inferiorly to topk but useful for maximum-compression scenarios
- **Non-linear scheduling:** Sigmoid excelled at moderate ratios (0.4-0.7), exponential decay prevailed at high ratios (~0.9), linear was best below 0.5
- **Adaptive pruning via validation accuracy:** Added +2% accuracy retention at 0.9 compression by adapting pruning rate based on epoch-to-epoch validation performance

## Challenges

The main difficulty was the full from-scratch reimplementation -- requiring extensive debugging, manual integration of unified search, progressive pruning, mask binarization, normalization, sparsity loss, and weight freezing into every layer of the DeiT model. Training 10-12 model variants simultaneously across multiple Kaggle GPU instances was necessary to complete the ablation study within time constraints.

---

*All 6 claims from the original paper were validated. The study confirms Progressive Pruning as the dominant contributor to compression quality, with Unified Search providing meaningful but secondary improvements.*
