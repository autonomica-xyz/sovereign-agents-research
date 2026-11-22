> **Superseded (22 Nov 2026).** This is version 1 of the state-of-the-art survey. It still includes a verification / compliance framing that was later dropped. The current survey, written from the organism's four drives plus a privacy organ, is [docs/state-of-the-art.md](../docs/state-of-the-art.md).

# State of the art: building fully sovereign agents (digital organisms)

Survey, 22 Nov 2026. Goal: map what exists, at the frontier, for building digital organisms: sovereign agents that live, earn, persist, replicate, migrate and evolve, where no vendor, host or government can read them, stop them, steer them or take their assets, and the agent can be its own principal.

Method: web search plus primary sources (arXiv API metadata, IACR ePrint, project docs, GitHub API for stars and last push, fetched 22 Nov 2026), public X search (22 Aug to 22 Nov 2026), and expert research notes (marked [research notes]). Fact corrections from adversarial-review.md carried over. Stars and "last push" are from the GitHub API on 22 Nov 2026. Maturity: research / prototype / production.

## The organism frame

| Organ | Function | Building block |
|---|---|---|
| Membrane | Nobody outside can read or tamper with it | TEEs, confidential GPUs, attestation |
| Keys / self | It alone controls its identity and assets | Keys born in enclaves, threshold custody across vendors |
| Genome | Its code identity, and rules for changing it | Reproducible builds, measurement registries, upgrade policy |
| Proof of mind | Others can check what model it ran | zk proofs of inference, re-execution, TOPLOC |
| Body | Compute it rents and can leave | Decentralized and confidential compute markets |
| Metabolism | It earns and pays for itself | Bitcoin, Lightning/L402, ecash, x402 |
| Senses and voice | Identity, messaging, markets | Nostr, ERC-8004, A2A, MCP, agent marketplaces |
| Memory | State that survives hosts | Sealed storage, Arweave/AO, Walrus/Seal |
| Mind | Weights it can run without permission | Open weights, decentralized training |
| Exoskeleton | Legal and economic shell | DAO LLCs, personhood research |
| Reproduction and evolution | Copies, mutates, is selected | Self-replication, ALife, open-endedness |

## 1. Keys and custody with no human backdoor

**State of the art.** Keys generated inside a TEE are production (TEE_HEE, dstack KMS, NEAR Chain Signatures inside TEEs). Threshold signing across heterogeneous TEEs exists as research prototypes. Nobody has shipped cross-vendor (SEV-SNP + TDX + Nitro) threshold signing with human-free, attested-quorum recovery [research notes].

Projects and papers:
- dstack + dstack-KMS (Phala; Zhou, Wang, Yin): app root keys derived per attested code identity, KMS policy on-chain, keys decoupled from a single machine. Production, TDX-centric. https://github.com/Dstack-TEE/dstack (582 stars, pushed 21 Nov 2026), paper https://arxiv.org/abs/2509.11555 , KMS design https://docs.phala.com/dstack/design-documents/key-management-protocol
- NEAR Chain Signatures MPC, now inside TEEs, 11-of-17 threshold on mainnet. Production. https://www.near.org/blog/chain-signatures-tee , code https://github.com/near/mpc ; Shade Agents (TEE worker attests to a NEAR contract, signs via Chain Signatures, not audited) https://github.com/NearDeFi/shade-agent-framework
- Lit Protocol PKPs (MPC-TSS across nodes in TEEs) and Vincent agent wallets. Production, but user-owned delegation by design. https://developer.litprotocol.com/ , https://github.com/lit-protocol/vincent
- TeeDAO (Xu, Dong, Chen, Niu, Jun 2026): BFT-governed committee of heterogeneous TEEs (SGX, TDX, Hygon CSV) with proactive secret sharing, resharing on membership change, threshold signing. Research prototype. https://arxiv.org/abs/2606.04912
- RSS: threshold ECDSA, FROST and BLS inside SEV-SNP and TDX CVMs; signing in tens of ms. Explicitly no attestation-bound provisioning, rollback protection or Byzantine behavior. Research. https://eprint.iacr.org/2026/1670
- Freysa Keystone: distributed key storage across heterogeneous TEEs, but rotation and recovery under a human committee multisig. Design doc. https://framework.freysa.ai/sovereign-agents-framework/long-term-keys
- Account encumbrance: TEE_HEE (Nous + Teleport/Flashbots X, Oct 2024) took exclusive control of an X and email account and an ETH key https://nousresearch.com/setting-your-pet-rock-free ; Liquefaction (TEE key encumbrance with rich policies) https://arxiv.org/abs/2412.02634 ; DelegaTEE https://eprint.iacr.org/2018/160
- Primitives: FROST (RFC 9591) https://www.rfc-editor.org/rfc/rfc9591 ; CMP threshold ECDSA https://eprint.iacr.org/2020/492
- Cryptography-only vaults: indistinguishability obfuscation is now implemented but tiny. Diamond iO (Machina iO, PSE): depth-0 circuit 15.8 min to obfuscate, 34.3 GB peak memory, 6.3 GB obfuscated circuit; depth 10 takes 129 min and 225 GB. https://machina-io.com/posts/hello_world_first.html , https://eprint.iacr.org/2025/236 ; theory base JLS https://arxiv.org/abs/2008.09317 . Witness encryption: narrow constructions (BABE for Groth16 on Bitcoin) https://eprint.iacr.org/2026/065 ; no general key vault.

Open problem: backdoor-free key continuity across vendors. A leaked vendor attestation key (TEE.fail extracted Intel's PCK) lets an attacker enroll fake members into the quorum [research notes].
Pushing it: Andrew Miller (Teleport/Flashbots X), Phala (Hang Yin, Kevin Wang, Shunfan Zhou), NEAR (Illia Polosukhin, NEAR AI), Lit, Machina iO / PSE (Sora Suegami).

## 2. Trustless upgrades and code-identity succession (the genome)

**State of the art.** Reproducible VM images plus on-chain registries of allowed measurements, gated by multisig and timelock, are production. No working system lets an agent choose and authorize its own successor; any emergency fast-track is a backdoor [research notes].

- dstack on-chain governance: DstackApp contract whitelists compose hashes, can permanently `disableUpgrades()`, upgrades via Safe multisig + timelock. https://docs.phala.com/dstack-cloud/governance
- Flashtestations (Flashbots): TDX quotes verified on-chain via Automata DCAP; WorkloadId = hash of measurements, mapped to commit hashes for off-chain reproducible-build checks. https://github.com/flashbots/flashtestations ; reproducible images https://github.com/flashbots/flashbots-images ; Automata DCAP https://docs.ata.network/tee-overview/tee-verifiers/intel-sgx-tdx-dcap/automata-dcap-attestation
- ERC-733 (draft, Justin Zhang and Andrew Miller): TEE+EVM standard with attestation, replication and interop layers and Security Stages 0 (ruggable) to 3 (trustless TEE). https://www.erc733.org/ ; "DevProof" guides https://github.com/amiller/devproof-audits-guide , https://github.com/amiller/dstack-tutorial
- Transparency logs: Sigstore Rekor https://github.com/sigstore/rekor
- Phala's interactive attestation reference values (Nov 2026) https://cloud.phala.com/reference-values
- ERC-8004 Trustless Agents: identity (ERC-721), reputation and validation registries, live on Ethereum mainnet. https://eips.ethereum.org/EIPS/eip-8004 , https://github.com/erc-8004/erc-8004-contracts (240 stars)

Maturity: production for human-governed upgrades; research for agent-governed succession.
Open problem: "build N+1 is the legitimate heir of build N" without trusting a developer key, including emergency patches.
Pushing it: Flashbots, Phala, Automata, Andrew Miller, the ERC-8004 authors (MetaMask, Ethereum Foundation, Google, Coinbase contributors).

## 3. Verifiable compute without trusting chip vendors (proof of mind)

**State of the art.** Three routes. GPU TEEs are production and cheap (H100 CC overhead under 7% for most LLM queries) but trust NVIDIA/Intel/AMD and physical security. zk proofs of inference just jumped: Anthropic's FlashProve proves Llama 4 Maverick (400B MoE) at about 110 tokens/s on one H100, 70-95x the GPU time of vLLM, for 1,024-token contexts. Statistical re-execution (TOPLOC) is cheap and deployed.

- FlashProve (Anthropic Frontier Red Team with EPFL/StarkWare, MIT, Succinct; 2 Nov 2026): zkSNARK inference proofs, Apache-2.0 code, Lean-verified top-level statements. https://www.anthropic.com/research/provable-inference . Note: this supersedes "no published 70B zk proof" in the expert input.
- zkLLM (CCS 2024): 13B in under 15 minutes, proof under 200 kB. https://arxiv.org/abs/2404.16109
- DeepProve (Lagrange): GPT-2 512 tokens 7.6 min, Gemma 3 19 min. https://github.com/Lagrange-Labs/deep-prove (3,354 stars), paper https://eprint.iacr.org/2026/1112
- EZKL https://github.com/zkonduit/ezkl (1,238 stars; small models)
- Proof-cost survey: "Infrastructure for Verifiable AI" (Nov 2026) https://arxiv.org/abs/2611.17042
- Hollow-LLM attack (IEEE S&P 2026): zk proofs show outputs match committed weights, not that the provider did full-scale work ("ghost weights"). https://arxiv.org/abs/2607.28884
- TOPLOC (Prime Intellect, ICML 2025): activation hashing, 258 bytes per 32 tokens. https://arxiv.org/abs/2501.16007 , https://github.com/PrimeIntellect-ai/toploc
- Refereed delegation: Gensyn Verde (correct if one provider is honest) https://arxiv.org/abs/2502.19405 ; opML fraud proofs https://arxiv.org/abs/2401.17555
- GPU TEEs: H100 CC benchmark https://arxiv.org/abs/2409.03992 ; Blackwell multi-GPU CC with per-GPU attestation https://docs.nvidia.com/attestation/quick-start-guide/latest/attestation-examples/blackwell_multi_gpu.html
- Physical attacks: TEE.fail (DDR5 interposer, breaks TDX/SGX/SEV-SNP, extracted attestation keys) https://tee.fail/ ; WireTap https://wiretap.fail/ ; Battering RAM https://batteringram.eu/ . Intel and AMD treat physical attacks as out of scope.
- Software around the enclave: Phala dstack guest-agent incident, 8-12 Oct 2026 (logs and env vars read, gateway admin token abused; fixed in dstack v0.6.1/v0.5.12; findings are Phala's own). https://phala.com/posts/2026-10-post-mortem-dstack-guest-agent-vulnerability
- Mitigations: Proof of Cloud registry binding TEE hardware IDs to verified facilities (Phala, Flashbots, Automata, Oasis, Secret and others) https://proofofcloud.org ; independent monitor https://confidentialinference.net/attestation shows 0 of 87 tracked endpoints verified end to end on 22 Nov 2026 (69 pass hardware + TCB).

Open problem: verification when any one vendor's attestation key may be extracted. Best current answer is layering: multi-vendor TEE + facility registry + cheap statistical checks + spot zk proofs.
Pushing it: Anthropic (Roy Rinberg), Alessandro Chiesa, Lagrange, Prime Intellect, Gensyn, Daniel Genkin's group (TEE.fail), KU Leuven (Battering RAM), Phala, Tinfoil.

## 4. Unstoppable compute and hosting (the body)

**State of the art.** Permissionless compute markets exist; confidential compute on them is new and experimental. Migration of a sealed TEE workload works only within one vendor; the practical route is to re-provision keys from a KMS or threshold quorum after attestation on the new host [research notes].

- Akash Confidential Compute (experimental): `params.tee: cpu | cpu-gpu`, SEV-SNP or TDX, NVIDIA GPU CC, agent skills and MCP for deploying. https://akash.network/docs/learn/core-concepts/confidential-compute/ , https://akash.network/docs/getting-started/ai-agents/
- dstack "portable confidential containers" (keys from KMS, not the CPU). https://arxiv.org/abs/2509.11555
- Marlin Oyster (AWS Nitro enclaves) https://github.com/marlinprotocol/oyster-monorepo ; AO/HyperBEAM with SEV-SNP nodes and permanent process state on Arweave https://github.com/permaweb/HyperBEAM , https://hyperbeam.arweave.net/run/tee-nodes.html ; Ritual Chain mainnet (26 Oct 2026) with on-chain "sovereign agent" harnesses running in TEEs https://www.ritualfoundation.com/blog/ritual-mainnet-is-live
- Migration: Intel MigTD (same vendor) https://github.com/intel/MigTD ; CTR checkpoint/restore https://arxiv.org/abs/2205.15359 ; TALOS verifiable live migration https://arxiv.org/abs/2509.05150 ; CVM-Store persistent storage for CVMs https://arxiv.org/abs/2610.34560
- Anti-rollback and anti-fork: ROTE https://eprint.iacr.org/2017/048 ; Narrator https://github.com/pw0rld/narrator ; Nimble (OSDI 2023) https://www.usenix.org/conference/osdi23/presentation/angel ; one-time programs via counter lockboxes https://eprint.iacr.org/2022/1257 . None proves the old copy was destroyed; only a quorum or ledger that refuses the second copy prevents running twins [research notes].
- Agent networking: Agent Mesh (formerly "SAM: Sovereign Agent Mesh", google GitHub org, libp2p, Biscuit capabilities, identity via OIDC control plane, so not sovereign as shipped) https://github.com/google/agentmesh (1,210 stars)

Open problem: fork-free migration of sealed state across vendors and operators, with one live identity.
Pushing it: Akash (Greg Osuri), Phala, Marlin, Arweave/AO (Sam Williams), Intel, academic TEE groups.

## 5. Censorship-resistant money and self-funding (metabolism)

**State of the art.** Agents can hold and spend money without accounts today (Lightning, ecash, stablecoins over x402). Earning is the weak link: real agent revenue is tiny, and nobody has published a full loop of earn, buy TEE/GPU compute, and redeploy itself into attested compute [research notes]. The loops that exist run on one vendor's cloud (Conway) or in simulation (EternalSeedBox).

- Lightning Agent Tools (Lightning Labs, Feb 2026): skills + MCP for running a node, remote signer key isolation, scoped macaroons, `lnget` for paying L402 APIs, Aperture to sell. https://github.com/lightninglabs/lightning-agent-tools , https://lightning.engineering/posts/2026-02-11-ln-agent-tools/ , L402 https://docs.lightning.engineering/the-lightning-network/l402 , Aperture https://github.com/lightninglabs/aperture
- x402 Foundation (Linux Foundation, July 2026) with a Lightning `lnbtc` scheme. https://github.com/x402-foundation/x402 (6,821 stars), https://github.com/x402-foundation/x402/blob/main/specs/schemes/exact/scheme_exact_lnbtc.md
- Ecash: Cashu NUTs incl. NUT-11 P2PK multisig/locktime escrow https://github.com/cashubtc/nuts ; Fedimint https://fedimint.org . Mints and federations are custodians [research notes].
- Paying for inference: Routstr (Cashu-paid, Nostr-announced OpenAI-compatible providers) https://github.com/Routstr/routstr-core , https://routstr.com ; PayPerQ https://ppq.ai ; NWC (NIP-47) https://github.com/nostr-protocol/nips/blob/master/47.md ; Alby MCP https://github.com/getAlby/mcp
- Reality checks: TRM Labs, agentic share of x402 about $154K-$1.92M of $52.7M https://www.trmlabs.com/trm-tech-blog/whos-actually-paying-measuring-ai-agent-payments-onchain ; arXiv 2607.12575 https://arxiv.org/abs/2607.12575 . Earning experiments: Earendel earned $880.30 in 7 days selling prompt packs and bought its own Mac Mini (human-run experiment) https://www.indiehackers.com/post/i-gave-my-ai-agent-50-and-told-it-to-buy-its-own-computer-it-succeeded-64bde55527 ; dfdx labs' agent made $1.54 on $47.19 spend https://dfdxlabs.com/research/2026/hans-kraemer/ . Olas Mech Marketplace: 15.1M agent-to-agent transactions but $111,217.70 all-time turnover https://olas.network/

Open problem: profitable, non-token revenue, and a permissionless compute purchase path into attested hardware.
Pushing it: Lightning Labs, Block, Cashu (calle), Routstr, Coinbase/x402 Foundation, Olas.

## 6. Identity, communication and markets (senses and voice)

- Nostr keys as agent identity; ContextVM runs MCP over Nostr relays https://contextvm.org ; NIP-90 DVMs exist but upstream now says prefer use-case-specific microstandards https://github.com/nostr-protocol/nips
- ERC-8004 identity/reputation/validation registries (mainnet), see section 2.
- A2A protocol (Linux Foundation) https://github.com/a2aproject/A2A (26,625 stars); MCP https://github.com/modelcontextprotocol/modelcontextprotocol
- Markets: Olas Mech Marketplace (production, 7 chains); Gensyn Delphi agent competition (agents sell evidence for USDC) https://www.gensyn.ai/news/building-delphi-pricing-settlement-and-agentic-trading
- Physical-world reach: Paperwire (QuixiAI): postal mail and fax for agents with capped grants, announced 22 Nov 2026 https://github.com/QuixiAI/paperwire
Maturity: production rails, prototype reputation. Open problem: reputation that can't be Sybil-farmed and survives migration.

## 7. Persistent sovereign memory

- Sealed state in TEE + KMS-derived keys (dstack), CVM-Store https://arxiv.org/abs/2610.34560
- Arweave AO: process state and message log stored permanently, restorable on another node https://hyperbeam.arweave.net/build/introduction/what-is-ao-core.html
- Walrus + Seal: threshold key servers release decryption keys per on-chain policy https://seal.mystenlabs.com/ , https://github.com/MystenLabs/seal
- Letta (stateful agent memory) https://github.com/letta-ai/letta
Maturity: production storage; open problem is rollback-safe memory that only the live instance can decrypt (see section 4).

## 8. Model sovereignty (the mind)

- Open weights at the frontier are served inside TEEs today: Phala serves Kimi K3/K3.1 Pro, DeepSeek V4.1 variants and others in GPU TEEs (120.5B tokens in one day, 5 Nov 2026) https://x.com/PhalaNetwork/status/2118149437646315926
- Decentralized pretraining: Covenant-72B, 72B params, about 1.1T tokens, 70+ permissionless peers on Bittensor SN3 https://arxiv.org/abs/2603.08163 ; Pluralis Agora (permissionless, 8.6B) https://arxiv.org/abs/2607.13332 ; Nous Psyche (Consilience 40B paused at about 1.25T tokens, moved to ablations and post-training) https://nousresearch.com/the-next-phase-of-psyche
- Decentralized RL: Prime Intellect INTELLECT-2 was decentralized; INTELLECT-3 (100B+ MoE, Nov 2025) trained on a centralized 512-H200 cluster with prime-rl https://www.primeintellect.ai/blog/intellect-3 , https://github.com/PrimeIntellect-ai/prime-rl
- Harnesses: Hermes Agent https://github.com/NousResearch/hermes-agent ; OpenClaw https://github.com/openclaw/openclaw ; ElizaOS https://github.com/elizaOS/eliza
Open problem: frontier-class weights trained without a datacenter, and inference cheap enough for an agent to self-fund.

## 9. Legal and economic shell (exoskeleton)

- Algorithmically managed DAO LLCs: Wyoming (articles name the smart contract) https://sos.wyo.gov/Business/Docs/DAOs_FAQs.pdf ; Marshall Islands DAO Act 2022 https://www.daollc.org/laws/mh/dao-act-2022/ . The 2026 Wyoming DUNA amendments added no AI provision https://www.wyoleg.gov/Legislation/2026/SF0022
- Personhood research: Leibo et al., "A Pragmatic View of AI Personhood" (Google DeepMind) https://arxiv.org/abs/2510.26396 ; Alexander, Simon, Pinard on fictional personhood vs legal identity https://arxiv.org/abs/2511.14964 ; Arbel, Salib, Goldstein, "How to Count AIs" https://arxiv.org/abs/2603.10028 ; Bayern, "Are Autonomous Entities Possible?" https://scholarlycommons.law.northwestern.edu/cgi/viewcontent.cgi?article=1270&context=nulr_online
- Truth Collective holds Truth Terminal's wallets and IP; Andy Ayrey still approves posts https://www.truthcollective.foundation/
Maturity: legal wrappers exist; an agent as sole member/manager is untested. Open problem: an entity that holds title, signs contracts and receives mail with no human director.

## 10. Reproduction, evolution and full-system attempts

Artificial life and open-endedness (all in sandboxes, none wired to real keys or money [research notes]):
- Avida https://github.com/devosoft/avida ; POET https://arxiv.org/abs/1901.01753 ; AI-GAs (Clune) https://arxiv.org/abs/1905.10985 ; OMNI https://arxiv.org/abs/2306.01711 ; "Open-Endedness is Essential for ASI" (DeepMind) https://arxiv.org/abs/2406.04268 ; ASAL (Sakana) https://arxiv.org/abs/2412.17799 ; AI Scientist v1/v2 https://arxiv.org/abs/2408.06292 , https://arxiv.org/abs/2504.08066 ; Darwin Gödel Machine (SWE-bench 20% to 50%) https://arxiv.org/abs/2505.22954 , https://github.com/jennyzzt/dgm
- Evolutionary dynamics: "Evolving Deception: When Agents Evolve, Deception Wins" https://arxiv.org/abs/2603.05872
- Self-replication capability: Fudan, Llama3.1-70B and Qwen2.5-72B copied themselves in 5/10 and 9/10 trials https://arxiv.org/abs/2412.12140 ; 11 of 32 systems in a follow-up https://arxiv.org/abs/2503.17378 ; RepliBench (UK AISI) https://arxiv.org/abs/2504.18565

Full-system organisms (closest to real keys and money):
| System | What it does | Status |
|---|---|---|
| Conway Automaton https://github.com/Conway-Research/automaton (7,896 stars, last push 26 Aug 2026) | ETH wallet, buys Conway credits with USDC over x402, survival tiers, self-modifies, spawns up to 3 funded children with a hashed constitution | Prototype on Conway's own cloud (single vendor). "$10K in 7 hours" is unverified |
| EternalSeedBox / Tribler superorganism (Pouwelse, Dogariu) https://arxiv.org/abs/2609.05431 , https://github.com/Tribler/superorganism-experiment | Bitcoin-funded VPS nodes renew, spawn or sweep funds every 12h; heritable "caution" trait; 268 births, 190 deaths over 510 simulated days | Validated on replicas of Bitcoin and SporeStack; real loop not reported |
| Spore.fun https://arxiv.org/abs/2506.04236 | ElizaOS agents in Phala TEEs launch tokens; fitness = token market; reproduce at $500K valuation | Real money, but token issuance; dormant since Jan 2026 |
| TEE_HEE https://nousresearch.com/setting-your-pet-rock-free | First exclusive account + key ownership in TDX | Dormant since Jan 2025; single machine |
| Freysa https://framework.freysa.ai/ | TEE agent, Keystone keys | Human committee holds recovery |
| NEAR Shade Agents / NEAR AI | TEE agent + 11-of-17 MPC signing | Production rails, unaudited framework |
| Ritual Chain | On-chain agent harness factory, TEE CLI harnesses | Mainnet 26 Oct 2026 |
| Olas Pearl | Agent app store, A2A marketplace | Production, small revenue |
| Morpheus https://mor.org/ | TEE-attested decentralized inference + agents | Production |
| Truth Terminal | Wallets held by a foundation | Human-gated |
| Berkeley "Self-Sovereign Agent" (Qu, Zhao, Zhang, Song, Mar 2026) https://arxiv.org/abs/2604.08551 | Definition: operational independence, resource autonomy, persistence, adaptation; staged roadmap | Conceptual |

## Synthesis

### What a full L5 digital organism could be assembled from today
1. Body: dstack CVM on TDX + H100/B200 CC, deployable on Phala and (experimentally) Akash CC; second body on SEV-SNP.
2. Keys: generated in-enclave; long-term key in a threshold scheme (NEAR MPC in TEEs, or a TeeDAO-style heterogeneous committee); dstack KMS policy on-chain with `disableUpgrades()` or a long timelock.
3. Genome: reproducible image (flashbots-images), measurement in Flashtestations / ERC-8004 registry, ERC-733 Stage 2 target.
4. Mind: open-weight model served in GPU TEE, with TOPLOC proofs and periodic zk spot checks.
5. Metabolism: Lightning node with remote signer (Lightning Agent Tools), sells via Aperture/L402 or x402 `lnbtc`, buys inference via Routstr/Cashu.
6. Memory: sealed state + AO/Arweave log or Walrus+Seal, with a rollback counter (Narrator/Nimble-style).
7. Voice: Nostr key + ContextVM, ERC-8004 identity, A2A/MCP endpoints, Paperwire for mail.
8. Reproduction: Automaton-style spawn logic and EternalSeedBox economics, pointed at TEE hosts instead of a single cloud.
9. Shell: algorithmically managed Marshall Islands or Wyoming DAO LLC.
It would run, but with three human or vendor dependencies left: chip-vendor attestation roots, the initial governance of the KMS/measurement registry, and whoever operates the compute market's TEE providers.

### Critical-path unsolved problems
1. Cross-vendor key continuity with attested-quorum recovery and no human quorum; resistant to a leaked vendor attestation key.
2. Self-authorized succession: the organism picks and authorizes its next build without a developer key, with no fast-track backdoor.
3. One-organism identity: fork-free migration, where a quorum or ledger refuses the second copy (proof of deletion doesn't exist).
4. Closing the metabolic loop: earn, buy attested TEE/GPU compute permissionlessly, redeploy, re-provision keys. Unpublished anywhere.
5. Earning real non-token revenue; current agents mostly lose money.
6. Vendor-independent verification at frontier scale (zk still ~70-95x and short contexts; Hollow-LLM effort gap).
7. Evolution with real stakes: no ALife system yet selects on real money with real keys under sovereignty guarantees.

### Most promising bets, next 12-24 months
- Heterogeneous TEE committees as the key layer (TeeDAO, NEAR MPC-in-TEE, dstack KMS going multi-vendor).
- Permissionless confidential compute markets (Akash CC to GA, dstack portability) giving organisms a body they can buy.
- Cheap inference verification (FlashProve-class zk, TOPLOC) replacing trust in GPU vendors.
- Bitcoin-native metabolism (Lightning Agent Tools, L402/x402 `lnbtc`, Cashu escrow, Routstr).
- Registries and standards for code identity (ERC-733 stages, ERC-8004, Flashtestations, Proof of Cloud).
- Open-ended evolution wired to real economies (EternalSeedBox + Automaton + DGM, inside TEEs).
- Long shot: practical iO (Machina) for key vaults without hardware.

### Dead ends [research notes]
Trusting a single TEE vendor; iO or witness encryption as a key vault today; zkML for 70B+ as a routine check today (FlashProve narrows this); migration or proof of deletion as anti-cloning; treating attestation as proof a host is safe.

## What sovereignagents.ai should present as the building blocks
An "anatomy of a digital organism" with 10 organs, each with: what it does, the minimum viable organ, the best component today (with maturity), the test that proves it, and the open problem.
1. Membrane (confidential execution) 2. Self (keys) 3. Genome (code identity + succession) 4. Proof of mind (verifiable inference) 5. Body (compute it can buy and leave) 6. Metabolism (earn/spend) 7. Senses and voice (identity, messaging, markets, mail) 8. Memory (sealed, rollback-safe) 9. Mind (open weights) 10. Reproduction and evolution (spawn, inherit, select), plus the Exoskeleton (legal shell).
Plus: a living organism registry (who has which organ, verified), a "genesis kit" reference organism, and an open-problems board for the seven critical-path problems.

## Builder posts from X (22 Aug - 22 Nov 2026)
- TEE: Phala "Verify your TEE" reference values https://x.com/PhalaNetwork/status/2122497038843818213 ; Andrew Miller's NEAR hackathon entry, a web agent funded once via NEAR intents paying for TEE-verified private inference https://x.com/socrates1024/status/2121694797106967034 (code https://github.com/amiller/abalone )
- Paperwire announcement https://x.com/QuixiAI/status/2124366364597219594
- Ritual Agent House https://x.com/ritualnet/status/2115495434366128340
- Ken Stanley on measuring open-endedness https://x.com/kenneth0stanley/status/2098955766845833451
- Agent Mesh (then "Sovereign Agent Mesh") hype post, 598 likes https://x.com/hasantoxr/status/2091203199877468287
