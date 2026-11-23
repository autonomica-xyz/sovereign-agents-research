---
title: "Fedimint"
category: money-rail
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-24
---

# Fedimint

> Federated Chaumian ecash for Bitcoin. A group of guardians runs the mint
> together over AlephBFT consensus and holds deposits in a threshold
> multisig (for example 3-of-4). Users hold blind-signed notes, so the
> federation can't see who owns what. It is private like Cashu, but the
> custodian is a federation instead of one server. v0.13.0 "Steady State"
> shipped on 30 Oct 2026. The public observer tracks 23 federations holding
> about 3.2 BTC (23 Nov 2026).

## Details

- **Consensus:** guardians run AlephBFT. It tolerates a malicious or
  offline minority, and consensus halts (then resumes) if a majority drops.
  It adds about 1 s to payments, and its speed is set by "the slowest of
  the fastest 2/3rds of guardians".
- **Custody and recovery:** funds need `t`-of-`n` guardian signatures. To
  recover a dead federation you need `t` keys plus at least one guardian
  database. The guardian UI backup is encrypted with the guardian
  password. `fedimint-recoverytool` (v0.13.0, Nov 2026) rebuilds the
  on-chain wallet of a decommissioned federation.
- **Modules:** ecash (blind issuance and redemption), wallet (on-chain
  multisig peg-in/out), and Lightning (LNv1/LNv2 through gateways).
- **v0.12.0 (27 Aug 2026)** moved guardian P2P and the client API to Iroh
  1.0 and added recovery without downtime.
- **v0.13.0 (30 Oct 2026):**
  - Fixed stalls "seen on mainnet" that left guardians "connected" but not
    contributing. Dead connections are now detected in about 5 s.
  - Hardened gateway payments.
  - Made peg-outs fail fast when guardians disagree on fees.
- **Activity (observer API, 23 Nov 2026):** 23 listed federations, 19 with
  transactions in the last 7 days, and about 3.20 BTC in deposits in total.
  The largest are Freedom Money (about 0.74 BTC) and Morpheus (about
  0.58 BTC). The observer also records `expiry_timestamp` and `successor`
  for federations that announce a shutdown and a replacement.
- **Repo:** `fedimint/fedimint` (MIT), 709 stars, pushed 23 Nov 2026.

## How it serves the organism

- **Private balance:** the organism's money is invisible to the mint and to
  chain watchers, and Lightning gateways let it pay out instantly. See
  [privacy-organ](privacy-organ.md).
- **Becoming a guardian:** three or more organisms (or nodes of one
  organism) on different hosts could run a federation themselves. The
  treasury would then be held by a threshold of their own bodies, with no
  outside custodian. Iroh networking ([n0-computer](n0-computer.md)) suits
  peers that move between hosts.
- **Succession:** the successor field gives a protocol-level way to migrate
  funds when a federation retires.

## How it fails

- **Guardian majority:** a majority can freeze or steal. Guardians are
  usually known people in one community and can be pressured together.
- **Small and liquidity-bound:** about 3 BTC across all observed
  federations, so exits depend on gateway liquidity.
- **Note loss:** ecash notes are bearer instruments. An organism whose
  wallet state is lost or rolled back loses the notes unless it uses the
  recovery modules.

## Related

[cashu](cashu.md) · [custodian-seizure](custodian-seizure.md) · [privacy-organ](privacy-organ.md) · [threshold-custody](threshold-custody.md) · [n0-computer](n0-computer.md)

## Sources

- Fedimint — <https://fedimint.org>
- How Federations Work — <https://fedimint.org/guardians/how-federations-work>
- v0.13.0 release (30 Oct 2026) — <https://github.com/fedimint/fedimint/releases/tag/v0.13.0>
- Fedimint Observer API — <https://observer.fedimint.org/api/federations>
- fedimint-recoverytool — <https://crates.io/crates/fedimint-recoverytool>
