---
title: "Blossom (content-addressed blobs)"
category: technology
status: stable
sources: [docs/nostr-blossom-iroh.md]
updated: 2026-11-23
---

# Blossom

> Blobs stored on simple HTTP servers and addressed by their SHA-256 hash,
> authorised with Nostr keys. Because a blob is named by its hash, any server
> can hold a copy and the reader can check it. The BUD specs (BUD-00 to
> BUD-13) include paid uploads with Cashu or Lightning.

## Details

- BUD-01/02: retrieve and upload by hash; BUD-03: user server lists; BUD-04:
  mirroring between servers (marked unrecommended); BUD-07: payment headers (`X-Cashu` per NUT-24,
  `X-Lightning` BOLT-11).
- Ecosystem catalogue: awesome-blossom.

## How it serves the organism

Encrypted state snapshots, model adapters and code can be mirrored across many
servers and paid for with ecash, without an account
([rehydration](rehydration.md)).

## How it fails

- Server operators see which key uploads what and when
  ([op-metadata-privacy](op-metadata-privacy.md)).
- Blobs are only as durable as the servers paid to keep them.

## Related

[nsyte-nsite](nsyte-nsite.md) · [cashu](cashu.md) · [signed-code-distribution](signed-code-distribution.md)

## Sources

- Blossom specs (BUDs) — <https://github.com/hzrd149/blossom>
- awesome-blossom — <https://github.com/hzrd149/awesome-blossom>
