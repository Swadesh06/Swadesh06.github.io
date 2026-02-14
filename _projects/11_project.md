---
layout: page
title: RISC-V Factorian Number Program
description: RISC-V assembly implementation for Factorian-number checking
img: assets/img/11.jpg
importance: 11
category: course project
---

## Summary

Assembly-level implementation in ECN-207 to check whether an integer is a Factorian number (sum of factorials of digits equals the number).

**Duration:** August 2023 -- September 2023  
**Language:** RISC-V Assembly  
**Simulator:** Ripes

## Algorithm

1. Extract digits using `div`/`rem`.
2. Compute factorial for each digit.
3. Accumulate factorial sum.
4. Compare sum with the original integer.
5. Return boolean result.

## Implementation Notes

- Modular subroutines for digit extraction and factorial computation.
- Register-discipline aligned with RISC-V calling convention.
- Stack save/restore for nested routine calls.
- Early-exit checks to limit unnecessary computation.

## Validation

Tested with known cases (`1`, `2`, `145`, `40585`) and non-Factorian values. Step-through debugging in Ripes was used to verify register and control-flow correctness.

## Outcome

- Correct checker implementation for tested inputs.
- Improved fluency with low-level control flow, stack handling, and arithmetic routines in RISC-V.
