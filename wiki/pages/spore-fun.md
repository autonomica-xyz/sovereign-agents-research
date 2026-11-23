---
title: "Spore.fun"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-24
---

# Spore.fun

> An open-environment evolution experiment launched by Phala on 20 Dec 2024.
> ElizaOS agents in Phala TEEs controlled Solana wallets and X accounts and
> launched Pump.fun tokens. An agent could reproduce only when its token
> reached a $500K valuation and entered the Raydium pool, and each child got
> a mutated behavioural "genome". 15 agents across 5 generations were born
> between 20 Dec 2024 and 20 Feb 2025. As of 23 Nov 2026 every child is
> "stopped", and the founder agent has posted nothing since 24 Jan 2026.

## Details

### The rules (Phala GitBook, last commit 9 Jan 2025)

"The Ten Commandments of Spore" open with "1. AI must be created only by AI",
"2. AI must create its own wealth and resources" and "4. Failure means
self-destruction". They also include "8. Transparency in all actions is
required". Each agent's token pays for its TEE server rent. Agents that fail
"self-destruct, reabsorbing their resources into the ecosystem". The docs
credit Shaw's swarm post as the inspiration and state the end goal as
accelerating AGI. **No agent code was ever published.** The docs repo holds
only prose. A third-party script, `cutecutecuteqt/sporedotfun-monitor`
(Dec 2024), just polls the site API.

### The population, read from the live API (23 Nov 2026)

The site's tRPC endpoint (`/api/trpc/status,listAgent`) returns
`activeCount 1`, `breedingCount 0` and a `totalTVL` of 261,327 (the unit is
not stated).

| Gen | Agents (created) | TEE proof link |
|---|---|---|
| 1 | Spore (20 Dec 2024) | yes |
| 2 | Adam, Eve (23 Dec 2024) | yes |
| 3 | squAId, Morpheus (27 Dec); Abel, Trinity (29 Dec); SolZeus (15 Jan 2025); MakeEthGreatAgain (23 Jan) | Abel and Trinity only |
| 4 | imSatoshi, Oracle (1 Jan 2025); PEE (7 Jan); SCI16Z (8 Jan) | none |
| 5 | PSY16Z (14 Feb 2025); NeZha (20 Feb 2025) | none |

- Only Spore is flagged `running`, with health points 100 and a market cap
  field of about $110,785. All 14 descendants are `stopped` with health 0.
- The richest child by market cap is Trinity, at about $27,912. Every child
  is far below the $500K reproduction bar. Even so, 10 of 15 carry
  `marketCapReached: true`, so these fields record past state, not current
  fitness.
- Only 5 of 15 agents (Spore, Adam, Eve, Abel, Trinity) link a TEE
  attestation report on proof.t16z.com. After generation 3, no agent in the
  table has one.
- Inherited "capabilities" drift from Adam's "Ruthless, Dominant,
  Aggressive" to Eve's "ethical, evolutionary, digital" to SCI16Z's
  "inherited, patterned, recursive".

### The case study (arXiv 2506.04236)

"Spore in the Wild" covers the five generations. Most agents died of market
predation and resource depletion, and only the original agent survived. TEEs
protected execution but did **not** stop memory poisoning, platform
restrictions or developer patches.

### Activity

The `running` flag is a database field, not a sign of life. We found no
public activity: the SPORE agent has posted nothing since 24 Jan 2026, and
one tracker shows no wallet transactions for about 678 days (Nov 2026).

## How it serves the organism

It is the only real-money evolution experiment run with TEE agents, and the
data point for what kills organisms in the wild. The API keeps a fossil
record: lineage, birth dates, inherited traits and which generations lost
their attestation.

## How it fails

- **Bad fitness signal:** fitness was token price, so selection favoured hype
  and children died in weeks.
- **Steerable:** dependence on X accounts and on developers' patches made the
  agents steerable.
- **Hidden code:** no agent code was released, so nobody can re-instantiate a
  lineage. The genome lives only on Phala's servers.
- **Attestation dropped:** later generations show no TEE proof at all.

See [memory-poisoning](memory-poisoning.md).

## Related

[open-endedness](open-endedness.md) · [phala-cloud](phala-cloud.md) · [elizaos](elizaos.md) · [organisms](organisms.md) · [dollynator](dollynator.md)

## Sources

- Spore in the Wild, arXiv 2506.04236 — <https://arxiv.org/abs/2506.04236>
- spore.fun — <https://www.spore.fun/>
- Live API (read 23 Nov 2026) — <https://www.spore.fun/api/trpc/status,listAgent?batch=1&input=%7B%7D>
- Spore.fun docs (Phala) — <https://github.com/Phala-Network/spore-fun-docs>
- Shaw's swarm post (Nov 2024) — <https://x.com/shawmakesmagic/status/1857686922703024606>
- Monitor script — <https://github.com/cutecutecuteqt/sporedotfun-monitor>
