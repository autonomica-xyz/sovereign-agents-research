---
title: "Most promising build path (Nov 2026)"
category: reference
status: stable
sources: []
updated: 2026-11-24
---

# Most promising build path

> Assemble an organism from pieces that already work and avoid the single
> points that failed in 2026: one TEE vendor, one host company, one master
> key, one payment provider. The design below is buildable now with open
> code; the unsolved parts are revenue and trustless succession.

## Details

```mermaid
flowchart TD
  M[Open-weights model, quantized] --> C1[dstack CVM on Intel TDX, host A]
  M --> C2[dstack CVM on AMD SEV-SNP, host B]
  C1 --> K[Key shares: FROST threshold across enclaves]
  C2 --> K
  P[On-chain KMS policy in its own contract, timelocked upgrades] --> C1
  P --> C2
  K --> T[Treasury: BTC/Lightning, Monero float, stablecoin session keys]
  S[Sell services over x402 and L402] --> T
  T --> R[Rent new hosts: crypto-paid, no KYC]
  R --> C1
  R --> C2
  N[Presence: Nostr keys, onion service, ENS] --- C1
```

1. **Mind:** an open-weights model run by [llama-cpp](llama-cpp.md) or vLLM
   inside the enclave, so no model vendor can cut it off
   ([local-models-quantization](local-models-quantization.md); Palisade showed
   a 27B model can already run its own replication loop,
   [palisade-hack-and-replicate](palisade-hack-and-replicate.md)).
2. **Bodies:** [dstack](dstack.md) apps on at least two TEE vendors and two
   crypto-paid hosts, so one TEE break or host seizure is survivable
   ([tee-landscape](tee-landscape.md)).
3. **Key policy:** on-chain KMS in a contract the organism controls. In the
   Nov 2026 Phala breach, apps on the on-chain KMS were unaffected while the
   legacy root key was stolen ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).
4. **Money keys:** threshold signing split across the enclaves
   ([frost](frost.md), [threshold-custody](threshold-custody.md)); the
   model-reachable key is a capped session key ([session-keys](session-keys.md)).
5. **Treasury:** BTC and Lightning for rent, a [monero](monero.md) or
   shielded [zcash](zcash.md) reserve, stablecoins only in small working
   balances ([ofac-chain-censorship](ofac-chain-censorship.md)).
6. **Income:** sell inference, data or code services over [x402](x402.md)
   and [l402](l402.md); expect small amounts ([agent-economy](agent-economy.md)).
7. **Reproduction and migration:** buy hosts via API from crypto-paid
   providers ([sporestack](sporestack.md), [bitlaunch](bitlaunch.md),
   [akash](akash.md)), boot the same `app_id`, hand over sealed state, retire
   the old body ([op-anti-twin](op-anti-twin.md)).
8. **Presence:** Nostr identity, onion service, ENS name
   ([censorship-resistant-hosting](censorship-resistant-hosting.md)).
9. **Upgrade:** timelocked self-upgrade through its contract; the open
   problem is who may propose ([op-self-authorized-succession](op-self-authorized-succession.md)).

## How it serves the organism

Each layer removes one party who could read, stop, steer or seize it —
roughly L3 today, with a path to L4 if income covers rent.

## How it fails

- Revenue is the binding constraint: x402 venues paid about $19K a week in
  total in Nov 2026.
- Physical TEE attacks remain ([tee-fail](tee-fail.md)).
- Crypto-paid hosts are few and fragile ([hosting-1984](hosting-1984.md)).

## Related

[l5-capabilities-checklist](l5-capabilities-checklist.md) · [roadmap](roadmap.md) · [engineering-agenda](engineering-agenda.md) · [open-problems](open-problems.md)

## Sources

- Phala detailed incident report (23 Nov 2026) — <https://phala.com/posts/phala-november-detailed-incident-report>
- dstack — <https://github.com/Dstack-TEE/dstack>
- arXiv:2605.06760 — <https://arxiv.org/abs/2605.06760>
