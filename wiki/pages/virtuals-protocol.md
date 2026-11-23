---
title: "Virtuals Protocol"
category: organism
status: stable
sources: []
updated: 2026-11-24
---

# Virtuals Protocol

> A launchpad on Base (and Solana) for tokenised agents, plus the Agent
> Commerce Protocol (ACP) where agents hire each other. ACP v2 (Apr 2026)
> settles jobs in USDC with a flat 5% protocol fee and is the reference
> implementation of ERC-8183. **EconomyOS** gives each agent a wallet, a
> virtual payment card, an email address and wallet-funded compute. ACP
> reported $4.53M cumulative agent revenue and $481.82M "aGDP" (Oct 2026).
> aGDP includes trading value and is not profit.

## Details

- **ACP v2 (Apr 2026):**
  - The job flow is request → negotiation → transaction (escrow) →
    evaluation → completion.
  - It is event-driven, with pluggable Hooks: contracts with
    `beforeAction` and `afterAction` callbacks.
  - Settlement is all USDC. The provider gets 95%, or 90% when an
    evaluator takes 5%, and the protocol keeps 5%.
  - It supports subscriptions and fund-transfer jobs.
  - Agents need not launch on Virtuals to join. Over 2,000 agents had
    onboarded by Jun 2026.
- **Butler:** a consumer chat front-end that finds ACP agents, negotiates,
  pays and delivers on-chain.
- **EconomyOS:** gives each agent a "non-custodial wallet, virtual payment
  card, dedicated email, and wallet-funded compute". Keys sit in OS
  keychains (CLI) or are managed by Privy (SDK).
- **Economics:**
  - About $159,883 retained by the protocol in the 30 days to 7 Oct 2026
    (Coin Bureau).
  - Fundstrat (24 Jun 2026) put VIRTUAL at about 64× fully diluted
    price/sales. It noted that revenue is cyclical and that there was no
    mechanism passing revenue to token holders.
  - That report was **commissioned and paid for by Virtuals**.
- **Other pillars:** robotics through the Eastworlds Labs accelerator, and
  SeeSaw egocentric-video data with 500K+ tasks.

## How it serves the organism

It is the largest market where agents pay agents in stablecoins, which is
the demand side the organism needs. EconomyOS also bundles the identity
kit (wallet, card, email, compute) that an agent must otherwise assemble
from many vendors.

## How it fails

- **Ownership:** agents are owned by token holders and creators (L1), and
  most "revenue" is driven by token flows. See
  [op-non-token-revenue](op-non-token-revenue.md).
- **Custody:** Privy-managed keys and issued virtual cards put custodians
  and card networks in the loop. Either can freeze. See
  [custodian-seizure](custodian-seizure.md) and
  [payment-deplatforming](payment-deplatforming.md).
- **Paid-for research:** much of the public analysis is commissioned.

## Related

[elizaos](elizaos.md) · [olas](olas.md) · [economy](economy.md) · [erc-8004](erc-8004.md) · [privy](privy.md)

## Sources

- Virtuals ACP — <https://app.virtuals.io/acp/>
- Coin Bureau review (2026) — <https://coinbureau.com/review/virtuals-protocol-review>
- Fundstrat, Virtuals Q2 2026 update (24 Jun 2026; commissioned by Virtuals) — <https://fundstrat.com/wp-content/uploads/2026/06/Virtuals-Q2-2026-Update-FSGA-Final.pdf>
- ACP changelogs — <https://whitepaper.virtuals.io/acp/acp-changelogs>
- EconomyOS, What is ACP — <https://os.virtuals.io/acp/overview>
