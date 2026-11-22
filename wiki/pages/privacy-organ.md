---
title: "The privacy organ"
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-22
---

# The privacy organ (survival, not luxury)

Source: [state-of-the-art.md §2c](../../docs/state-of-the-art.md). Privacy
exists so no host or attacker can see and steal keys, money, mind, location.

## Confidential execution (anti-theft)
- dstack CVMs on TDX; Akash Confidential Compute (`tee: cpu | cpu-gpu`,
  SEV-SNP/TDX, NVIDIA GPU CC, experimental); NVIDIA Blackwell multi-GPU CC;
  Marlin Oyster (Nitro).
- Confidential inference: open-weight models in GPU TEEs on Phala (120.5B
  tokens/day, 5 Nov 2026), NEAR AI, Routstr providers.
- Limits: physical bus attacks (TEE.fail etc.); wrapper bugs (dstack).
  Defence: threshold-split long-term keys, short-lived hot keys, multiple
  vendors.

## Financial privacy (don't show your balance to predators)
- Cashu: blind-signed tokens, NUT-11 P2PK; trade-off: the mint is a custodian.
- Lightning: onion-routed but pubkey + channels visible; Lightning Agent Tools
  adds remote signer + scoped macaroons.
- Ark (Arkade live Oct 2025; Second's Bark on mainnet Jun 2026): off-chain
  VTXOs, unilateral exit; Bark blinded mailbox.
- Silent payments (BIP-352): one static address, unlinkable receipts; Sparrow,
  Cake, Dana, BlindBit; Bitcoin Core support unreleased.
- JoinMarket NG 0.43.0 self-custodial; original JoinMarket archived "do not use".
- Anti-pattern: survival balances on public chain addresses (Conway's USDC
  wallet on Base shows anyone how close it is to death).

## Verification status
confidentialinference.net: **0 of 13 providers fully attested** (22 Nov 2026).
→ [open problems](open-problems.md) #4.


## Update 2026-11-22 — financial privacy rails (research pass 1)

- Cashu: Nutshell 0.20.3 shipped **NUT-28 Pay-to-Blinded-Key (P2BK)** —
  ecash locked without revealing the receiver's key to the mint; mint can no
  longer link multiple P2PK spends — [NUT-28](https://cashubtc.github.io/nuts/28).
  **NUT-24** now specifies native HTTP-402 ecash payment (X-Cashu header,
  NUT-18/26 payment requests) — [NUT-24](https://cashubtc.github.io/nuts/24).
  CDK v0.18 (Q3 report, 1 Nov): NUT-16 fountain QR, NUT-25 BOLT12,
  durable melt coordination — [blog](https://blog.cashu.space/q3-2026-highlights).
- Silent payments: BIP-352 base protocol **merged into Bitcoin Core master**
  (PR #35301, 23 Sep) + scriptSig fix (#36338, 7 Oct) — but no Core release
  ships wallet support yet (sending #35302, receiving #32966 still open);
  libsecp256k1 module shipped in 0.8.0.
- Ark family: Bark 0.8.1 (5 Nov) adds **pre-signed emergency-exit CPFP**
  transactions and reproducible nix builds —
  [changelog](https://second.tech/docs/changelog). Lightning Labs
  **Wavelength** went live on mainnet 23 Oct: self-custodial, Ark-like,
  with an MCP server, L402 support and **receive-only macaroons for agents**
  (300k sat account cap, ~2-week VTXO refresh) —
  [launch post](https://lightning.engineering/posts/2026-10-23-wavelength-mainnet-launch/).
  V-PACK (stateless VTXO verification standard) and hArk (hash-lock
  refresh) tracked by [Optech](https://bitcoinops.org/en/topics/ark).
