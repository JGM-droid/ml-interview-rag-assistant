# Machine Learning Interview RAG Assistant

Retrieval-Augmented Generation (RAG) study assistant for machine learning interview preparation.

## 30-Second Overview

- Problem: help interview candidates answer ML and DS technical questions from a curated knowledge base.
- Approach: chunk Markdown study docs, embed with Sentence Transformers, index in ChromaDB, answer with a Hugging Face QA model.
- Scope: notebook-first implementation focused on retrieval quality, confidence gating, and source attribution.
- Status: implemented prototype with documented evaluation in the notebook.

## What Is Implemented

- Knowledge base in `docs/` covering:
  - ML fundamentals
  - Data preprocessing
  - Feature engineering and encoding
  - Supervised learning
  - Model evaluation
  - Neural networks and deep learning
  - Computer vision
  - NLP, embeddings, and RAG
- End-to-end RAG workflow in `ml_interview_rag_assistant.ipynb`:
  - Markdown document loading
  - Configurable chunking with overlap
  - Embedding generation
  - ChromaDB vector retrieval
  - Extractive QA answer generation
  - Confidence-based fallback behavior
  - Source attribution in responses
- Structured test runs and reflection sections documented in the notebook.

## What This Project Is Not

- Not a production deployment.
- Not a web service or API package.
- Not a benchmark-optimized system.

This repository is intentionally a transparent, educational engineering artifact that demonstrates design tradeoffs and implementation choices.

## Engineering Decisions

1. Notebook-first architecture
  - Chosen to make each pipeline stage observable and reviewable end-to-end.

2. Markdown files as source-of-truth for the knowledge base
  - Keeps domain content separated from code and easier to maintain.

3. Vector retrieval with ChromaDB
  - Lightweight local vector store suitable for prototyping retrieval behavior.

4. Extractive QA model for answer generation
  - Prioritizes a straightforward baseline over more complex generative pipelines.

5. Confidence thresholding
  - Reduces unsupported answers by returning a fallback when model confidence is low.

## Repository Structure

```text
ml-interview-rag-assistant/
├── ml_interview_rag_assistant.ipynb
├── README.md
├── requirements.txt
├── docs/
│   ├── 01_ml_fundamentals.md
│   ├── 02_data_preprocessing.md
│   ├── 03_feature_enginering_encoding.md
│   ├── 04_supervised_learning.md
│   ├── 05_model_evaluation.md
│   ├── 06_nueral_networks_deep_learning.md
│   ├── 07_computer_vision.md
│   ├── 08_nlp_rag.md
│   └── README.md
└── code/
  └── prototype_v1/
    └── results/
      └── active_editor_state.json
```

Note: a few file names preserve original course naming (including spelling) for consistency with existing project artifacts.

## Setup

### 1. Create and activate a virtual environment

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

macOS/Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Launch Jupyter

```bash
jupyter notebook
```

Open `ml_interview_rag_assistant.ipynb` and run cells in order.

## How To Review Quickly (Recruiter/Hiring Manager)

1. Read this README for scope and decisions.
2. Open `ml_interview_rag_assistant.ipynb` and inspect:
  - Chunking implementation
  - Retrieval setup
  - `RAGAssistant` class
  - Comprehensive testing and analysis sections
3. Scan `docs/` to evaluate domain coverage and source quality.

## Limitations

- Answer generation uses an extractive QA model, which can return short phrases.
- No automated unit/integration test suite in this version (evaluation is notebook-based).
- Single-notebook implementation; packaging and service layers are future work.

## Potential Next Improvements

- Add automated tests for chunking and retrieval behavior.
- Add experiment tracking and repeatable evaluation scripts.
- Compare extractive QA baseline with a generative answer model.

## Audience and Portfolio Context

This repository demonstrates applied ML engineering fundamentals for a RAG workflow: data preparation, retrieval pipeline construction, model integration, confidence handling, and technical documentation.