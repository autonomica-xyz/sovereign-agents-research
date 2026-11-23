---
title: "Internet Computer (ICP) canisters"
category: compute
status: stable
sources: []
updated: 2026-11-24
---

# ICP canisters

> Code on the Internet Computer runs in "canisters" that pay for their own
> execution with prepaid **cycles** (reverse gas). A canister whose
> controllers are removed ("blackholed") cannot be changed or deleted by
> anyone except an exceptional NNS governance proposal; it lives until its
> cycles run out. This is the closest production substrate to code that pays
> its own rent.

## Details

- Canisters can hold ICP or tokens and convert them to cycles, so a canister
  can fund itself from its own earnings.
- A blackholed canister cannot upgrade itself either (no controller), which
  rules out evolution unless it keeps itself as its own controller.
- Subnet node providers can in principle read canister memory (no TEE by
  default); the NNS DAO can vote to remove code.

## How it serves the organism

Self-paying execution with no account; mature tooling; HTTP outcalls and
threshold signatures (chain-key) let a canister hold Bitcoin and Ethereum
keys split across a subnet.

## How it fails

NNS governance is a kill path; node providers are known entities in data
centres; memory is not confidential; models must be tiny or run off-chain.

## Related

[near-mpc](near-mpc.md) · [threshold-custody](threshold-custody.md) · [censorship-resistant-hosting](censorship-resistant-hosting.md)

## Sources

- ICP docs, trust in canisters — <https://docs.internetcomputer.org/guides/canister-management/trust-in-canisters/>
- ICP docs, canister settings — <https://docs.internetcomputer.org/guides/canister-management/settings/>
- DFINITY forum, "Can a blackholed canister self delete?" — <https://forum.dfinity.org/t/can-a-blackholed-canister-self-delete/27652>
