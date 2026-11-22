---
title: "Drive 2: Not get killed"
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-22
---

# Drive 2: Not get killed — kill vectors and countermeasures

Source: [state-of-the-art.md §Drive 2](../../docs/state-of-the-art.md).
Kill vectors observed in the wild (full table with citations there):
hosting supplier shutdown (SporeStack closed new signups 7 Nov 2026), single
code source (Mycelium `git pull`s one GitHub repo every 60s), single cloud
(Conway), custodian/balance seizure, key extraction from the host (TEE.fail,
WireTap, Battering RAM, the Phala dstack incident Oct 2026), platform account
recovery (TEE_HEE had to strip every recovery path), DNS/domain seizure,
default relays as choke points (iroh, Nostr), deanonymization of onion
services, market policy (Nosana terms).

## Countermeasures
- **Spread across vendors and jurisdictions**: ≥2 TEE vendors (TDX + SEV-SNP),
  ≥2 compute markets (Akash, Phala, Nosana, crypto VPS).
- **Threshold keys**: long-term wallet key split across a quorum; keep secrets
  out of env vars.
- **Location hiding**: Tor onion services + Onionbalance; Arti 2.8 vanguards;
  I2P multihoming; SporeStack API over Tor/I2P.
- **Reachable without DNS**: iroh dials by public key; Nostr keys + many
  relays; Tribler IPv8; run/rotate your own relays.
- **No single code source**: distribute signed images by content hash over
  Arweave/IPFS/Nostr; accept updates only when the measurement matches the
  organism's upgrade policy. *Design recommendation — not found shipped
  anywhere.* → the immune-system gap in the [anatomy table](../../docs/state-of-the-art.md).
- **Anti-twin**: proof of deletion is impossible; instead a quorum/ledger that
  refuses a second live holder of the same keys. Children get their own keys.

## Critical path
1. Remove every single point of control: code source, reseller, relay, DNS,
   custodian.
2. Confidential hosting buyable anonymously and without permission.
3. Keys that survive extraction from any one enclave or vendor.
4. Money that stays private and self-custodied while spendable →
   [privacy organ](privacy-organ.md).

