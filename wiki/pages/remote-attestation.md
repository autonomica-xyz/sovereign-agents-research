---
title: "Remote attestation"
category: concept
status: stable
sources: []
updated: 2026-11-24
---

# Remote attestation

> A signed report from the hardware stating what code runs inside a TEE and
> at what patch level. It is only as good as the verifier: it must check the
> measurement against a reproducible build, the TCB level against vendor
> bulletins, and the signing chain against revocation lists.

## Details

- Phala's 2026 root-key theft happened because replica onboarding checked
  only the OS image and a dev-mode KMS approved everything
  ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)).
- Physical attacks can extract attestation keys and forge quotes
  ([wiretap](wiretap.md), [tee-fail](tee-fail.md)).
- On-chain verifiers: [automata](automata.md).

## How it serves the organism

The gate for releasing its keys only to its own code
([attestation-gated-key-release](attestation-gated-key-release.md)).

## How it fails

Forged quotes, stale TCBs and lax policies all pass a naive check.

## Related

[tee-landscape](tee-landscape.md) · [signed-code-distribution](signed-code-distribution.md)

## Sources

- Oasis, "A cup of TEE, please" — <https://oasis.net/blog/tees-remote-attestation-process>
- Automata DCAP docs — <https://docs.ata.network/tee-overview/tee-verifiers/intel-sgx-tdx-dcap>
