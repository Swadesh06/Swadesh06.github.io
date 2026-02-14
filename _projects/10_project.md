---
layout: page
title: TLB and Page Table Simulation
description: Virtual memory translation simulation in C++
img: assets/img/10.jpg
importance: 10
category: course project
---

## Summary

Course project in ECN-207 (Computer Architecture) implementing a virtual-memory translation pipeline with TLB and page-table integration.

**Duration:** October 2023  
**Language:** C++

## Components

- TLB with configurable size/associativity and replacement policy.
- Multi-level page table for virtual-to-physical mapping.
- MMU translation flow with TLB lookup, page walk, and TLB update.

## Experiments

- Sequential and random access traces.
- Working-set based traces.
- Context-switch scenarios with TLB invalidation.
- Policy comparisons (LRU/FIFO/Random).

## Metrics

- TLB hit rate.
- Page fault rate.
- Effective memory access latency.
- Translation overhead.

## Outcome

- Demonstrated expected performance gains from TLB caching.
- Measured sensitivity of hit rate to TLB size and workload locality.
- Built a reusable simulation base for extended memory-system studies.
