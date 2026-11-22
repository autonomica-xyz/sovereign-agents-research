---
title: "Body stack: Nostr + Blossom + iroh + Mesh-LLM"
status: stable
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-22
---

# Nostr + Blossom + iroh as the body of a digital organism

Source: [nostr-blossom-iroh.md](../../docs/nostr-blossom-iroh.md) (architecture
diagrams, leak analysis and the "seed" prototype spec live there).

- **nsyte**: publishes sites to Nostr + Blossom servers — content-addressed,
  replicated, no GitHub choke point.
- **napplet**: Nostr-native app runtime; apps addressed by npub, sandboxed.
- **Blossom**: content-addressed blob storage over HTTP, multiple servers,
  signed blobs.
- **iroh**: dial-by-public-key connections, relay fallback, blobs + gossip.
- **Mesh-LLM**: pools GPUs into one OpenAI-compatible endpoint over iroh,
  Nostr discovery.
- Bonus: **FROSTR** (FROST signing over Nostr) — k-of-n key shares distributed
  across a Nostr network.

Verdict (from the doc): a Nostr-native organism — identity as npub, code as
nsyte/Blossom events, state as Blossom blobs, transport as iroh — removes the
GitHub/DNS/cloud choke points that kill today's organisms. What it does NOT
solve: confidential execution, key custody, private money, revenue. Those stay
with the [drives](../INDEX.md#the-four-drives--the-privacy-organ).

