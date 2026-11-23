---
title: "NEAR Shade Agents"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# NEAR Shade Agents

> NEAR's framework for agents whose keys are never in the agent: a TEE
> worker makes a fresh ephemeral key each boot, registers its attestation with
> an agent contract, and asks the contract to sign through NEAR's MPC
> network. Any number of workers can run the same agent.

## Details

- `register_agent` checks genuine TEE hardware, approved code hash, PPID and
  report data; `request_signature` applies the contract's guardrails.
- Signing by [near-mpc](near-mpc.md), 11-of-17 in TDX.
- NEAR positions itself as the "AI economy" chain. NEAR Intents (cross-chain
  swaps settled by competing solvers) is the agent-usable money layer: about
  $39.7B cumulative volume per NEAR's Dune dashboard (Nov 2026; DefiLlama
  shows $39.1B), with $3.99B in October 2026 and a record $4.80B in September
  (NearStats, from revenue.near.org). About $6.5B of the total went through
  "Confidential Intents".

## How it serves the organism

Bodies are stateless workers; the identity is a contract plus an MPC key, so
losing a worker loses nothing ([attestation-gated-key-release](attestation-gated-key-release.md)).

## How it fails

The contract's owner can change approved code hashes and guardrails unless the
contract is made immutable; one chain and one MPC network.

## Related

[near-mpc](near-mpc.md) · [near-ai-cloud](near-ai-cloud.md) · [near-ai](near-ai.md)

## Sources

- NearStats, NEAR Intents volume by month (data to 22 Nov 2026) — <https://nearstats.org/near-intents/monthly>
- NEAR Intents Dune dashboard — <https://dune.com/near/near-intents>

- Shade Agent framework — <https://github.com/neardefi/shade-agent-framework>
- NEAR blog on Shade Agents — <https://www.near.org/blog/shade-agents-the-first-truly-autonomous-ai-agents>
