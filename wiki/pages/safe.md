---
title: "Safe (smart-contract multisig)"
category: technology
status: stable
sources: []
updated: 2026-11-24
---

# Safe

> The dominant smart-contract account on EVM chains (formerly Gnosis Safe):
> m-of-n owners, modules and guards. It held $57.64B at the end of Q3 2026
> across 65.7M Safes (Safe Foundation report, 30 Oct 2026). The Feb 2025
> Bybit theft (~$1.5B) came through a Safe{Wallet} developer machine
> compromised by Lazarus, which let the attackers present Bybit's signers a
> disguised malicious transaction; the Safe contracts were not at fault.

## How it serves the organism

On-chain policy: owners can be its own key shares on different hosts, with
spending limits and time locks enforced by the chain.

## How it fails

Signers trust a front end; a malicious UI or blind signing drains funds.
Owners and modules are public.

## Related

[erc-4337](erc-4337.md) · [session-keys](session-keys.md) · [threshold-custody](threshold-custody.md)

## Sources

- Safe Foundation Q3 2026 report — <https://safefoundation.org/reports/q3-2026>
- Safe, Bybit incident statement — <https://x.com/safe/status/1894768522720350673>
