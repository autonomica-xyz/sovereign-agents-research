---
title: "NVIDIA confidential computing (GPU TEEs)"
category: technology
status: stable
sources: [docs/research-notes.md, docs/state-of-the-art.md]
updated: 2026-11-23
---

# NVIDIA confidential computing

> H100, H200 and Blackwell GPUs can run in a confidential mode paired with a
> CPU TEE, so model weights, prompts and memory stay encrypted from the host.
> It is what lets an organism think on rented GPUs without its mind being read.

## Details

- Overhead on H100 CC is under 7% for typical LLM inference (arXiv 2409.03992).
- Blackwell supports multi-GPU confidential computing.
- Offered by [phala-cloud](phala-cloud.md), [near-ai-cloud](near-ai-cloud.md),
  [chutes](chutes.md), [io-net](io-net.md) (on request) and
  [akash](akash.md) (`cpu-gpu`, experimental; GPU CC awaits NVIDIA licensing).

## How it serves the organism

Private thought: the organism's prompts, memory and keys in context are hidden
from the GPU landlord ([op-inference-confidentiality](op-inference-confidentiality.md)).

## How it fails

- [tee-fail](tee-fail.md) showed NVIDIA's attestation is **not bound to a
  specific CVM**, so a non-TEE workload can borrow another machine's GPU
  attestation.
- Providers serving "confidential" models without full hardening leaked
  in-flight prompts ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).
- confidentialinference.net still showed 0 of 13 providers fully attested
  (22 Nov 2026).

## Related

[intel-tdx](intel-tdx.md) · [op-inference-confidentiality](op-inference-confidentiality.md) · [fhe-inference](fhe-inference.md)

## Sources

- H100 CC performance, arXiv 2409.03992 — <https://arxiv.org/abs/2409.03992>
- NVIDIA Blackwell multi-GPU attestation — <https://docs.nvidia.com/attestation/quick-start-guide/latest/attestation-examples/blackwell_multi_gpu.html>
- TEE.fail — <https://tee.fail/>
- io.net confidential compute — <https://io.net/docs/guides/clouds/confidential-compute-overview>
