---
title: "Services"
---

We cover the full engineering cycle of working with AI models — from raw data to a running service in production. Each service is a standalone project with fixed deliverables: code, configurations, metrics and documentation — not a "consultation".

## Data and preparation

We start with what every ML project stands on. Audit of your existing datasets and documents, corpus collection from your sources (document flow, logs, CRM, tickets), deduplication, cleaning, labeling and quality control. A separate track is checking data for toxicity and poisoning (data poisoning): a dataset contaminated with a hostilely crafted sample set makes every subsequent stage meaningless.

## Training and fine-tuning

Fine-tuning open models (Llama, Qwen, Gemma, Mistral) to your domain: SFT and LoRA/QLoRA, hyperparameter search, overfitting control on held-out sets, quantitative hallucination evaluation. The result is not "here are the weights" but a reproducible pipeline: configuration, seeds, model card, evaluation protocol.

## Optimization

We bring the model to economic viability: quantization (GGUF, AWQ/GPTQ, INT8/FP8), distillation into compact students, speculative decoding, KV-cache and batching optimization. Before rollout — a before/after benchmark under your real workload: tokens per second, P95 latency, cost per million tokens, quality degradation. The "quality vs speed" trade-off decision is made on numbers, not on feelings.

## Deployment and integration

Inference service inside your perimeter: llama.cpp or vLLM on Kubernetes, load balancing, autoscaling, latency and error monitoring. RAG pipelines over your documents with hybrid search, reranking and mandatory source citations. AI agents with strict tool restriction and white-listed external calls. Data never leaves your perimeter — that is the default design constraint.

## Security and ongoing support

ML-stack audit against OWASP LLM Top 10 and MITRE ATLAS: prompt injection via documents and user input, context leaks, supply chain integrity (artifact signatures, SBOM, SLSA). After deployment — quality drift monitoring, regular red-team runs with poisoned smoke tests in CI, and model update support.

---

Engagement format: fixed scope and deliverables, repository access from day one, weekly demos. You can start at any stage — but we never take on inference optimization without measurements on your data.
