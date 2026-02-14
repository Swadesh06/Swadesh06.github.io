---
layout: page
title: CNN on FPGA for MNIST Digit Classification
description: FPGA implementation of a CNN for real-time digit inference
img: assets/img/5.jpg
importance: 5
category: course project
---

## Summary

Course project on deploying a CNN on FPGA for MNIST digit classification.

**Duration:** August 2025 -- September 2025  
**Platform:** Basys3 FPGA  
**Tools:** Xilinx Vivado

## Implementation

- Designed a resource-aware CNN suitable for Basys3 constraints.
- Implemented convolution and inference logic in hardware.
- Converted floating-point operations to fixed-point arithmetic.
- Validated latency and correctness on board.

## Engineering Focus

- LUT/DSP/BRAM budgeting.
- Timing closure and stable clock operation.
- On-chip memory management for weights and activations.
- Throughput-latency trade-off for real-time inference.

## Outcome

- Achieved real-time MNIST inference on hardware.
- Verified functional correctness on Basys3.
- Demonstrated feasibility of low-cost FPGA deployment for small CNN models.
