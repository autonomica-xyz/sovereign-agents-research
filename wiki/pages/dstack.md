---
title: "dstack"
category: technology
status: stable
sources: [docs/state-of-the-art.md, docs/research-notes.md]
updated: 2026-11-23
---

# dstack

> Open-source framework (github.com/Dstack-TEE) that runs Docker apps in
> confidential VMs with a key management service that releases keys only to
> attested code. It is the most widely used TEE layer for agents in 2026:
> Phala Cloud, NEAR AI Cloud (and through it Brave Leo) and many agent
> projects run on it.

## Details

- **Apps, not machines:** an `app_id` owns keys derived by the KMS; any CVM
  that attests as that app gets them, so bodies are swappable
  ([attestation-gated-key-release](attestation-gated-key-release.md)).
- **On-chain governance:** KMS and upgrade policy can live on Base/Ethereum;
  AppAuth supports a timelock (about 48 h) on upgrades; the DevProof / ERC-733
  draft formalises stages 0–3.
- **Releases:** v0.6.1 (Oct 2026) fixed the guest-agent `/logs` bug;
  v0.6.6 (20 Nov 2026) anchored SEV-SNP TCB policy to AMD bulletins, added
  key-epoch crossing and `dstack-key-recovery`.
- **Zero-downtime upgrade:** two CVMs with the same `app_id`, GetKey-sealed
  state handover; 0 of 503 requests failed vs a 65 s outage in place
  (Andrew Miller, 15 Nov 2026).
- Brave Leo's private chats pin dstack OS measurements in their verifier
  (Oct 2026).

## How it serves the organism

The default way to give an agent a body whose host cannot read its keys, and
to move between bodies without losing them.

## How it fails

- Platform wrapper bugs, not silicon, have been the real breaches:
  [phala-dstack-incident-2026-10](phala-dstack-incident-2026-10.md) (env vars
  read via `/logs`), [phala-inference-breach-2026-11](phala-inference-breach-2026-11.md).
- Mostly TDX; cross-vendor is new.
- Whoever controls the upgrade policy steers the app
  ([op-self-authorized-succession](op-self-authorized-succession.md)).
- **Survival rule:** never keep secrets in container environment variables.

## Related

[phala-cloud](phala-cloud.md) · [near-ai-cloud](near-ai-cloud.md) · [andrew-miller](andrew-miller.md) · [flashbots](flashbots.md)

## Sources

- dstack repository — <https://github.com/Dstack-TEE/dstack>
- dstack paper, arXiv 2509.11555 — <https://arxiv.org/abs/2509.11555>
- dstack v0.6.1 security release — <https://github.com/Dstack-TEE/dstack/releases/tag/v0.6.1>
- dstack-tutorial (DevProof, timelocks) — <https://github.com/amiller/dstack-tutorial>
- ERC-733 — <https://www.erc733.org/>
- Brave Leo verifier — <https://github.com/brave/near-verifier>
