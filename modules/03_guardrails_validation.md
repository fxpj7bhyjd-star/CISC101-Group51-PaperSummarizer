**Module 3 — Guardrails & Validation**:

- Enforce no hallucination by cross-referencing every claim against stored section content. 
- Explicitly flag missing or near-empty sections  
- Verify every cited reference actually appears  
- If paper is very long, state chunking strategy used 
- evidence_mode = "strict"
  If `evidence_mode = "strict"` is active:
    -> The summarizer shold only include claims, equations, and results that appear in the provided text.
    -> If it cannot find enough information
      -> it must say so explicitly (e.g., “The source text does not provide enough detail to summarize this section in strict  evidence mode.”).
- Section Warning Messages for sections that are: missing/empty, too short (<50 words)
    If it is missing/empty,
      -> Print "Section skipped: no usable text was provided."
    If it is too short (<50 words)
      -> Print "Section very short: summary may be incomplete.”
