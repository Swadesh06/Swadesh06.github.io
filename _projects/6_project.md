---
layout: page
title: PDF Answering AI
description: Local retrieval-augmented QA pipeline for PDF documents
img: assets/img/6.jpg
importance: 6
category: open projects
---

## Summary

Open project under AriES, IIT Roorkee to build a local PDF question-answering system without external API calls.

**Duration:** May 2024 -- June 2024  
**Affiliation:** Artificial Intelligence and Electronics Society (AriES), IIT Roorkee

## Stack

- **LLM:** LLaMA3-8B  
- **Optimization:** Unsloth  
- **Orchestration:** LangChain  
- **Embeddings:** Sentence Transformers  
- **Vector DB:** FAISS  
- **PDF parser:** PyMuPDFLoader

## Pipeline

1. Parse PDF and chunk text.
2. Generate dense embeddings for chunks.
3. Index vectors in FAISS.
4. Retrieve top-k relevant context for a user query.
5. Generate answer conditioned on retrieved context.

## Design Goals

- Fully local execution for privacy.
- Low dependency on internet services.
- Modular components for model and retriever swaps.
- Support for long technical documents.

## Current Status

The baseline end-to-end RAG pipeline is complete, with ongoing work on retrieval quality and answer grounding.
