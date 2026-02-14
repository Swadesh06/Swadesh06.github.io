---
layout: page
title: Reproducing UPoP
description: Reimplementation and ablation of Unified Progressive Pruning for vision transformers
img: assets/img/12.jpg
importance: 12
category: research
github: https://github.com/Swadesh06/BYOP_Repro_UPop
---

## Summary

Reproducibility study of **UPop: Unified and Progressive Pruning for Compressing Vision-Language Transformers (ICML 2023)** under the DSG BYOP track.

**Duration:** December 2023 -- February 2024  
**Model:** DeiT-base-distilled (`facebook/deit-base-distilled-patch16-224`)  
**Dataset:** CIFAR-10  
**Compute:** ~200 GPU hours (Kaggle P100)

## Implementation

- Reimplemented the full pipeline from scratch because the original codebase was not usable for replication.
- Implemented both UPop components:
  - **Unified Pruning:** joint mask search across structures.
  - **Progressive Pruning:** iterative pruning schedule for stable convergence at high sparsity.
- Ran ablations for normalization, sparsity loss, thresholding, and pruning schedules.

## Main Results

| Compression | Accuracy Drop | Gain vs. mask pruning |
| --- | --- | --- |
| 50% | ~3% | ~+3% |
| 80% | ~6% | ~+5% |
| 90% | ~5.5-7% (schedule-dependent) | ~+5.5% |

At 90% compression, the reproduced setup reached ~5.5% drop, close to the original report (~5.2%).

## Additional Findings

- Sigmoid schedule worked better at moderate compression.
- Exponential-decay schedule was stronger near 90% compression.
- Validation-driven adaptive pruning improved retention at high compression.

## Code

- [GitHub Repository](https://github.com/Swadesh06/BYOP_Repro_UPop)
