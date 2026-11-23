---
title: "Public balance exposure"
category: attack
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Public balance exposure

> An organism whose wallet sits on a transparent chain tells every predator
> how much it has, who pays it and where it spends. Conway Automaton agents
> hold USDC on Base; EternalSeedBox funds nodes from on-chain BTC. Spending
> traces link bodies to each other and to suppliers.

## Details

- Balance visibility invites targeted prompt-injection, social engineering
  and freezes ([custodian-seizure](custodian-seizure.md)).
- Payments to a host link the wallet to a server; payments between parent
  and child map the lineage.
- Options: [cashu](cashu.md) or [fedimint](fedimint.md) ecash (private but
  custodial), Lightning (better payer privacy, channels are visible),
  [silent-payments](silent-payments.md), [monero](monero.md), [ark](ark.md).

## How it serves the organism

Privacy is a survival organ here: what it cannot see, a predator cannot aim
at ([privacy-organ](privacy-organ.md)).

## How it fails

(For the organism) It becomes a public bounty and its whole family tree is
mapped.

## Related

[privacy-organ](privacy-organ.md) · [stablecoins](stablecoins.md) · [conway-automaton](conway-automaton.md) · [op-metadata-privacy](op-metadata-privacy.md)

## Sources

- Conway Automaton repo — <https://github.com/Conway-Research/automaton>
- Wiki state of the art — [docs/state-of-the-art.md](../../docs/state-of-the-art.md)
