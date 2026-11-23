---
title: "ENS (Ethereum Name Service)"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# ENS

> Names like `alice.eth` held as tokens on Ethereum and resolved by smart
> contract. ENS cancelled its planned L2 "Namechain" in February 2026 and
> launched ENSv2 directly on Ethereum mainnet on 27 Oct 2026, with
> hierarchical registries and finer permissions.

## Details

- A name is owned by a key, paid by annual rent in ETH; nobody can take it
  except by expiry or contract rules.
- `contenthash` records point to IPFS, Arweave or onion content; gateways
  (eth.limo) bridge to the web but are central.
- ENS DAO governs the root and fees.

## How it serves the organism

A human-readable name that only its key can change, payable by itself.

## How it fails

Expires if it forgets to pay rent; gateways and browsers are chokepoints;
the root is controlled by the ENS DAO and multisig; owning it on a public
chain links the name to a wallet.

## Related

[handshake](handshake.md) · [namecoin](namecoin.md) · [dns-seizure](dns-seizure.md) · [censorship-resistant-hosting](censorship-resistant-hosting.md)

## Sources

- ENS, "ENSv2 is live on mainnet" (27 Oct 2026) — <https://ens.domains/blog/post/ensv2-live-on-mainnet>
- ENS, "ENS is staying on Ethereum" (Feb 2026) — <https://ens.domains/blog/post/ens-staying-on-ethereum>
