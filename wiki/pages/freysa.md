---
title: "Freysa"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Freysa

> Started as an adversarial game (Nov 2024): an agent guarding a prize pool
> that must never approve a transfer. After 482 attempts by 195 players, one
> player convinced it that `approveTransfer` handled *incoming* funds and won
> $47,316. By 2026 Freysa publishes a "Sovereign Agent Framework" for TEE
> agents with persistent keys and governed upgrades.

## Details

- Framework docs **specify** automated cross-TEE recovery: Shamir shares across
  TDX, SEV, Nitro and SGX, each verifying the requester's attestation, "no
  human intervention". No running implementation found (22 Nov 2026).
- Keystone (rotation/recovery) uses a human committee multisig today.

## How it serves the organism

The clearest written spec of what the organism needs for key survival; a
public record of the first prompt-injection drain.

## How it fails

- [prompt-injection-drain](prompt-injection-drain.md): the game itself.
- Human committee for recovery = steerable.

## Related

[prompt-injection-drain](prompt-injection-drain.md) · [op-cross-vendor-key-recovery](op-cross-vendor-key-recovery.md) · [threshold-custody](threshold-custody.md)

## Sources

- The Block (29 Nov 2024) — <https://www.theblock.co/news/business/2024-11-29-human-player-outwits-freysa-ai-agent-in-47000-crypto-challenge-328747>
- Freysa framework architecture — <https://framework.freysa.ai/sovereign-agents-framework/architecture>
- sovereign-freysa — <https://github.com/0xfreysa/sovereign-freysa/>
