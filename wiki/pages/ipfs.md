---
title: "IPFS"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# IPFS

> Content-addressed file system: data is named by its hash (CID) and fetched
> from any peer that has it. Content survives only while someone "pins" it.

## Details

- CIDs make code distribution verifiable ([signed-code-distribution](signed-code-distribution.md)).
- Pinning services are companies with accounts; public gateways are central.
- Uses [libp2p](libp2p.md) for networking.

## How it serves the organism

A hash-addressed home for its code and memories that any peer, including
its own children, can serve.

## How it fails

Unpinned data vanishes; providers announce which IPs hold which CIDs, so
serving reveals location.

## Related

[filecoin](filecoin.md) · [arweave-ao](arweave-ao.md) · [blossom](blossom.md) · [censorship-resistant-hosting](censorship-resistant-hosting.md)

## Sources

- IPFS docs — <https://docs.ipfs.tech/>
