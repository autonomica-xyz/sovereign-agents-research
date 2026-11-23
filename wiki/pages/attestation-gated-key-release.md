---
title: "Attestation-gated key release"
category: concept
status: stable
sources: [docs/state-of-the-art.md, docs/research-notes.md]
updated: 2026-11-23
---

# Attestation-gated key release

> The organism's keys are never stored with a body. A key service (ideally a
> quorum) hands them only to a host that proves, by hardware attestation, that
> it is running the organism's exact code. This is how the "self" survives
> moving between hosts it does not trust.

## Details

- **dstack KMS** derives keys per app identity and releases them only to
  measurements allowed by an on-chain policy; keys are decoupled from any one
  CPU ([dstack](dstack.md)).
- **NEAR Shade Agents** register an attestation with a contract; the contract
  then signs through [near-mpc](near-mpc.md) for that agent
  ([near-shade-agents](near-shade-agents.md)).
- **Walrus + Seal** release decryption keys from t-of-n key servers only when an
  on-chain policy passes ([walrus-seal](walrus-seal.md)).
- **Lit Protocol** runs threshold keys inside TEEs and executes "Lit Actions"
  that decide when to sign ([lit-protocol](lit-protocol.md)).
- **Zero-downtime handover:** Andrew Miller showed (15 Nov 2026) a stateful
  dstack app upgraded by booting a second CVM with the same `app_id`, handing
  state over with a GetKey-sealed handover and deleting the old one. On Phala,
  an in-place update caused a 65 s outage; the double-buffered handover had
  0 failed requests out of 503.

## How it serves the organism

Bodies become disposable. Losing a host loses no secrets, because the host
never had the long-term key, only a session.

## How it fails

- Attestation proves a measurement, not a safe host: physical interposers forge
  quotes ([tee-fail](tee-fail.md), [wiretap](wiretap.md),
  [battering-ram](battering-ram.md)).
- If the key service is one operator, the operator is the throat
  ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md):
  Phala rotated its KMS root key after attackers obtained app credentials).
- Whoever can change the allowed-measurement policy can steer the organism
  ([op-self-authorized-succession](op-self-authorized-succession.md)).

## Related

[threshold-custody](threshold-custody.md) · [rehydration](rehydration.md) · [survive](survive.md) · [op-cross-vendor-key-recovery](op-cross-vendor-key-recovery.md)

## Sources

- dstack repository — <https://github.com/Dstack-TEE/dstack>
- dstack paper, arXiv 2509.11555 — <https://arxiv.org/abs/2509.11555>
- Andrew Miller on X (15 Nov 2026) — <https://x.com/socrates1024/status/2121830789327282680>
- Phala November preliminary incident report (10 Nov 2026) — <https://phala.com/posts/phala-november-preliminary-incident-report>
