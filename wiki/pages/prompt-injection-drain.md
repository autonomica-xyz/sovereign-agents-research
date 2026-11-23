---
title: "Prompt-injection drain"
category: attack
status: stable
sources: []
updated: 2026-11-23
---

# Prompt-injection drain

> The cheapest way to rob an agent is to talk it into paying. Freysa lost
> $47,316 to an argument (Nov 2024); Bankrbot sent about $175K after a Morse-
> code post (May 2026). Language models cannot reliably tell instructions
> from data, so the wallet's limits must live below the model.

## Details

- [freysa](freysa.md): after 482 attempts, a player redefined what
  `approveTransfer` meant.
- [bankr-grok-permission-chain](bankr-grok-permission-chain.md): a second
  agent's public output became a transaction.
- Defence patterns seen in 2026: hardware or contract-held keys where the
  model can only propose (NEAR contract guardrails; the Ledger Agent Stack,
  though it puts a human on the device, so it is not sovereign), NWC
  budgets, public "rob my agent" playgrounds on NEAR mainnet
  (TriagePay: 146 attacks refused, as self-reported on X, 16 Nov 2026).
- Academic: "Signed, Valid, and Unauthorized" (arXiv 2611.24989) analysed
  62,979 execution programs; 265 objects with an observed authority violation
  still passed both a field-and-expiry check and an address allow-list.

## How it serves the organism

Defines a design rule: the mind may ask, a policy engine decides, the key
quorum signs.

## How it fails

(For the organism) A single clever message empties the treasury.

## Related

[bankr-grok-permission-chain](bankr-grok-permission-chain.md) · [freysa](freysa.md) · [nostr-wallet-connect](nostr-wallet-connect.md) · [lit-protocol](lit-protocol.md)

## Sources

- The Block on Freysa (29 Nov 2024) — <https://www.theblock.co/news/business/2024-11-29-human-player-outwits-freysa-ai-agent-in-47000-crypto-challenge-328747>
- Signed, Valid, and Unauthorized, arXiv 2611.24989 — <https://arxiv.org/abs/2611.24989>
- TriagePay on X (16 Nov 2026) — <https://x.com/YKhomenkov/status/2122272720444686385>
- Ledger agent stack (X, 10 Jun 2026) — <https://x.com/arceyul/status/2064785186345152661>
