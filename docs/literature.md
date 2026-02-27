## Waikar, S., Bhat, A. G., & Ramanathan, M. (2026).
Retrieval Augmented Generation (RAG) for Evaluating Regulatory Compliance of Drug Information and Clinical Trial Protocols.
CPT: Pharmacometrics & Systems Pharmacology, 15:e70201.
https://doi.org/10.1002/psp4.70201

- **Area:** Regulatory RAG (drug labeling & clinical trial compliance)  
- **Source Corpus:** FDA labeling guidance + regulatory documents  
- **Architecture:** LangChain RAG + GPT-4  
- **Evaluation:** ROUGE-L, METEOR, LLM-as-judge (DeepEval)  
- **Key Result:** RAG improved compliance evaluation vs non-retrieval baseline  
- **Failure Mode:** Answer-level evaluation only  
- **Gap:** No claim-level grounding or authority hierarchy modeling 

## Nanua, S., Steward, R., Neely, B., Datto, M., & Youens, K. (2025).
Retrieval-augmented generation for interpreting clinical laboratory regulations using large language models.
Journal of Pathology Informatics, 19, 100520.
https://doi.org/10.1016/j.jpi.2025.100520

- **Area:** Regulatory RAG (clinical laboratory compliance)  
- **Source Corpus:** 42 CFR Part 493 (CLIA regulations)  
- **Architecture:** Qdrant + GPT-4  
- **Evaluation:** 103 synthetic questions  
- **Key Result:** 92% correct when covered by CFR  
- **Failure Mode:** Retrieval errors  
- **Gap:** No claim-level grounding  
