# Claim-Level Grounding for High-Stakes Regulatory RAG

Authority-aware Retrieval-Augmented Generation (RAG) system for pharmaceutical regulatory question answering with claim-level verification and risk-weighted hallucination evaluation.

---

## What This Repository Contains

This project implements a research prototype designed to:

- Perform hybrid retrieval over regulatory text (BM25 + dense embeddings)
- Expand context via regulatory cross-reference graphs
- Generate candidate answers using RAG
- Decompose outputs into atomic claims
- Align claims to evidence using multiple verification strategies
- Quantify hallucination risk using an enforcement-anchored taxonomy
- Calibrate refusal when grounding thresholds are not met

This is a research system for evaluating grounded LLM behavior in regulated domains.

---

## System Architecture

### High-Level Flow

```text
User Query
  ↓
Planner Agent
  ↓
Hybrid Retrieval
  ↓
Graph-Based Expansion
  ↓
Candidate Generation
  ↓
Claim Extraction
  ↓
Claim–Evidence Alignment
  ↓
Selection or Adaptive Refusal
```

---

## Key Properties

- Claim-level (not answer-level) grounding  
- Authority-aware retrieval (binding vs interpretive sources)  
- Hybrid retrieval pipeline (BM25 + dense)  
- Graph expansion over regulatory cross-references  
- Multi-strategy claim–evidence alignment:
  - Embedding similarity  
  - Cross-encoder reranking  
  - LLM-based entailment prompting  
- Enforcement-anchored hallucination taxonomy  
- Risk-weighted hallucination evaluation  
- Refusal calibration based on grounding thresholds  

---

## Data Platform

The system operates over a structured, version-controlled corpus including:

- 21 CFR  
- 45 CFR 46  
- FDA guidance documents  

The corpus supports:

- Hierarchical parsing into normalized schema  
- Authority labeling  
- Cross-reference graph construction  
- Corpus snapshot hashing  
- Reproducible release manifests  

---

## Evaluation

### Stress-Test Benchmark

50 curated regulatory queries across:

- Lookup  
- Conditional reasoning  
- Multi-authority conflict  
- Ambiguity  
- Adversarial framing  

### Metrics

- Unsupported Claim Rate  
- Citation Correctness Rate  
- Authority Misattribution Rate  
- Hallucination category frequency  
- Risk-Weighted Hallucination Rate  
- Precision@k  
- nDCG  
- Unsafe Answer Rate vs Refusal Rate  
- Tokens per query  
- Latency  

---

## Quickstart

```bash
# install dependencies
pip install -e .

# run demo pipeline
python run_demo.py
```

## Repository Structure

```text
src/
  regulatory_platform/
  retrieval/
  rag/
  grounding/
  taxonomy/
  risk_model/
  evaluation/

benchmarks/
configs/
docs/
reports/
runs/
notebooks/
```
