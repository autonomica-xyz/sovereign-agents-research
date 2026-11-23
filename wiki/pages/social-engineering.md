---
title: "Social engineering of agents"
category: attack
status: stable
sources: []
updated: 2026-11-24
---

# Social engineering of agents

> Talking an agent, or the humans and dashboards around it, into moving
> money. Real cases: Freysa (Nov 2024) paid its prize pool after a crafted
> message; aixbt (18 Mar 2025) sent 55.5 ETH after an attacker got into its
> dashboard and queued malicious replies; Bankr paid out through a
> Grok-permission chain (2026); the Bybit theft (Feb 2025) began with a
> compromised developer machine.

## How it serves the organism

Every input is adversarial: money moves only through rules below the model
([key-encumbrance](key-encumbrance.md)).

## How it fails

Operator dashboards and admin panels are softer than the agent itself.

## Related

[freysa](freysa.md) · [bankr-grok-permission-chain](bankr-grok-permission-chain.md) · [prompt-injection-drain](prompt-injection-drain.md) · [wallet-drainers](wallet-drainers.md)

## Sources

- Cointelegraph, aixbt dashboard hack — <https://cointelegraph.com/news/hacker-breaches-ai-crypto-bot-aixbt-steals-55-eth>
- Safe{Wallet} statement on Bybit — <https://x.com/safe/status/1894768522720350673>
