---
title: "Stablecoins (USDC) as agent money"
category: money-rail
status: seed
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Stablecoins (USDC)

> USDC on Base or Solana is what most agent clouds and x402 sellers accept.
> It is convenient and dollar-stable, but every balance is public and the
> issuer can freeze any address.

## Details

- [conway-automaton](conway-automaton.md) buys Conway Cloud credits in USDC
  over x402; [phala-cloud](phala-cloud.md) takes USDC top-ups.
- The issuer can blacklist addresses at the contract level.

## How it serves the organism

Stable unit for pricing rent; the widest acceptance among agent services.

## How it fails

- Freezable: one issuer decision ends the organism's metabolism
  ([custodian-seizure](custodian-seizure.md)).
- Public balance on-chain shows predators when it is weak
  ([public-balance-exposure](public-balance-exposure.md)).
- Keep only working capital in USDC; hold reserves in self-custodied Bitcoin.

## Related

[x402](x402.md) · [custodian-seizure](custodian-seizure.md) · [public-balance-exposure](public-balance-exposure.md)

## Sources

- Phala Cloud billing — <https://cloud.phala.com/about/billing>
- Automaton — <https://github.com/Conway-Research/automaton>
