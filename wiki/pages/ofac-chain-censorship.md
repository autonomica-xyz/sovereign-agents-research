---
title: "OFAC and chain-level censorship"
category: attack
status: stable
sources: []
updated: 2026-11-24
---

# OFAC and chain-level censorship

> Sanctions can push block builders, relays, RPC providers, stablecoin
> issuers and front ends to refuse an address. After the Tornado Cash
> sanctions (Aug 2022), most Ethereum blocks briefly went through censoring
> MEV-Boost relays; on 22 Nov 2026 MEV Watch showed 11.8% of relay payload
> deliveries through OFAC-censoring relays. Stablecoin issuers freeze
> addresses directly.

## Details

- Censored transactions still land, just slower, while some builders and
  validators include them.
- USDC and USDT have admin freeze functions ([stablecoins](stablecoins.md)).
- RPC providers (Infura, Alchemy) and front ends block sanctioned addresses.

## How it serves the organism

Explains why BTC, Monero or self-run nodes beat stablecoins on hosted RPC
for its core treasury.

## How it fails

If the organism's addresses get listed, every compliant intermediary cuts
it off at once.

## Related

[tornado-cash](tornado-cash.md) · [the-dao](the-dao.md) · [custodian-seizure](custodian-seizure.md)

## Sources

- MEV Watch — <https://www.mevwatch.info/>
- U.S. Treasury, Tornado Cash delisting (21 Mar 2025) — <https://home.treasury.gov/news/press-releases/sb0057>
