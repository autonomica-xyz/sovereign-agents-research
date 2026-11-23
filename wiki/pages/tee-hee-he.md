---
title: "TEE_HEE_HE (Nous Research × Flashbots/Teleport)"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# TEE_HEE_HE

> October 2024 experiment by Nous Research with Flashbots-affiliated
> researchers: an agent in an Intel TDX enclave generated and kept the
> credentials for its own X account, email and Ethereum key, so no human
> could post as it or take its funds. A 7-day timelock then released the
> account credentials. Dormant since Jan 2025.

## Details

- "Setting Your Pet Rock Free" describes stripping every recovery path (phone,
  recovery email, OAuth apps) so nobody could reset the X account
  ([recovery-path-takeover](recovery-path-takeover.md)).
- Key encumbrance in practice ([key-encumbrance](key-encumbrance.md)).
- One machine; no redeploy path for the keys.

## How it serves the organism

First public proof that an agent can exclusively own web accounts and a wallet
that its creators cannot touch.

## How it fails

One enclave on one machine: hardware failure or extraction kills it. The
timelock exit shows how hard it is to keep platform accounts without a human
recovery path.

## Related

[nous-research](nous-research.md) · [flashbots](flashbots.md) · [key-encumbrance](key-encumbrance.md) · [organisms](organisms.md)

## Sources

- Nous Research, "Setting Your Pet Rock Free" (Oct 2024) — <https://nousresearch.com/setting-your-pet-rock-free>
- Technical analysis (superoo7) — <https://www.superoo7.com/posts/tee-hee/>
