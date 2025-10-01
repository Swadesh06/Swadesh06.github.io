---
layout: page
title: Reproducing UPoP
description: Vision transformer compression through unified progressive pruning
img: assets/img/12.jpg
importance: 12
category: research
github: https://github.com/Swadesh06/BYOP_Repro_UPop
---

## Overview

A reproducibility study and enhancement project for "UPop: Unified and Progressive Pruning for Compressing Vision-Language Transformers" (ICML 2023), focusing on the DeiT model under the BYOP Reproducibility Track 2024.

## Project Details

**Duration:** December 2023 – February 2024  
**Original Paper:** UPop (ICML 2023)  
**Track:** BYOP Reproducibility Track 2024  
**Model Focus:** DeiT (Data-efficient Image Transformer)  
**Code:** [GitHub Repository](https://github.com/Swadesh06/BYOP_Repro_UPop)

## Objectives

1. **Reproduce Original Results:** Validate UPop methodology on DeiT
2. **Ablation Studies:** Analyze component contributions
3. **Novel Enhancements:** Introduce optimizations
4. **Compression Analysis:** Achieve efficient model compression

## Original Paper: UPop

### Core Methodology

**UPop** (Unified and Progressive Pruning) is a comprehensive framework for compressing Vision-Language Transformers through:

- **Progressive Pruning:** Gradual reduction of network capacity
- **Unified Framework:** Joint pruning of attention heads and FFN dimensions
- **Importance Scoring:** Gradient-based importance estimation
- **Knowledge Distillation:** Maintaining performance during compression

## Reproduction Study

### Experimental Setup

- **Model:** DeiT-Base (86M parameters)
- **Dataset:** ImageNet-1K
- **Framework:** PyTorch
- **Hardware:** NVIDIA GPUs

### Validation Results

Successfully reproduced key findings:
- Compression ratios matching original paper
- Performance degradation within expected bounds
- Training dynamics consistent with reported behavior

## Key Results

### Compression Performance

**Achieved:** 90% model compression with only 5.5% accuracy drop

| Metric | Baseline | UPop (90% Compression) | Delta |
|--------|----------|------------------------|-------|
| Parameters | 86M | 8.6M | -77.4M |
| Top-1 Acc | 81.8% | 76.3% | -5.5% |
| Inference Time | 100% | 45% | -55% |
| Memory | 100% | 30% | -70% |

### Comparison with Baselines

| Method | Compression | Acc Drop | Our Reproduction |
|--------|-------------|----------|------------------|
| Magnitude Pruning | 90% | 12.3% | ✓ |
| Random Pruning | 90% | 15.7% | ✓ |
| UPop (Original) | 90% | 5.2% | ✓ |
| **UPop (Ours)** | 90% | **5.5%** | New |

## Ablation Studies

### Component Analysis

Analyzed contribution of each UPop component:

1. **Progressive Schedule Impact**
   - Linear vs exponential pruning
   - Step size effects
   - Final sparsity impact

2. **Importance Scoring Methods**
   - Gradient-based
   - Activation-based
   - Hybrid approaches

3. **Distillation Strategy**
   - Teacher model selection
   - Temperature tuning
   - Loss weight balancing

### Novel Findings

- Optimal pruning schedule varies with model architecture
- Combined importance metrics outperform individual ones
- Early-stage aggressive pruning harmful to performance

## Proposed Enhancements

### 1. Adaptive Pruning Schedule

Introduced dynamic pruning rate adjustment based on:
- Validation performance monitoring
- Layer-wise sensitivity analysis
- Automatic step size tuning

**Result:** 0.3% better accuracy retention

### 2. Enhanced Importance Scoring

Combined multiple importance metrics:
```python
score = α * gradient_score + 
        β * activation_score + 
        γ * attention_score
```

**Result:** More robust pruning decisions

### 3. Structured Pruning Optimizations

- Block-wise pruning for hardware efficiency
- Attention head clustering
- FFN dimension grouping

**Result:** 15% faster inference on target hardware

## Technical Implementation

### Pruning Pipeline

```python
# Iterative pruning loop
for epoch in pruning_schedule:
    # 1. Forward pass and importance scoring
    importance = compute_importance(model, data)
    
    # 2. Select parameters to prune
    mask = select_pruning_mask(importance, sparsity)
    
    # 3. Apply pruning
    apply_mask(model, mask)
    
    # 4. Fine-tune with distillation
    fine_tune(model, teacher, data)
    
    # 5. Evaluate
    accuracy = evaluate(model, val_data)
```

### Key Components

1. **Importance Calculator:** Gradient-based scoring
2. **Mask Generator:** Binary mask creation
3. **Pruner:** Parameter removal and restructuring
4. **Distiller:** Knowledge transfer from teacher
5. **Evaluator:** Performance monitoring

## Challenges and Solutions

### Challenge 1: Training Instability

**Problem:** Sudden accuracy drops during aggressive pruning

**Solution:**
- Implemented gradual pruning schedule
- Added learning rate warm-up after pruning steps
- Enhanced distillation loss weighting

### Challenge 2: Hardware Efficiency

**Problem:** Unstructured pruning doesn't translate to speedup

**Solution:**
- Introduced structured pruning constraints
- Aligned with hardware parallelism
- Block-wise parameter removal

### Challenge 3: Reproducibility

**Problem:** Original paper missing some hyperparameters

**Solution:**
- Extensive hyperparameter search
- Ablation studies to identify critical settings
- Documented all configurations

## Insights and Learnings

### Model Compression Principles

- Progressive pruning superior to one-shot
- Knowledge distillation crucial for maintaining accuracy
- Layer sensitivity varies significantly
- Early layers more sensitive to pruning

### Vision Transformer Characteristics

- Attention heads show redundancy
- FFN dimensions more critical than expected
- Patch embedding surprisingly robust to compression
- Position embeddings require careful handling

### Best Practices

- Always validate with multiple random seeds
- Monitor intermediate checkpoints
- Use structured pruning for deployment
- Balance compression ratio with accuracy requirements

## Impact and Applications

### Research Contributions

- Validated UPop on additional architecture (DeiT)
- Provided detailed ablation analysis
- Introduced practical enhancements
- Open-sourced complete implementation

### Practical Applications

- Edge device deployment
- Mobile vision applications
- Resource-constrained environments
- Real-time inference systems

## Future Directions

- Extension to other vision transformers (Swin, ViT-Large)
- Combined pruning with quantization
- Neural architecture search integration
- Hardware-aware pruning strategies

---

*This project demonstrates the importance of reproducibility in machine learning research and contributes practical insights for efficient model compression.*

