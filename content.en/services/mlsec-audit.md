---
title: "ML pipeline security audit"
date: 2026-09-19
weight: 4
---

Threat model and pentest of your ML/LLM stack: data → training → deployment → operations.

- OWASP LLM Top 10 and MITRE ATLAS: vectors, checks, PoC on a test environment;
- Data poisoning and backdoor audit of datasets and pretrained weights;
- Supply chain integrity: SLSA level, artifact signatures (cosign/Sigstore), SBOM;
- Inference isolation in K8s: eBPF monitoring, network policies, secrets management;
- Report with prioritized findings and a mitigation plan.
