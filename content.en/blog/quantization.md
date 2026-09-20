---
title: "LLM quantization: how much quality does one bit cost"
date: 2026-09-12
description: "A practical comparison of GGUF Q4/Q5/Q8 and AWQ: perplexity degradation, speed, memory on real tasks."
image: "img/blog/quantization.svg"
tags: ["quantization","llm","inference","gguf"]
---

Quantization is the cheapest way to speed up inference, but the "free cheese" ends at Q4. We ran three open models (7B, 13B, 34B) through a task suite and pinpointed where degradation actually begins.

## Methodology

- Formats: GGUF (llama.cpp, Q4_K_M, Q5_K_M, Q8_0 quants) and AWQ 4-bit (vLLM);
- Metrics: perplexity on an English corpus, fact-extraction accuracy from documents, P95 latency, peak memory;
- Hardware: RTX 4090 24 GB and an ARM SBC with RK3588.

## Results

| Config | Perplexity (Δ vs FP16) | Speed | Memory |
|---|---|---|---|
| Q8_0 | +0.1% | ×1.8 | 51% |
| Q5_K_M | +0.4% | ×2.4 | 34% |
| Q4_K_M | +1.9% | ×3.1 | 28% |
| AWQ 4-bit | +1.2% | ×4.2 (batch) | 27% |

Practical takeaway: **Q5_K_M is the sweet spot** — quality is nearly indistinguishable from Q8 while the memory savings are already there. Q4_K_M is already noticeably worse at fact extraction (−4…7 p.p. on narrow domains) but works great for chat tasks. For RAG with citations we do not recommend going below Q5 — source links start to drift.

## Next time

Distillation: when it is cheaper to train a 7B student to the level of a 34B teacher once than to keep serving the quantized teacher.
