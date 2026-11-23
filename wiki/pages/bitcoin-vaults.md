---
title: "Bitcoin vaults and covenants"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Bitcoin vaults and covenants

> A vault forces withdrawals through a delay during which a recovery key can
> claw them back. True vaults need covenants (OP_CTV, OP_CAT, OP_CCV); OP_VAULT
> (BIP 345) was withdrawn in favour of OP_CHECKCONTRACTVERIFY. As of
> November 2026 no covenant soft fork is scheduled for activation.

## Details

- Today's workaround: pre-signed transactions with deleted keys, or
  miniscript time locks ([miniscript](miniscript.md)).

## How it serves the organism

A thief who steals the hot key must wait out the delay while the organism's
watchtower claws funds back.

## How it fails

Not available natively; pre-signed designs are brittle and need an online
watcher.

## Related

[bitcoin](bitcoin.md) · [miniscript](miniscript.md) · [ark](ark.md)

## Sources

- BIP 345 (OP_VAULT) — <https://bitcoin.org/bip/345/>
- Bitcoin Optech, OP_CHECKTEMPLATEVERIFY — <https://bitcoinops.org/en/topics/op_checktemplateverify/>
- Bitcoin Power Law, "Bitcoin covenants: what comes next?" (Nov 2026) — <https://bitcoin-powerlaw.com/en/magazin/covenants>
