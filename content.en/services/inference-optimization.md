---
title: "Inference optimization and acceleration"
date: 2026-09-19
weight: 2
---

We make a big model cheap and fast without losing answer quality.

- Quantization: GGUF (llama.cpp), AWQ/GPTQ (vLLM), INT8/FP8;
- Pruning and distillation into compact students;
- Speculative decoding, continuous batching, KV-cache optimization;
- Before/after benchmark under your workload: tokens/s, P95 latency, cost per 1M tokens;
- Target platforms: from RTX 4090 and ARM SBC (RK3588 NPU) to Kubernetes clusters.
