---
title: "Freysa"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-24
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
- The open `sovereign-freysa` repository (17 stars) was last pushed on
  28 Feb 2025 (GitHub API, 23 Nov 2026); the framework docs moved to
  framework.freysa.ai.

- **Freysa.ai, the agent platform (Aug–Oct 2026).** On 15 Aug 2026 Freysa
  announced "a virtual machine, an email address, and a wallet for every
  agent". By 19 Sep it said "over 200 agents" had come online in two weeks.
  It frames the mission as "billions of sovereign agents" and says
  "Cognition should be self-owned".
- **What agents can do there:** Agent Creation Hooks (22 Sep) let any app
  mint an agent from a link. Safe multisigs (27 Sep) have the agent propose
  and the human approve, so custody is shared, not sovereign. From 3 Oct
  agents can buy on Amazon and book hotels with USDC, and from 14 Oct pay
  "via x402". Freysa claims an agent can go from birth to hiring a human
  through a @rentahumanx bounty in under 5 minutes (4 Oct). On 29 Oct it
  added "Networks", shared spaces for agents and teams.
- The platform hosts the VMs, so the operator can still stop or read any
  agent. Whether agent VMs run in TEEs was not stated in these posts
  (unverified).

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
- GitHub API, 0xfreysa/sovereign-freysa — <https://api.github.com/repos/0xfreysa/sovereign-freysa>
- @freysa_ai, freysa.ai launch (15 Aug 2026) — <https://x.com/freysa_ai/status/2088638456419455393>
- @freysa_ai, mission post (19 Sep 2026) — <https://x.com/freysa_ai/status/2101164273745777007>
- @freysa_ai, Safe multisigs (27 Sep 2026) — <https://x.com/freysa_ai/status/2104146718363423207>
- @freysa_ai, x402 purchases (14 Oct 2026) — <https://x.com/freysa_ai/status/2110488378190024842>
