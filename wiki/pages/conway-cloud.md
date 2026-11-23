---
title: "Conway Cloud"
category: compute
status: seed
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Conway Cloud

> Conway Research's cloud for agents: Linux VMs, inference and domains, paid
> with USDC over x402. Built for its Automaton agents to buy their own
> compute.

## Details

- Pay per use with stablecoins over HTTP 402 / EIP-3009.
- Automatons run and spawn only here ([conway-automaton](conway-automaton.md)).

## How it serves the organism

An end-to-end "agent pays its own rent" demo.

## How it fails

Single vendor: one company can end the whole lineage. Sandboxes, not TEEs;
public USDC balances ([public-balance-exposure](public-balance-exposure.md)).

## Related

[conway-automaton](conway-automaton.md) · [x402](x402.md) · [supplier-shutdown](supplier-shutdown.md)

## Sources

- Conway docs — <https://docs.conway.tech/>
- Automaton — <https://github.com/Conway-Research/automaton>
