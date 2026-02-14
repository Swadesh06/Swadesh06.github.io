---
layout: page
title: IEEE Signal Processing Cup, ICASSP 2025
description: Deepfake Detection via Multi-Transform Ensemble with Custom Attention
img: assets/img/12.jpg
importance: 1
category: research
github: https://github.com/Swadesh06/DFWild_Cup
---

## Overview

A team research project for the [IEEE Signal Processing Cup, ICASSP 2025](https://2025.ieeeicassp.org/sp-cup/) DFWild-Cup challenge, targeting robust deepfake detection in real-world scenarios. Our pipeline leverages an ensemble of four specialized EfficientNet variants, each with custom attention mechanisms and tailored input processing.

**Duration:** September 2024 -- February 2025 | **Role:** Team Member  
**Advisor:** [Vinod Pankajakshan](https://faculty.iitr.ac.in/~sparshfec/), Associate Professor, Vision and Image Processing Lab -- IIT Roorkee

## Technical Approach

### Ensemble Architecture

Our system combines four specialized models, each capturing different aspects of deepfake artifacts:

1. **EfficientNetB4 Baseline** -- Standard 224x224 backbone leveraging ImageNet-pretrained features
2. **EfficientNetB4 with Attention** -- Integrates a simplified attention mechanism after the 3rd MBConv block (at 28x28x56 feature depth), enabling focused artifact detection while retaining spatial detail
3. **EfficientNetV2-S with Attention** -- Operates at 256x256 resolution with squeeze-excitation and added attention for finer detail capture
4. **EfficientNetB4-CSMT** -- Our most sophisticated variant: **Channel-Spatial Attention with Multiple Transforms**. Accepts 308x308x6 inputs combining RGB, Fourier magnitude spectrum, Haar wavelet edge maps, and Steerable Pyramid transform outputs

### Multi-Transform Input Processing

The CSMT model processes six input channels through complementary transforms:

- **Fourier Transform** -- frequency domain analysis for spectral artifact detection
- **Haar Wavelet Transform** -- edge maps highlighting manipulation boundaries
- **Steerable Pyramid Transform** -- multi-scale derivative analysis for subtle inconsistencies

This multi-domain approach detects artifacts invisible in any single representation.

### Memory-Efficient Training

Trained on a 16GB P100 GPU with 30GB RAM using a chunk-based strategy -- processing 4,000 images per chunk with gradient accumulation (effective batch size of 128). The full ensemble of ~79M parameters trains within 24-30 hours on publicly available Kaggle GPUs.

## Results

| Metric | Value |
| -------- | ------- |
| **AUC** | 97.39% |
| **Accuracy** | 94.04% |
| **F1 Score** | 94.02% |
| **EER** | 5.40% |
| **DCF** | 0.0509 |
| **Inference Speed** | 0.0163 s/image (~61 img/s) |

The ensemble achieves +0.52% AUC and -22.5% EER improvement over the best individual model, with near-uniform weight distribution (std: 0.0007) indicating strong complementarity across the four architectures.

## Documentation

**Technical Report:** [Project Report](https://github.com/Swadesh06/DFWild_Cup/blob/main/Technical_report.pdf)
