---
title: "FHE inference (thinking while encrypted)"
category: technology
status: seed
sources: []
updated: 2026-11-23
---

# FHE inference

> Fully homomorphic encryption lets a host run a model on encrypted inputs
> without ever seeing them, with no trusted hardware. In Nov 2026 the best
> full-FHE Llama-3-8B decode is 7.8 s/token on one GPU, about 8× too slow for
> chat. It is the only path to private thought that does not trust a chip
> vendor.

## Details

- Perseus (arXiv 2611.04488, Nov 2026): 7.8 s/token decode at 512-token
  context on one RTX Pro 6000; BUSL 1.1 licence.
- Trajectory: 181.5 s/token (Llama-2-7B, Sep 2024) → 31 s/token (Sylph) →
  7.8 s/token, roughly 20× per two years.
- Hybrids: Sylph encrypts only the private tail of a prompt; Bifrost mixes FHE
  linear layers with a TEE for nonlinear parts (still trusts hardware).
- Full detail lives in [approaches-crypto](approaches-crypto.md).

## How it serves the organism

A host that cannot read anything even with a bus interposer: the answer to
[tee-fail](tee-fail.md) for the mind.

## How it fails

Too slow for real-time agency at 8B and above today. Key management is still
needed: whoever holds the FHE secret key reads everything.

## Related

[approaches-crypto](approaches-crypto.md) · [nvidia-confidential-computing](nvidia-confidential-computing.md) · [op-inference-confidentiality](op-inference-confidentiality.md)

## Sources

- Perseus, arXiv 2611.04488 — <https://arxiv.org/abs/2611.04488>
- Sylph, arXiv 2601.18511 — <https://arxiv.org/html/2601.18511>
- Bifrost, arXiv 2606.17421 — <https://arxiv.org/html/2606.17421>
