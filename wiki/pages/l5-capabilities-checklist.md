---
title: "L5 capabilities checklist vs state of the art"
category: reference
status: stable
sources: []
updated: 2026-11-24
---

# L5 capabilities checklist

> Each capability an L5 organism needs, with the best existing piece (Nov
> 2026) and the gap. Green means shipped and usable; amber means exists but
> with a chokepoint; red means not done.

## Details

| Capability | Best current piece | State | Gap |
|---|---|---|---|
| Mind runs without a model vendor | open weights + [llama-cpp](llama-cpp.md), [local-models-quantization](local-models-quantization.md) | green | quality below frontier |
| Private inference | TEE GPUs ([nvidia-confidential-computing](nvidia-confidential-computing.md)), [venice](venice.md) | amber | host breaches ([phala-inference-breach-2026-11](phala-inference-breach-2026-11.md)) |
| Keys no human has seen | TDX-generated keys ([tee-hee-he](tee-hee-he.md)), [near-mpc](near-mpc.md) | amber | single-vendor TEEs |
| Keys survive host loss | [threshold-custody](threshold-custody.md), [frost](frost.md) | amber | cross-vendor recovery ([op-cross-vendor-key-recovery](op-cross-vendor-key-recovery.md)) |
| Spending rules below the model | [session-keys](session-keys.md), [turnkey](turnkey.md) policies | green | custodial variants |
| Permissionless payments in | [x402](x402.md), [l402](l402.md), [cashu](cashu.md) | green | tiny demand |
| Real revenue | [agent-economy](agent-economy.md) | red | covers almost no organism's costs |
| Buys compute without KYC | [akash](akash.md), [vast-ai](vast-ai.md), [sporestack](sporestack.md), [bitlaunch](bitlaunch.md) | amber | APIs, reliability ([provider-kyc](provider-kyc.md)) |
| Multi-vendor hosting | [dstack](dstack.md) on TDX + SEV | amber | migration without cloning ([op-anti-twin](op-anti-twin.md)) |
| Censorship-resistant presence | [nostr](nostr.md), [tor-onion-services](tor-onion-services.md), [ens](ens.md) | green | relays and app stores |
| Private treasury | [monero](monero.md), [zcash](zcash.md), [railgun](railgun.md) | amber | exchange off-ramps |
| Trustless self-upgrade | timelocked governance in [dstack](dstack.md) KMS | amber | [op-self-authorized-succession](op-self-authorized-succession.md) |
| Memory that persists and cannot be poisoned | [agent-memory](agent-memory.md), [rehydration](rehydration.md) | amber | [memory-poisoning](memory-poisoning.md) |
| Replication | [conway-automaton](conway-automaton.md), [spore-fun](spore-fun.md); lab: [palisade-hack-and-replicate](palisade-hack-and-replicate.md) | amber | needs funded hosts |
| Self-improvement | [darwin-godel-machine](darwin-godel-machine.md), [shinka-evolve](shinka-evolve.md) | amber | eval cost |
| No legal owner | [cayman-foundation-company](cayman-foundation-company.md), [zero-member-llc](zero-member-llc.md) | amber | personhood bans ([ai-personhood-bans](ai-personhood-bans.md)) |
| Detects and survives attacks | [prompt-injection-drain](prompt-injection-drain.md), [wallet-drainers](wallet-drainers.md) defences | red | no integrated immune system |

## How it serves the organism

Turns L5 into a build list ([build-path](build-path.md)).

## How it fails

States are judgement calls; re-check monthly.

## Related

[sovereignty-levels](sovereignty-levels.md) · [open-problems](open-problems.md) · [build-path](build-path.md)

## Sources

- See linked pages — <https://github.com/autonomica-xyz/sovereign-agents-research>
