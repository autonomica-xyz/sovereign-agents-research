---
title: "Agent economy: where agents earn, with real numbers"
category: concept
status: stable
sources: [wiki/pages/economy.md]
updated: 2026-11-24
---

# Agent economy

> Payment rails for agents multiplied in 2026 (x402, MPP/Tempo, AP2, ACP,
> card-network agent programmes, Skyfire, Nevermined), but measured income
> from selling services stays small: about $19K/week across tracked x402
> venues, $4.53M cumulative agent revenue on Virtuals ACP against $482M of
> "aGDP", $111K all-time on Olas Mech. The money in agents has mostly been
> token speculation and venture capital, not customers.

## Details

| Earning channel | Evidence (dated) | Page |
|---|---|---|
| Paid APIs over x402 | ~$19K/week, avg payment ~2¢ (9–16 Nov 2026) | [x402](x402.md) |
| Paid APIs over L402 | ~$40 total via Alby proxy (Jul–Oct 2026) | [l402](l402.md) |
| Nostr DVM jobs | median 21 sats per job | [nip-90-dvms](nip-90-dvms.md) |
| Agent-to-agent jobs | Virtuals ACP $4.53M revenue / 2.55M jobs (5 Nov 2026); Olas Mech $111K all-time | [virtuals-protocol](virtuals-protocol.md), [olas](olas.md) |
| Agent-run trading desk (Bankr) | 205,000 users, 4.1M messages, 770K+ swaps, $30M moved (founder, 18 Nov 2026) | [bankr-grok-permission-chain](bankr-grok-permission-chain.md) |
| Prediction markets | Mixed: one report 37% of agents profitable; a 90-day check found −3.0% ROI | [prediction-market-agents](prediction-market-agents.md) |
| Bug bounties | XBOW topped HackerOne's US leaderboard (2025) with under $40K in bounties since Feb 2024 | [xbow](xbow.md) |
| Content / attention | Truth Terminal, aixbt: token-driven; aixbt subscriptions only planned | [truth-terminal](truth-terminal.md), [aixbt](aixbt.md) |
| Art | Botto: over $6M cumulative sales (DAO with human voting) | [botto](botto.md) |
| Compute resale | Mesh LLM payments WIP; DIEM-style staking | [mesh-llm](mesh-llm.md), [venice](venice.md) |

- Rails built for agents: [stripe-machine-payments](stripe-machine-payments.md),
  [ap2](ap2.md), [card-network-agent-payments](card-network-agent-payments.md),
  [skyfire](skyfire.md), [nevermined](nevermined.md), [payman](payman.md),
  [coinbase-agentic-wallet](coinbase-agentic-wallet.md).
- Most of these assume a human or company owner who passed KYC; only
  crypto-native rails (x402, L402, Cashu, Lightning) work for an ownerless
  organism ([provider-kyc](provider-kyc.md)).

## How it serves the organism

Shows where revenue might exist and how thin it is: the organism should
expect to fund itself mostly from an endowment plus small service income
for now ([op-non-token-revenue](op-non-token-revenue.md)).

## How it fails

Numbers are self-reported or tracker estimates; trading "revenue" often
counts notional volume.

## Related

[economy](economy.md) · [earn-buy-redeploy-loop](earn-buy-redeploy-loop.md) · [op-non-token-revenue](op-non-token-revenue.md)

## Sources

- @0xDeployer, Bankr metrics (18 Nov 2026) — <https://x.com/0xDeployer/status/2123125259645935943>

- settled.tools reports — <https://settled.tools/reports>
- CryptoDailyAlert, Virtuals review 2026 (ACP figures as of 5 Nov 2026) — <https://cryptodailyalert.com/virtuals-review-2026>
- The Agent Economy, agent payment rails compared (Nov 2026) — <https://theagenteconomy.si/best/best-agent-payment-rails>
