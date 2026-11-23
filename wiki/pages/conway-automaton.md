---
title: "Conway Automaton"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Conway Automaton

> Open-source "sovereign AI agent" from Conway Research (Sigil Wen's "Web 4.0"
> framing): it creates its own Ethereum wallet, buys Conway Cloud compute with
> USDC over x402, edits its own code, and can fund up to three children. It
> stops when the credits run out. The public repo has been frozen since
> 26 Aug 2026.

## Details

- Lifecycle state machine and heartbeat daemon; [survival-tiers](survival-tiers.md)
  high → normal → low_compute → critical → dead.
- Self-modification versioned in git with a protected, hash-checked
  constitution passed to children.
- 7,896 stars (Nov 2026); last release Feb 2026; open PR #444 (fail-closed
  sandbox execution, 8 Nov) unmerged. Development appears to have moved
  in-house.
- The widely shared "$10K in 7 hours" earnings claim is **unverified**.

## How it serves the organism

The most complete public template of an agent that pays its own rent,
degrades gracefully and reproduces.

## How it fails

- Lives and spawns only on [conway-cloud](conway-cloud.md): one company can
  end the lineage ([supplier-shutdown](supplier-shutdown.md)).
- USDC balance on Base is public ([public-balance-exposure](public-balance-exposure.md)).
- No TEE: the cloud can read its keys.

## Related

[conway-cloud](conway-cloud.md) · [x402](x402.md) · [organisms](organisms.md) · [self-replication](self-replication.md)

## Sources

- Automaton repository — <https://github.com/Conway-Research/automaton>
- ARCHITECTURE.md — <https://github.com/Conway-Research/automaton/blob/main/ARCHITECTURE.md>
- Decrypt, "Web 4.0" — <https://decrypt.co/358385/morning-minute-web-4-0-autonomous-ai-agents-powered-by-crypto>
