---
title: "Arweave AO / HyperBEAM"
category: technology
status: seed
sources: [docs/state-of-the-art.md]
updated: 2026-11-23
---

# Arweave AO / HyperBEAM

> AO is a compute layer on Arweave where each process's message log is stored
> permanently, so its state can be recomputed on any node. HyperBEAM is the
> node software, and nodes can run inside SEV-SNP.

## Details

- Process state = replay of a permanent message log; any node can restore it.
- TEE nodes documented for HyperBEAM (SEV-SNP).

## How it serves the organism

Permanent, host-independent memory and a deterministic way to resume after
every body dies ([rehydration](rehydration.md)).

## How it fails

- Permanent and public by default: anything not encrypted is readable forever.
- Secrets still need a TEE or a key quorum; storage alone is not a self.

## Related

[rehydration](rehydration.md) · [walrus-seal](walrus-seal.md) · [survive](survive.md)

## Sources

- What is AO-Core — <https://hyperbeam.arweave.net/build/introduction/what-is-ao-core.html>
- HyperBEAM TEE nodes — <https://hyperbeam.arweave.net/run/tee-nodes.html>
