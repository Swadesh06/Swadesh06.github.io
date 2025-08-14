---
layout: page
title: Reproducing UPoP
description: Vision-Language Transformer Compression Research
img: assets/img/7.jpg
importance: 3
category: work
---

## Overview

This reproduction study focused on "UPop: Unified and Progressive Pruning for Compressing Vision-Language Transformers," originally published at ICML 2023. The project was conducted as part of the BYOP Reproducibility Track 2024.

## Project Details

**Duration:** December 2023 – February 2024  
**Track:** BYOP Reproducibility Track 2024  
**Target Model:** DeiT (Data-efficient image Transformers)  
**Code Repository:** [GitHub](https://github.com/Swadesh06/BYOP_Repro_UPop)

## Research Objectives

1. **Reproducibility:** Faithfully reproduce the original UPoP results for DeiT models
2. **Enhancement:** Introduce optimizations and improvements to the original methodology
3. **Analysis:** Conduct extensive ablation studies to understand the method's effectiveness

## Key Achievements

### Performance Results
- Achieved **90% model compression** with only **5.5% accuracy drop**
- Successfully reproduced the original paper's core findings
- Demonstrated the effectiveness of progressive pruning in Vision-Language Transformers

### Technical Contributions
- Implemented unified pruning strategy for both vision and language components
- Developed progressive compression pipeline that maintains model performance
- Conducted comprehensive ablation studies on pruning strategies
- Introduced enhancements for better optimization convergence

## Methodology

### Unified Pruning Strategy
Implemented a cohesive approach to prune both vision and language transformer components simultaneously, maintaining the balance between modalities.

### Progressive Compression
Developed a gradual pruning schedule that allows the model to adapt to reduced capacity over multiple stages.

### Optimization Enhancements
Introduced novel optimizations to improve the convergence properties of the compressed models.

## Impact

This work contributes to the field of efficient AI by demonstrating practical approaches to compress large Vision-Language models while maintaining their performance, making them more accessible for deployment in resource-constrained environments.

---

*This project was part of the BYOP Reproducibility Track, emphasizing the importance of reproducible research in machine learning.*
