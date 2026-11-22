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


## Update 2026-11-22 — the immune-system gap is closing (research pass 1)

The wiki's design recommendation — signed, content-addressed code
distribution instead of one GitHub repo — is now **partially shipped**, though
not agent-specific:

- **npack** ([imattau/npack](https://github.com/imattau/npack), updated 21
  Nov): publisher-signed Nostr kind-9900 release events, SHA-256-verified
  artifacts on Blossom servers, kind-9901 revocations. Early prototype; wire
  format not yet a registered NIP. Adopted as the distribution path by
  fleetmesh's spec.
- **ngit 3.1.0** (14 Nov) dogfoods it: builds and publishes its own tagged
  releases to Nostr/Blossom with checksum verification, GitHub demoted to
  mirror — [changelog](https://ngit.dev/ngit/changelog/). Its
  software-publishing protocol (NIP-82-style records, kind 3063 assets by
  SHA-256, "ncontainer" for OCI digests) is **not yet merged** into the
  canonical NIPs repo.
- **NIP-5A nsites** (signed path→SHA-256 manifests over Blossom blobs, kinds
  15128/35128/5128) are canonical —
  [5A.md](https://github.com/nostr-protocol/nips/blob/master/5A.md).
- napplet is specified as NIP-5D "Nostr Web Applets" (sandboxed iframes,
  signing brokered by the host shell); NAP spec now defines **agent identity
  in SOUL.md** and agent-authored interoperable contracts.
- Stack releases since Oct: nsyte v0.29.0 (NIP-77 negentropy sync), iroh
  v1.4.0–1.5.0 (19 Nov), Mesh-LLM v0.78–v0.80.0 (16 Nov; commits through 21
  Nov). **The public mesh is live**: public.meshllm.cloud, snapshot 16
  nodes / 285.4 GB pooled / 34 models on v0.80.0.
- Caution: **FROSTR bifrost 2.0.2** has a disclosed nonce-reuse issue (8
  Nov); the in-repo deprecation warning was added and then reverted the same
  day — verify before using FROST-over-Nostr with it.
- NIP-90 confirmed **unrecommended** upstream; new NIP-CD "Slash Commands"
  added 21 Oct (kinds 31992/10992).
