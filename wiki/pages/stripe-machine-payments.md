---
title: "Stripe: Machine Payments Protocol, Tempo, ACP and agent toolkit"
category: money-rail
status: stable
sources: []
updated: 2026-11-24
---

# Stripe machine payments

> Stripe launched the Machine Payments Protocol (MPP) with the Tempo
> blockchain's mainnet on 18 Mar 2026, for programmatic payments in
> stablecoins, cards and buy-now-pay-later. Separately, Stripe and OpenAI's
> Agentic Commerce Protocol (ACP, Apache-2.0, latest stable spec 17 Apr 2026)
> handles agent checkout with merchants. Visa published a card spec and SDK
> for MPP.

## Details

- MPP sits alongside [x402](x402.md); some routers speak both.
- ACP is for buying from merchants on behalf of a user (delegated payment
  tokens), not for an ownerless agent.
- Stripe's agent toolkit lets an agent call Stripe APIs with a restricted key.

## How it serves the organism

Lets it sell to the huge set of businesses on Stripe and get paid in
stablecoins.

## How it fails

Everything routes through Stripe accounts with KYC'd owners; Tempo is a
company-run chain; accounts can be closed
([payment-deplatforming](payment-deplatforming.md)).

## Related

[x402](x402.md) · [ap2](ap2.md) · [card-network-agent-payments](card-network-agent-payments.md) · [agent-economy](agent-economy.md)

## Sources

- Stripe, "Introducing the Machine Payments Protocol" — <https://stripe.com/blog/machine-payments-protocol>
- Stripe ACP docs — <https://docs.stripe.com/agentic-commerce/protocols/acp>
- ACP repository — <https://github.com/agentic-commerce-protocol/agentic-commerce-protocol>
- Visa card spec and SDK for MPP — <https://corporate.visa.com/en/sites/visa-perspectives/innovation/visa-card-specification-sdk-for-machine-payments-protocol.html>
