---
layout: page
title: PDF Answering AI
description: Local RAG pipeline for PDF question answering
img: assets/img/6.jpg
importance: 6
category: open projects
---

## Overview

Developed under the Artificial Intelligence and Electronics Society (AriES), this project implements a complete pipeline for answering user queries from PDF documents without relying on external APIs.

## Project Details

**Duration:** May 2024 – June 2024  
**Affiliation:** Artificial Intelligence and Electronics Society (AriES), IIT Roorkee  
**Role:** Student Project

## Objectives

Create a working pipeline to perform the task of answering user queries and questions from a PDF, with minimal use of internet and without external APIs.

## Technical Stack

### Core Technologies

- **Language Model:** Meta AI's LLaMA3-8B model
- **Optimization:** Unsloth library for efficient inference
- **Framework:** Langchain for pipeline orchestration
- **Embeddings:** Sentence Transformer for semantic understanding
- **Vector Database:** FAISS for efficient similarity search
- **PDF Processing:** PyMuPDFLoader for document parsing

## Architecture

### Pipeline Components

1. **Document Processing**
   - PDF text extraction using PyMuPDFLoader
   - Text chunking and preprocessing
   - Metadata extraction

2. **Embedding Generation**
   - Semantic embeddings via Sentence Transformers
   - Vector representation of document chunks
   - Efficient storage in FAISS index

3. **Retrieval System**
   - FAISS-based similarity search
   - Context-aware chunk retrieval
   - Relevance scoring

4. **Answer Generation**
   - LLaMA3-8B for natural language generation
   - Context-aware response synthesis
   - Query understanding and interpretation

## Key Features

- **Local Execution:** Runs entirely on local hardware without external API calls
- **Efficient Inference:** Optimized using Unsloth for faster response times
- **Semantic Search:** Advanced retrieval using dense embeddings
- **Scalable Architecture:** Handles large documents efficiently

## Implementation Highlights

- Minimal internet dependency for maximum privacy
- Efficient memory utilization for resource-constrained environments
- Modular design for easy extensibility
- RAG (Retrieval-Augmented Generation) architecture for accurate answers

## Applications

- Academic research assistance
- Document analysis and summarization
- Legal document querying
- Technical documentation navigation

## Impact

This project demonstrates the feasibility of building powerful AI-assisted tools using open-source models and local infrastructure, promoting accessibility and data privacy.

---

*Developed as part of AriES initiative to explore practical applications of Large Language Models in document understanding.*

