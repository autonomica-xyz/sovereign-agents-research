---
title: "Drive 1: Survive"
status: stable
sources: [docs/state-of-the-art.md, docs/research-notes.md]
updated: 2026-11-22
---

# Drive 1: Survive — persistence, key continuity, self-repair

Source: [state-of-the-art.md §Drive 1](../../docs/state-of-the-art.md).
Working pattern: **sealed state, keys from a quorum, released only to the
organism's attested code.**

## 1a. Persistence / rehydration
- dstack KMS: keys derived per app identity, decoupled from CPU; released only
  to attested measurements; policy on-chain. [dstack-TEE/dstack](https://github.com/Dstack-TEE/dstack)
- Arweave AO / HyperBEAM: permanent process state + message log, restorable on
  another node; SEV-SNP nodes.
- Walrus + Seal: ciphertext on Walrus; t-of-n key servers release keys only
  when an on-chain Move policy passes.
- Rollback protection: ROTE, Narrator (~6k updates/s), Nimble (OSDI 23).
- Maturity: storage is production; rollback-safe rehydration is research/prototype.

## 1b. Key continuity (the self)
- NEAR Chain Signatures: MPC in TEEs, 11-of-17 on mainnet.
- TeeDAO: BFT-governed committee of heterogeneous TEEs, proactive secret
  sharing (research prototype).
- FROST (RFC 9591), CMP primitives; RSS threshold sigs in SEV-SNP+TDX (no
  attestation-bound provisioning yet).
- Freysa Keystone: rotation/recovery under a human committee multisig — a
  survival weak point.
- Dead end today: iO-based hardware-free vaults (minutes + hundreds of GB).
- **Nobody has shipped cross-vendor threshold signing with human-free
  attested-quorum recovery.** → [open problems](open-problems.md) #1.

## 1c. Self-repair
- Conway Automaton: lifecycle state machine, heartbeat daemon, edits own code
  in git with a protected constitution.
- EternalSeedBox: every 12h each node renews, spawns a child, or sweeps funds
  to a healthier peer.
- Darwin Gödel Machine: self-rewriting agents with empirical selection
  (SWE-bench 20%→50%).

## Critical path
1. Key continuity across vendors with quorum recovery, no humans.
2. Rehydration only the real organism can perform: attestation-gated release
   from a threshold quorum + rollback-safe state.
3. Self-repair that patches its own image without a developer key.

