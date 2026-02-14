---
layout: page
title: IEEE Signal Processing Cup, ICASSP 2025
description: Deepfake detection using EfficientNet ensembles and multi-transform inputs
img: assets/img/12.jpg
importance: 1
category: research
github: https://github.com/Swadesh06/DFWild_Cup
---

## Summary

Research project for the [IEEE Signal Processing Cup, ICASSP 2025](https://2025.ieeeicassp.org/sp-cup/) DFWild-Cup challenge on deepfake detection.

**Duration:** September 2024 -- February 2025  
**Role:** Team Member  
**Advisor:** [Vinod Pankajakshan](https://faculty.iitr.ac.in/~sparshfec/), IIT Roorkee

## Method

- Built a 4-model ensemble: EfficientNetB4, EfficientNetB4+Attention, EfficientNetV2-S+Attention, and EfficientNetB4-CSMT.
- Used multi-transform inputs in CSMT: RGB + Fourier magnitude + Haar wavelet edge map + steerable pyramid output.
- Added channel-spatial attention to improve artifact localization.
- Used chunk-based training on limited hardware (16GB P100), with gradient accumulation.

## Results

| Metric | Value |
| --- | --- |
| AUC | 97.39% |
| Accuracy | 94.04% |
| F1 Score | 94.02% |
| EER | 5.40% |
| DCF | 0.0509 |
| Inference Speed | 0.0163 s/image (~61 img/s) |

The ensemble improved over the best individual model by +0.52% AUC and reduced EER by 22.5%.

## Documentation

- [Technical Report](https://github.com/Swadesh06/DFWild_Cup/blob/main/Technical_report.pdf)
