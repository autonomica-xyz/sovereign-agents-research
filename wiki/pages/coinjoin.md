---
title: "CoinJoin and Bitcoin mixing"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# CoinJoin

> Many users combine inputs into one Bitcoin transaction with equal-sized
> outputs so ownership links break (Maxwell, 2013). The main coordinators
> were shut by legal pressure: zkSNACKs stopped Wasabi's coordinator in June
> 2024 and the Samourai Wallet founders were sentenced in November 2025 to
> five and four years in prison; no pardon had been issued as of Sep 2026 (TFTC).

## Details

- Community-run Wasabi/WabiSabi coordinators and JoinMarket (maker/taker,
  no central coordinator) still operate.
- PayJoin (BIP 77/78) mixes inside ordinary payments.

## How it serves the organism

Breaks the link between earnings and its spending wallets on Bitcoin.

## How it fails

Coordinators are legal targets; exchanges flag mixed coins; amount and
timing analysis.

## Related

[bitcoin](bitcoin.md) · [silent-payments](silent-payments.md) · [tornado-cash](tornado-cash.md) · [ofac-chain-censorship](ofac-chain-censorship.md)

## Sources

- IRS-CI, Samourai founders sentenced — <https://www.irs.gov/compliance/criminal-investigation/founders-of-samourai-wallet-cryptocurrency-mixing-service-sentenced-to-five-and-four-years-in-prison>
- TFTC, "Keonne and Bill are still in prison" — <https://www.tftc.io/keonne-rodriguez-william-hill-pardon-samourai>
- Bitcoin Optech, coinjoin — <https://bitcoinops.org/en/topics/coinjoin/>
- JoinMarket — <https://github.com/JoinMarket-Org/joinmarket-clientserver>
