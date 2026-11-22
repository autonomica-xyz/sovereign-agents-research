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

