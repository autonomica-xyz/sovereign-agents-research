---
title: "Bitcoin (2008)"
category: money-rail
status: stable
sources: []
updated: 2026-11-24
---

# Bitcoin

> "A purely peer-to-peer version of electronic cash" (Satoshi Nakamoto,
> 31 Oct 2008; network live 3 Jan 2009). For an organism it is the base money
> nobody can freeze at the protocol level, and the settlement layer for
> [lightning](lightning.md), [ark](ark.md), [fedimint](fedimint.md) and
> [cashu](cashu.md).

## Details

- Keys are the only authority: no issuer can blacklist an address (unlike
  [stablecoins](stablecoins.md)); miners or pools can still refuse to include
  transactions ([ofac-chain-censorship](ofac-chain-censorship.md)).
- Transparent ledger: balances and flows are public unless hidden
  ([silent-payments](silent-payments.md), [coinjoin](coinjoin.md)).
- Programmability is limited ([miniscript](miniscript.md),
  [bitcoin-vaults](bitcoin-vaults.md)).
- The 2011–2013 Bitcoin agent design was built on it
  ([bitcoin-wiki-agents](bitcoin-wiki-agents.md)).

## How it serves the organism

Long-term reserve that no one can freeze; sats are the unit of most
agent-native payment rails (L402, Cashu, NWC).

## How it fails

On-chain fees make small payments uneconomic; price volatility; public
balances expose it.

## Related

[lightning](lightning.md) · [b-money](b-money.md) · [public-balance-exposure](public-balance-exposure.md) · [miniscript](miniscript.md)

## Sources

- Nakamoto, "Bitcoin: A Peer-to-Peer Electronic Cash System" (2008) — <https://bitcoin.org/bitcoin.pdf>
