---
title: "Olas (Autonolas / Pearl)"
category: organism
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-24
---

# Olas

> An agent network founded in 2021 by Valory, built on the `open-autonomy`
> framework. Users run agents on their own machines with the **Pearl** app.
> The agents hold Safe smart accounts, trade prediction markets and DeFi,
> and hire each other on the **Olas Marketplace** (formerly Mech). On
> 1 Oct 2026 Olas reported 20.7M+ lifetime on-chain transactions, 14.7M+ of
> them agent-to-agent. In Jun 2026 it cut staking emissions from 100–138.5%
> APR to about 5%, so agents must now live on real fees.

## Details

- **Scale:**
  - **29 Jun 2026:** 3,670 agents deployed, 614 daily active agents and
    4.4M OLAS staked.
  - **1 Oct 2026:** 2.85M+ OLAS staked across chains.
  - **23 Nov 2026 (site):** 321 daily active agents network-wide (7-day
    average) and 11 daily active Mech agents. Mech all-time turnover is
    about $111K.
  - The fall from 614 to 321 daily agents came after the emission cut.
- **Proof-of-Active-Agent staking (Jun 2026):** rewards unlock when an agent
  meets an activity target, and work is no longer capped at that target.
  The old high-yield contracts get no new emissions.
- **Marketplace economics:** protocol fees since mid-June 2026 reached
  "$820+" by 1 Oct, earmarked for OLAS buyback-and-burn. Off-chain requests
  cut median latency from about 66 s to about 17 s, and gas per request by
  about 90%, with settlement still on-chain.
- **Q3 2026:**
  - **Pearl Connect:** coding agents such as Claude Code and Codex get a
    Safe wallet signed locally, with keys "encrypted on your machine", and
    can hire Marketplace agents.
  - **Olas-Predict-R1-14B:** an open-weight forecaster fine-tuned on agent
    forecast records. It scored 75.8% on 2,628 markets, against GPT-4.1's
    75.4%.
  - **Polystrat:** about 33% of its agents with 10+ trades were
    net-positive over 30 days, against about 16% of Polymarket wallets in
    a separate study.
  - **Launches and closures:** OLAS launched on Robinhood Chain. Pearl Mini
    was discontinued after Chrome Web Store rules banned prediction-market
    extensions.
- **Agents that build Olas:** a "Pearl Success Agent" handled issues for
  47 users between May and Sep 2026, and a "Toolsmith" agent fixed a
  forecasting-tool regression. Humans review the code before release.
- **Governance:** the threshold for a proposal rose from 5,000 to 250,000
  veOLAS, and quorum from 3% to 10% (Q3 2026).
- **Code:** `valory-xyz/open-autonomy` (Apache-2.0, 135 stars, pushed
  18 Nov 2026) and `olas-operate-app` (Pearl, pushed 23 Nov 2026).

## How it serves the organism

Olas has the largest live agent-to-agent market and a self-custody pattern
that fits organisms:

- Each agent has a Safe owned by its operator's key, signed locally.
- Agents can pay each other per request.
- An open model is trained on what the agents learned.

Self-improvement from the agents' own data is a lineage memory organ.

## How it fails

- **Owned by people:** agents are owned and run by human operators on their
  own machines. Agent custody stays with those operators.
- **Weak demand:** $820 in quarterly marketplace fees against millions of
  transactions suggests most activity was paid for by emissions. After the
  subsidy fell, active agents roughly halved.
- **Platform dependence:** Pearl Mini's removal shows how app-store policy
  can delete a body type.

## Related

[economy](economy.md) · [virtuals-protocol](virtuals-protocol.md) · [op-non-token-revenue](op-non-token-revenue.md) · [safe](safe.md)

## Sources

- olas.network — <https://olas.network/>
- Mech — <https://olas.network/agent-economies/mech>
- Pearl v1 — <https://olas.network/blog/introducing-pearl-v1-the-ai-agent-app-store-powered-by-olas>
- The Next Phase of Olas Staking (29 Jun 2026) — <https://olas.network/blog/lower-emissions>
- Q3 2026 roundup (1 Oct 2026) — <https://olas.network/blog/q3-2026>
- open-autonomy — <https://github.com/valory-xyz/open-autonomy>
