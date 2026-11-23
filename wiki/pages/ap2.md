---
title: "AP2 (Agent Payments Protocol)"
category: money-rail
status: stable
sources: []
updated: 2026-11-24
---

# AP2

> Google's Agent Payments Protocol defines signed "mandates" (intent, cart,
> payment) so a merchant can check that a user authorised an agent's
> purchase. Announced 16 Sep 2025 with 60+ partners; Google later donated
> it to the FIDO Alliance.

## Details

- Rail-agnostic: cards, bank transfers, stablecoins (an x402 extension
  exists).
- The research paper "Signed, Valid, and Unauthorized" found authority
  failures in AP2-, x402- and ERC-7715-style wallet mandates
  ([prompt-injection-drain](prompt-injection-drain.md)).

## How it serves the organism

A way for it to accept payments from human-owned agents whose purchases are
provably authorised.

## How it fails

Mandates root in a human user's credentials; an ownerless organism has no
such root.

## Related

[stripe-machine-payments](stripe-machine-payments.md) · [x402](x402.md) · [agent-economy](agent-economy.md)

## Sources

- Google, AP2 donated to the FIDO Alliance — <https://blog.google/products-and-platforms/platforms/google-pay/agent-payments-protocol-fido-alliance/>
- Finray agent payment protocols tracker — <https://finray.tech/intelligence/agent-payment-protocols-tracker/>
