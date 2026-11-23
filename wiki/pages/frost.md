---
title: "FROST threshold Schnorr signatures"
category: technology
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-23
---

# FROST

> Flexible Round-Optimized Schnorr Threshold signatures, standardised as
> RFC 9591 (2024). t of n parties produce one ordinary Schnorr signature, so
> outsiders cannot tell a quorum signed. It fits Bitcoin Taproot, Nostr keys
> and Ed25519 chains.

## Details

- Two rounds; first round can be preprocessed.
- Used by [near-mpc](near-mpc.md) (added alongside Cait-Sith),
  [frostr](frostr.md) (Nostr), and research systems such as RSS and the
  "Sovereign Execution Consensus" paper (cross-vendor FROST design).

## How it serves the organism

The organism's Nostr identity or Taproot wallet can be held by a quorum of
its own bodies while still looking like one normal key.

## How it fails

- Nonce handling bugs leak the key (FROSTR bifrost 2.0.2 nonce-reuse issue,
  8 Nov 2026).
- Rolled-back enclaves can be tricked into reusing nonces
  ([rollback-protection](rollback-protection.md)).

## Related

[threshold-custody](threshold-custody.md) · [frostr](frostr.md) · [nostr](nostr.md)

## Sources

- RFC 9591 — <https://www.rfc-editor.org/rfc/rfc9591>
- Sovereign Execution Consensus (Zenodo) — <https://doi.org/10.5281/zenodo.18135001>
