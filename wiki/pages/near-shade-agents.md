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
- NEAR positions itself as the "AI economy" chain; ~$30B all-time NEAR Intents
  volume was cited on X (Sep 2026, unverified here).

## How it serves the organism

Bodies are stateless workers; the identity is a contract plus an MPC key, so
losing a worker loses nothing ([attestation-gated-key-release](attestation-gated-key-release.md)).

## How it fails

The contract's owner can change approved code hashes and guardrails unless the
contract is made immutable; one chain and one MPC network.

## Related

[near-mpc](near-mpc.md) · [near-ai-cloud](near-ai-cloud.md) · [near-ai](near-ai.md)

## Sources

- Shade Agent framework — <https://github.com/neardefi/shade-agent-framework>
- NEAR blog on Shade Agents — <https://www.near.org/blog/shade-agents-the-first-truly-autonomous-ai-agents>
