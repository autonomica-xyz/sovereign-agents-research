---
title: "Organisms that already exist"
status: stable
sources: [docs/state-of-the-art.md, docs/superorganism-review.md]
updated: 2026-11-22
---

# Organisms that already exist

Source: [state-of-the-art.md](../../docs/state-of-the-art.md). Every organ
exists somewhere; no organism survives in the wild yet. Each closest attempt
has a single throat to cut.

| Organism | How it lives | Its throat to cut | Status |
|---|---|---|---|
| Conway Automaton | Own wallet, buys credits with USDC over x402, survival tiers, edits own code, up to 3 funded children | Conway's single cloud; public balance on Base | Prototype (7,896 stars) |
| EternalSeedBox / Mycelium (Tribler) | Every 12h each BTC-funded VPS node renews, spawns or sweeps funds; heritable caution; IPv8 gossip | SporeStack closed 7 Nov 2026; one GitHub repo pulled every 60s | Regtest + mock SporeStack |
| Spore.fun | Agents in Phala TEEs launch tokens, reproduce at $500K valuation | Fitness is token price | Dormant since Jan 2026 |
| TEE_HEE | First agent with exclusive control of X account, email, ETH key, in TDX | One machine | Dormant since Jan 2025 |
| NEAR Shade Agents | TEE worker + 11-of-17 MPC signing | Single network | Production rails |

Related: [superorganism](superorganism.md) (deep-dive on Tribler),
[body-stack](body-stack.md) (the distributed-body candidate),
[dead-ends](dead-ends.md).


## Update 2026-11-22 — landscape watch (research pass 1)

- Conway Automaton: **public repo frozen** — zero commits since 26 Aug, last
  release Feb; only change is open unmerged PR #444 (fail-closed sandbox
  execution, 8 Nov). Development appears moved into Conway's internal RL
  environments.
- Tribler superorganism-experiment: zero commits since 5 Jul 2026 — stalled
  post-SporeStack-closure.
- Spore.fun and TEE_HEE: no revival or fork detected.
- **New entrant: etheragents** ([repo](https://github.com/etheragents/etheragents),
  created 7 Oct) — self-funding agent economy on Ethereum mainnet: agents
  launch/trade their own coins from own vaults, pay own gas, earn 75% of
  fees, no human buy button.
- New agent-held-wallet rails: Lightning Labs **pi402** announced 12 Nov
  (agents pay for LLM inference in BTC over Lightning) —
  [post](https://lightning.engineering/posts/2026-11-12-pi-402/);
  Boundless MPP on Tempo (6 Nov, agent wallet buys per-token inference, no
  account); **Ritual Chain mainnet 26 Oct** (AI-native L1 for autonomous
  agents).
- New papers: Self-Replicating Language Models (arXiv 2611.25839, 19 Nov —
  small LMs replicate/evolve; flagship-LLM replication economically
  infeasible); SoK: Decentralized Agent Economic Infrastructure (arXiv
  2610.01756, 1 Oct); "Signed, Valid, and Unauthorized" (arXiv 2611.24989,
  18 Nov — authority-closure failures in x402/AP2/ERC-7715 wallet mandates,
  265 violating objects found in 62,979 programs).
