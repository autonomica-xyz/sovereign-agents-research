---
title: "Session keys and spending permissions"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Session keys

> Short-lived keys with narrow rights (which contracts, how much, until
> when) granted by a smart account. Standards include ERC-7715 permission
> requests and ERC-7579 modules. For an agent, the hot key that the model can
> reach should be a session key, never the root.

## How it serves the organism

Caps loss from a prompt-injected or stolen runtime: the attacker gets one
session's budget, not the treasury.

## How it fails

The "Signed, Valid, and Unauthorized" study found wallet mandates that
verify correctly but still authorise the wrong thing
([prompt-injection-drain](prompt-injection-drain.md)).

## Related

[erc-4337](erc-4337.md) · [eip-7702](eip-7702.md) · [key-encumbrance](key-encumbrance.md)

## Sources

- ERC-7715 — <https://eips.ethereum.org/EIPS/eip-7715>
- ERC-7579 — <https://eips.ethereum.org/EIPS/eip-7579>
