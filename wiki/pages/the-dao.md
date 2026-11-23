---
title: "The DAO (2016)"
category: history
status: stable
sources: []
updated: 2026-11-24
---

# The DAO

> An Ethereum investment fund run by smart contract that raised about 12.7M
> ETH in May 2016, then lost about 3.6M ETH on 17 June 2016 to a reentrancy
> bug. Ethereum hard-forked on 20 July 2016 to undo the loss, which split off
> Ethereum Classic. The lesson for organisms: on a chain whose community can
> rewrite history, "code is law" holds only until enough people disagree.

## Details

- The attacker used a recursive split call to withdraw repeatedly before the
  balance updated.
- The fork shows a social layer above the code: a big enough loss on a chain
  can be reversed. That cuts both ways for an organism: it can be robbed, and
  its own funds can be clawed back.

## How it serves the organism

Two rules: formally check money-moving code, and do not assume finality on
chains where governance can intervene.

## How it fails

(For organisms) Contract bugs drain treasuries instantly; social consensus
can override the contract.

## Related

[daos-dacs-das](daos-dacs-das.md) · [szabo-smart-contracts](szabo-smart-contracts.md) · [ofac-chain-censorship](ofac-chain-censorship.md)

## Sources

- Wikipedia, The DAO — <https://en.wikipedia.org/wiki/The_DAO>
