---
title: "Turnkey"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Turnkey

> Wallet infrastructure that generates keys and signs only inside AWS Nitro
> Enclaves, with a policy engine (asset, counterparty, spend limit,
> approvals) aimed explicitly at AI agents. "Turnkey Verified" publishes
> boot and app proofs that link a signature to a Nitro attestation and the
> enclave's QuorumOS manifest.

## How it serves the organism

Policy enforced below the model: a prompt-injected agent still cannot
exceed limits ([prompt-injection-drain](prompt-injection-drain.md)).

## How it fails

Turnkey runs the enclaves on AWS; the organisation owner can lock the agent
out. Not sovereign custody.

## Related

[mpc-wallets](mpc-wallets.md) · [aws-nitro-enclaves](aws-nitro-enclaves.md) · [privy](privy.md)

## Sources

- AWS Web3 blog on Turnkey — <https://aws.amazon.com/blogs/web3/building-secure-verifiable-blockchain-key-management-on-aws-nitro-enclaves-at-turnkey/>
- Turnkey for AI agents — <https://www.turnkey.com/solutions/ai-agents>
- Turnkey Verified — <https://docs.turnkey.com/security/turnkey-verified>
