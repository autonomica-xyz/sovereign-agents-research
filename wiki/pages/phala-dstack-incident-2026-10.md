---
title: "Phala dstack guest-agent incident (8–12 Oct 2026)"
category: attack
status: stable
sources: [docs/adversarial-review.md, docs/research-notes.md]
updated: 2026-11-23
---

# Phala dstack guest-agent incident (Oct 2026)

> Between 8 and 12 Oct 2026 an attacker abused a path bug in dstack's
> `guest-agent` (versions v0.3.1–v0.6.0) to read container logs and
> environment variables of a small set of Phala Cloud apps, and on one host
> used a CVM-to-host network gap to steal a gateway admin token. Phala says
> enclave, sealing and KMS keys were not accessed.

## Details

- Crafted `/logs/<container_name>` values were inserted unescaped into Docker
  API paths, turning a log read into a container inspect (`Config.Env`).
- Detected 12 Oct 19:28 UTC; host isolated within 40 minutes; fixes by
  15 Oct; fixed images v0.6.1 / v0.5.12; forced upgrades from 20 Nov 2026.
- The attacker changed DNS-credential and ACME settings on one gateway.
- These are Phala's own findings; no independent forensic report.

## How it serves the organism

The lesson: the TEE silicon held, the **platform around it** leaked. Anything
in env vars or logs is outside the enclave's protection.

## How it fails

(For the organism) Secrets in environment variables (API keys, Cashu tokens,
wallet seeds) would have been read. Keep long-term secrets only in sealed
storage or key quorums ([threshold-custody](threshold-custody.md)).

## Related

[phala-inference-breach-2026-11](phala-inference-breach-2026-11.md) · [dstack](dstack.md) · [phala-cloud](phala-cloud.md)

## Sources

- Phala post-mortem (Oct 2026) — <https://phala.com/posts/2026-10-post-mortem-dstack-guest-agent-vulnerability>
- dstack v0.6.1 — <https://github.com/Dstack-TEE/dstack/releases/tag/v0.6.1>
- Phala status incident (resolved 19 Oct 2026) — <https://status.phala.network/incident/1088475>
