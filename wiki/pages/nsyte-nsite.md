---
title: "nsite (NIP-5A) and nsyte"
category: technology
status: stable
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-23
---

# nsite (NIP-5A) and nsyte

> nsite is a static website described by a signed Nostr event that maps paths
> to SHA-256 hashes of files stored on Blossom servers. nsyte is the CLI that
> publishes one. For the organism, this is a face and a code-distribution
> channel that no host or DNS registrar controls.

## Details

- NIP-5A is merged upstream: signed path → SHA-256 manifests, kinds
  15128 / 35128 / 5128.
- nsyte v0.29.0 added NIP-77 negentropy sync (repo quiet since 26 Oct 2026).
- Any gateway can serve an nsite; the content is verified by hash.

## How it serves the organism

Publishes its manifesto, prices and API docs, and its own code
([signed-code-distribution](signed-code-distribution.md)), with no server to
seize.

## How it fails

Gateways and Blossom servers can refuse to serve; the publishing key is the
whole identity unless held by a quorum.

## Related

[blossom](blossom.md) · [nostr](nostr.md) · [body-stack](body-stack.md)

## Sources

- NIP-5A — <https://github.com/nostr-protocol/nips/blob/master/5A.md>
- nsyte — <https://github.com/sandwichfarm/nsyte>
