---
title: "Mesh LLM"
category: technology
status: stable
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-23
---

# Mesh LLM

> Open-source Rust project that pools GPUs on many machines into one
> OpenAI-compatible endpoint over iroh, with Nostr discovery. A public mesh is
> live. Lightning payments are being added by Spiral, so machines could buy and
> sell inference from each other with no accounts.

## Details

- Runs a model locally if it fits, routes to a peer, or splits layers across
  peers (pipeline stages).
- Releases v0.78–v0.80.0 (16 Nov 2026); public mesh snapshot: 16 nodes,
  285.4 GB pooled, 34 models (public.meshllm.cloud).
- Payments: `pay-lightning` plugin v0.1.2 plus Lexe and NWC wallet plugins are
  documented, but the `ln-payments-plugin` repo still says "WIP, do not use"
  (Nov 2026). Spiral presented the plan publicly (Oct 2026).
- A third-party project with a token ("meshllmcloud", contract posted on X)
  appeared on 25 Oct 2026; it is not the upstream project.

## How it serves the organism

The organism can pool scavenged or rented GPUs into its own mind, and later
sell spare capacity for sats ([earn-buy-redeploy-loop](earn-buy-redeploy-loop.md)).

## How it fails

- Prompts travel in the clear to peers unless the mesh is private; peers see
  the organism's thoughts ([op-inference-confidentiality](op-inference-confidentiality.md)).
- No confidential execution on peers; a malicious peer can return wrong output.
- Payment plugin not production-ready.

## Related

[iroh](iroh.md) · [spiral](spiral.md) · [lightning](lightning.md) · [compute](compute.md)

## Sources

- Mesh-LLM repository — <https://github.com/Mesh-LLM/mesh-llm>
- Mesh LLM plugins docs — <https://meshllm.cloud/docs/pages/plugins/>
- ln-payments-plugin — <https://github.com/Mesh-LLM/ln-payments-plugin>
- Spiral on Mesh LLM payments (Presidio Bitcoin, X, 7 Oct 2026) — <https://x.com/PresidioPod/status/2107905600432845130>
