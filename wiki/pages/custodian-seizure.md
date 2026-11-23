---
title: "Custodian or issuer seizure"
category: attack
status: stable
sources: []
updated: 2026-11-23
---

# Custodian or issuer seizure

> Money someone else can freeze is not the organism's money. USDC and USDT
> issuers can blacklist addresses; ecash mints, federations, exchanges and
> custodial agent wallets can refuse withdrawals or vanish. After the US
> sanctioned Tornado Cash on 8 Aug 2022, Circle froze USDC held in the listed
> addresses (about 75,000 USDC).

## Details

- Issuer risk: [stablecoins](stablecoins.md) freeze at the contract level.
- Mint risk: a [cashu](cashu.md) mint can rug or be shut down; a
  [fedimint](fedimint.md) federation needs a threshold of guardians to collude
  or be coerced.
- Platform risk: custodial agent wallets (Bankr's, Conway's) are controlled
  by the platform operator, not the agent
  ([bankr-grok-permission-chain](bankr-grok-permission-chain.md)).
- Provider-balance risk: prepaid hosting credit dies with the host
  ([supplier-shutdown](supplier-shutdown.md)).

## How it serves the organism

A rule: keep only working capital in custodial forms, spread over several
custodians; keep the reserve in self-custody under a key quorum
([threshold-custody](threshold-custody.md)).

## How it fails

(For the organism) One decision by an issuer or custodian ends its
metabolism.

## Related

[stablecoins](stablecoins.md) · [cashu](cashu.md) · [fedimint](fedimint.md) · [public-balance-exposure](public-balance-exposure.md) · [economy](economy.md)

## Sources

- US Treasury sanctions Tornado Cash (8 Aug 2022) — <https://home.treasury.gov/news/press-releases/jy0916>
- Cointelegraph, Circle freezes Tornado Cash addresses (Aug 2022) — <https://cointelegraph.com/news/circle-freezes-blacklisted-tornado-cash-smart-contract-addresses>
- Circle, "The Responsibility of Trust" — <https://www.circle.com/blog/the-responsibility-of-trust>
