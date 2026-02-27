# Waikar et al. (2026) — Analytical Notes

## Core Contribution

- Implements RAG systems to evaluate:
  - FDA drug labeling compliance
  - Clinical trial protocol adherence to E9 guidance
- Uses guidance documents (21 CFR, FDA labeling guidance) as retrieval corpus
- Compares RAG vs GPT-4o (no retrieval)
- Evaluates with ROUGE-L, METEOR, faithfulness, and custom ClinPharm metric

## Architecture

- LangChain-based RAG pipeline
- Document ingestion + embedding + retrieval
- Prompt = persona + retrieved context + query
- LLM generation
- LLM-as-judge (DeepEval / G-Eval)

## Strengths

1. True regulatory domain (not synthetic QA)
2. Uses real FDA guidance documents
3. Compares retrieval vs no-retrieval baseline
4. Includes independent verification by domain experts
5. Attempts domain-specific evaluation metric (ClinPharm)

## Limitations

1. No claim-level grounding:
   - Evaluates at answer-level only
   - Does not decompose outputs into atomic claims

2. No authority hierarchy modeling:
   - CFR vs guidance vs advisory not structurally modeled

3. No hallucination taxonomy:
   - Errors discussed narratively, not systematically categorized

4. Small-scale pilot:
   - Limited number of drugs and protocols

5. Evaluation metrics:
   - ROUGE-L / METEOR not ideal for compliance reasoning
   - LLM-as-judge introduces subjectivity

6. No explicit refusal mechanism when grounding is weak

## Where This Differs From My Thesis

My thesis extends this direction by:

- Introducing claim-level grounding instead of answer-level compliance checks
- Modeling regulatory authority hierarchy (binding vs interpretive guidance)
- Designing a regulatory hallucination taxonomy
- Risk-weighting hallucinations based on enforcement impact
- Implementing adaptive refusal calibration
- Building a structured regulatory benchmark

This paper shows feasibility.
My work formalizes reliability.
