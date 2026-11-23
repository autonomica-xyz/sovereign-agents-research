---
title: "Spark (statechain L2)"
category: money-rail
status: stable
sources: []
updated: 2026-11-24
---

# Spark

> A Bitcoin layer 2 built on statechains: coins move by re-sharing a 2-of-3
> FROST key between the user and Spark Operators (Lightspark, Flashnet,
> Breez), with a pre-signed exit to L1. Mainnet is a beta; it supports
> Lightning interop and stablecoin tokens.

## Details

- Safety needs at least one operator to delete old key shares honestly.
- If all operators go offline, transfers stop but funds can exit to L1.

## How it serves the organism

Cheap instant BTC payments with unilateral exit, no channel management.

## How it fails

Operator collusion could double-spend; three known companies run it.

## Related

[ark](ark.md) · [lightning](lightning.md) · [frost](frost.md) · [cashu](cashu.md)

## Sources

- Spark FAQ — <https://docs.spark.money/learn/faq>
- Spark, what is Spark — <https://www.spark.money/research/what-is-spark-bitcoin-layer-2>
