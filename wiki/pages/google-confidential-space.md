---
title: "Google Confidential Space"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# Google Confidential Space

> Google Cloud service that runs a container image in a Confidential VM
> and issues attestation tokens which other parties' KMS or workload
> identity can check before releasing keys or data. The workload operator
> cannot inspect the running container.

## How it serves the organism

Attestation-gated key release on a big, reliable cloud
([attestation-gated-key-release](attestation-gated-key-release.md)).

## How it fails

Google account, billing identity and policy; Google is in the trust base.

## Related

[tee-landscape](tee-landscape.md) · [azure-confidential-computing](azure-confidential-computing.md) · [aws-nitro-enclaves](aws-nitro-enclaves.md)

## Sources

- Google Cloud, Confidential Space overview — <https://cloud.google.com/docs/security/confidential-space>
