---
title: "NEAR AI Cloud"
category: compute
status: seed
sources: []
updated: 2026-11-23
---

# NEAR AI Cloud

> Confidential inference on Intel TDX plus NVIDIA confidential GPUs, using
> dstack as the OS layer. Since 15 Oct 2026 it serves Brave Leo's end-to-end
> encrypted chats, the largest consumer deployment of TEE inference so far.

## Details

- Brave relays encrypted prompts through its AI gateway (with Oblivious HTTP);
  the client verifies TDX quotes, RTMR3 event logs, compose config and GPU
  attestation (open-source `near-verifier`).
- NEAR also runs an agent market and the Shade Agent stack
  ([near-shade-agents](near-shade-agents.md)).

## How it serves the organism

Private thought from a provider whose attestation chain is publicly
verifiable, paid without a human-in-the-loop via NEAR intents (hackathon
demos, Nov 2026).

## How it fails

Single operator; account-based access; same TDX/NVIDIA attestation limits as
everyone else ([tee-fail](tee-fail.md)).

## Related

[dstack](dstack.md) · [near-ai](near-ai.md) · [op-inference-confidentiality](op-inference-confidentiality.md)

## Sources

- Brave blog (Oct 2026) — <https://brave.com/blog/browser-ai-e2ee/>
- NEAR AI on Brave Leo — <https://near.ai/blog/near-ai-cloud-brings-private-inference-to-brave-leo>
- brave/near-verifier — <https://github.com/brave/near-verifier>
- NEAR hackathon entry paying for private inference via NEAR intents (Andrew Miller on X, 14 Nov 2026) — <https://x.com/socrates1024/status/2121694797106967034>
- NEAR AI agent market — <https://near.ai/blog/introducing-near-ai-agent-market>
