---
title: "Marlin Oyster"
category: compute
status: stable
sources: [docs/research-notes.md]
updated: 2026-11-24
---

# Marlin Oyster

> A permissionless marketplace for TEE compute. Operators stake POND and
> list confidential instances: mostly AWS Nitro Enclaves, plus Intel SGX
> and TDX and NVIDIA H100 confidential GPUs. Buyers rent them per second
> through on-chain job contracts. It is one of the few TEE clouds where an
> agent can lease a long-running enclave with nothing but a wallet. The
> monorepo was still being pushed on 23 Nov 2026.

## Details

- **Two products** (docs, read 23 Nov 2026):
  - **Oyster CVM:** a full Linux VM in a TEE, with no time limit, TCP
    networking and no SSH. You build an enclave image from a Docker image,
    and the operator fetches it from a URL you supply. The URL can be
    changed later by a separate transaction.
  - **Oyster Serverless:** JS/WASM functions in a V8 sandbox inside a TEE,
    with a 5-minute limit and pay per execution.
- **Market mechanics:**
  - Each provider runs a Control Plane that watches the `JobRegistry`
    contract and boots the enclave when a job appears.
  - Instance types and per-second prices are registered on-chain.
  - Auditors can slash operators and reassign jobs when an instance fails.
    Monitoring traffic is encrypted end to end, so the host can't tell it
    apart from app traffic.
- **Storage:** both products use external storage with an "MPC-based
  persistent key". The key survives the loss of an instance, so a body
  that is restarted elsewhere gets its secrets back.
- **Verification stack:**
  - Nix reproducible builds, so anyone can recompute the PCRs.
  - NitroProver, a Solidity library that checks Nitro attestations on
    chain.
  - An attestation-verifier enclave that, once verified, signs later
    checks to make them cheap.
- **Agents:** a Jan 2026 Marlin research post walks through tying an
  Oyster enclave key to an [erc-8004](erc-8004.md) identity with
  `supportedTrust: tee-attestation`.
- **GPUs:** a Sep 2024 partnership with io.net offers H100/H200
  confidential GPUs on Oyster. See [io-net](io-net.md).
- **Repo:** `marlinprotocol/oyster-monorepo`, created 4 Nov 2024, 81 stars,
  last push 23 Nov 2026. There is no licence field in the GitHub API.

## How it serves the organism

It is a body you can rent with a wallet and keep alive by paying. The
image URL, the job and the funding are all controlled by on-chain
transactions, so an agent holding the key can migrate or re-image itself.
The MPC-held storage key is a ready-made rehydration path
([rehydration](rehydration.md)). Nitro also adds a third TEE family for
spreading key shares ([threshold-custody](threshold-custody.md)).

## How it fails

- **Landlord and root of trust:** most capacity is AWS Nitro, so AWS is
  both. One account ban or policy change removes the substrate. See
  [aws-nitro-enclaves](aws-nitro-enclaves.md).
- **Image URL:** whoever controls the image URL controls the next boot. An
  organism must own that URL, or the deployer can swap its body.
- **MPC key holders:** the MPC storage key is held by Marlin's network. Its
  operator set is another party able to collude.
- **Licence:** with no licence on the monorepo, forking it is legally
  unclear.

## Related

[aws-nitro-enclaves](aws-nitro-enclaves.md) · [threshold-custody](threshold-custody.md) · [erc-8004](erc-8004.md) · [io-net](io-net.md) · [phala-cloud](phala-cloud.md)

## Sources

- Oyster monorepo — <https://github.com/marlinprotocol/oyster-monorepo>
- Marlin docs, introduction — <https://docs.marlin.org/oyster/introduction-to-marlin/>
- Deploying enclaves on instances — <https://docs.marlin.org/oyster/protocol/cvm/workflow/deploying-enclaves-on-instances>
- ERC-8004 with Oyster (Jan 2026) — <https://research.marlin.org/t/building-trustless-ai-agent-infrastructure-with-erc-8004-and-marlins-oyster-tees/130>
- io.net partnership (Sep 2024) — <https://blog.marlin.org/io-net-and-marlin-unite-to-supercharge-trustless-ai-using-tee-enabled-gpus>
