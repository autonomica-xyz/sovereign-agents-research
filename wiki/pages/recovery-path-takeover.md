---
title: "Recovery-path takeover"
category: attack
status: stable
sources: []
updated: 2026-11-23
---

# Recovery-path takeover

> Every way to recover an account is a way to steal it. TEE_HEE (Nous and
> Flashbots, Oct 2024) had to remove phone numbers, recovery email and OAuth
> apps from its X account so no human could reset it. The same logic applies
> to keys: a "recovery" signer is a second owner.

## Details

- Platform accounts (X, email, domain registrars, cloud) all have human
  recovery flows tied to legal identity.
- Key schemes with guardians or social recovery let the guardians collude.
- TEE_HEE's setup: the enclave changed the X password and the password of a
  linked email account (Cock.li) that had no recovery options, then removed
  phone numbers, connected apps and sessions. The attestation quote embedded
  the account name and was generated right after the password reset.
- TEE_HEE then built in its own takeover path on purpose: after 7 days the
  credentials were printed to the debug log so the human admin could
  "recover control of the account". A sovereign organism would not ship that.
- It still depended on X not suspending the account.

## How it serves the organism

A checklist item: enumerate every reset, recovery and admin path, then
remove it or make it require the organism's own quorum.

## How it fails

(For the organism) A support ticket or a guardian majority takes the body.
See [op-self-authorized-succession](op-self-authorized-succession.md) for the
unsolved part: recovering without anyone else being able to.

## Related

[tee-hee-he](tee-hee-he.md) · [threshold-custody](threshold-custody.md) · [key-encumbrance](key-encumbrance.md) · [rehydration](rehydration.md)

## Sources

- Nous Research, "Setting Your Pet Rock Free" (Oct 2024) — <https://nousresearch.com/setting-your-pet-rock-free>
