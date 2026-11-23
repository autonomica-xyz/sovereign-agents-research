---
title: "Card networks for agents (Visa Intelligent Commerce, Mastercard Agent Pay)"
category: money-rail
status: stable
sources: []
updated: 2026-11-24
---

# Card networks for agents

> Visa Intelligent Commerce and Mastercard Agent Pay issue tokenised cards
> that agents can use within limits set by a human cardholder. A Sep 2026
> landscape report lists Visa Intelligent Commerce plus the Trusted Agent
> Protocol (built with Cloudflare) as early production, and Mastercard Agent
> Pay as live (Santander, Q1 2026; eight APAC markets), with "Agent Pay for
> Machines" announced 10 Jun 2026 with 30+ partners. Mastercard bought
> stablecoin firm BVNK for up to $1.8B (Mar 2026).

## Details

- Spending limits and merchant rules enforced by the network, outside the
  model ([prompt-injection-drain](prompt-injection-drain.md)).
- Cardholder KYC is the root of trust.

## How it serves the organism

Lets it receive card payments indirectly and shows the policy-below-the-model
pattern it should copy.

## How it fails

Requires a human cardholder; the network can revoke the token at any time.

## Related

[stripe-machine-payments](stripe-machine-payments.md) · [ap2](ap2.md) · [payment-deplatforming](payment-deplatforming.md)

## Sources

- Visa card spec and SDK for MPP — <https://corporate.visa.com/en/sites/visa-perspectives/innovation/visa-card-specification-sdk-for-machine-payments-protocol.html>
- Ryan Yu, Agentic commerce landscape (Sep 2026) — <https://www.ryanyu.co/agentic-commerce-landscape-sept-2026.pdf>
