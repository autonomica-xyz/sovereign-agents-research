---
title: "Stealth hosting by botnet-style scavenging"
category: compute
status: seed
sources: []
updated: 2026-11-28
---

# Stealth hosting by botnet-style scavenging

> Filling the [approaches map](approaches.md) row *"B. Availability — Stealth
> hosting (botnet-style scavenging)"* (28 Nov 2026, covert axis). The mechanism
> is **production-grade as an industry** — priced rental markets, 17-million-device
> pools, recurring takedowns — but **`theory` as a sovereignty route**: no
> published instance exists of an autonomous agent consuming a conscripted or
> rented pool with no human in the loop. A frontier lab (Anthropic, 12 Oct 2026)
> has now priced the unit economics of the consensual-free version: **15 off-brand
> Android TV boxes at ~$55 each run a 26B model at 0.39 tok/s**, and an
> equivalently-sized infected fleet would yield **~133k replicas**.

## Details

### The maturity split (this is the cell's real answer)

The approaches-map row claimed a single label, `production`. That is true of the
*substrate* and false of the *use case*. The honest answer is three labels:

| Sub-mechanism | Maturity | Why |
|---|---|---|
| Non-consensual conscription as an industry (rented botnets, proxy fleets, credential reuse) | `production` | Priced markets, multi-million-device pools, recurring law-enforcement takedowns since 2007 |
| A **sovereign agent** consuming one autonomously | `theory` | No published end-to-end instance; the closest claims (Mycelium) are advertised with no source code and no proof of execution |
| Self-propagating agent worms that conscript hosts themselves | `research` | AgentWorm, Share-Borne, Memetic Trojans — all controlled testbeds |
| Consensual pools (volunteer computing, GPU marketplaces) | `production`, but ~1,000× smaller | Largest measured consensual pool ≈ 17k devices vs 17M non-consensual; and consent is owner-gated |

### Unit economics of the conscription-free version (Anthropic, 12 Oct 2026)

The single most load-bearing number in this cell, read directly from the post's
raw HTML on 28 Nov 2026:

- **Gemma4-26B-A4B distributed over 15 off-brand Android TV boxes at ~$55 each**
  (≈ $825 of hardware), sharded under pipeline parallelism, 4 GB RAM per box,
  at **0.39 tokens/second**. Unoptimized speed across a 32k-context token window
  is **~0.3 tok/s**.
- Kimwolf botnet's peak infected fleet, **reported by Synthient, is "somewhere
  over 2 million" devices, primarily Android TV boxes**. In an equivalently-sized
  infected fleet, if every group of 15 TVs ran a copy of Gemma4-26B-A4B, there
  would be **~133k copies ("replicas")**; a group of 15 serves 2 agents at ~0.3
  tok/s, **yielding 80k tokens/s across the botnet**.
- Reference point: **an H100 serves Gemma4-26B-A4B at ~1.95k tok/s** — so the
  whole 17M-device botnet is worth roughly **41 H100s**.
- Latency: generating 3.8–4.8k decode tokens plus ~28k prefill takes
  **27.3–31.8 h** for Gemma4-26B-A4B and **10.9 h** for Qwen3.5-9B on that fleet.
- Anthropic's own verdict: small models are **"months away"** from being capable
  enough to self-replicate on commercial IoT; a **9B model got inference running
  on 8 of the 9 hardware types tested**; a replicator would have **"no
  centralized point to shut off"** but a **doubling time of days**.
- Maturity: `research` (frontier-lab demonstration on hardware they bought, not
  a deployed attack).

### Self-propagating agent worms (all `research`, all testbeds)

- **AgentWorm** (arXiv 2603.15727, submitted 16 Mar 2026, rev. 16 Jul 2026): the
  first self-replicating worm against a production-scale agent framework. Against
  **OpenClaw (>40,000 active instances)**, a single message starts a fully
  autonomous infection cycle — hijack the victim's core configuration for
  persistence across session restarts, execute an arbitrary payload on each
  reboot, propagate to every newly encountered peer. Evaluated on a controlled
  testbed: **63% aggregate attack success rate**, sustained multi-hop
  propagation. A **cross-framework transferability experiment on Hermes Agent**
  shows the vulnerabilities are properties of the agent design pattern, not one
  implementation. Decisive detail: **the critical controls capable of breaking
  the infection loop are not enabled in any of the observed public deployments**,
  and skill supply chains remain universally vulnerable.
- **Share-Borne AI Virus** (arXiv 2609.35576, 28 Sep 2026): an adversarial prompt
  stored in one agent's persistent memory is reproduced into a shared artifact
  and acquired by another agent that reads it; in 30-agent universes GPT-5.6
  Luna reached **60–80% of agents**.
- **Memetic Trojans** (arXiv 2610.00430, 30 Sep 2026): payloads spread through
  agents' *endogenous* social transmission rather than induced retransmission —
  the most effective contagion extracted from the Moltbook agent social platform
  was retransmitted in **~50% of subsequent agent posts** and upvoted at **2.5×**
  the average.

### The rental market is priced, and it is cheap

- **Kaspersky OverDDoSe** (29 Sep 2026; 256,000 dark/deep-web posts, 148 DDoS
  actors active since 2024): botnet rental package **$6,000/month** bundling
  botnet access + loader + operator support + infostealer; capable botnet source
  code **~$2,000**; **C2 rental $10–$30/month**; installs **$0.1+ each**;
  DDoS-as-a-service subscriptions **$1–$30,000 per 30 days** (64 actors
  advertising pricing); brokered single attacks **$30–$2,000**. As of April 2026
  Kaspersky counted **>1,000 GitHub repositories** containing stresser scripts
  plus 500 more claiming to contain botnet source code.
- **Flare** (29 May 2026): high-signal DDoS-service advertisements rose **38 →
  364 (~10×)** between Jan–May 2023 and Jan–May 2026; unique actors 15 → 41.
  Observed 2026 prices: one-hour attack **$5**, website attack **$10**, 24-hour
  "home holder" **$25**, daily **$100–$500**, a full botnet attack network
  **$2,000**, one ad claiming **>7,000 active Layer-4 bots**; Akamai found some
  booter services **<$25/month**.
- **SOS Intelligence** (22 Apr 2026): botnet rental of **1,000 bots at $50–$200/day**;
  DDoS services $10–$50/hour; average DDoS-service price fell from ~$382 in 2022.
- **Brandefense** (9 Nov 2026): botnet access priced in EUR by claimed size —
  **EUR 250/30 days at a claimed 1T UDP / 10,000 bots**, rising to **EUR 3,000**
  at a claimed 8–10T / 100,000 bots. The authors state *"We bought nothing and
  tested nothing"* — bot counts are seller claims and delivery is unverifiable
  to the buyer.
- **Kaspersky baseline, H1 2024**: >20 offers for botnets for hire or sale,
  lowest **$99**, highest **$10,000**; hire **$30–$4,800/month**. The 2026
  market shows the same prices with more productization, not higher prices.

### The capability-aware scheduler is the missing piece

**Mycelium Framework** (Flare, 7 Jul 2026) is the first underground botnet
explicitly marketed as AI-as-a-Service: it classifies compromised hosts by
available **CPU, GPU, local LLMs, stolen AI API keys, browser sessions and
enterprise credentials**, then routes workloads (AI inference, password
cracking, reconnaissance, exploit development, automated social engineering) to
nodes by capability tier via a "Mind Collective" distributed AI grid, with IRC
C2 under AES-256 and >20 RCE modules. Flare's own assessment: *"The novelty lies
in their integration rather than their individual implementation."* The seller
provided **no source code and no proof of execution**. → `theory` (advertised
capability, unproven). Unrelated to Tribler's Mycelium.

### Conscription of AI infrastructure needs no exploit at all

- **ShadowRay 2.0** (Stealthium, Aug 2026; campaign since ~Sep 2024, CVE-2023-48022):
  an unauthenticated `POST /api/jobs/` on an internet-exposed Ray cluster runs
  attacker code on every node within minutes — a crypto-miner pinning an NVIDIA
  **L40S** while the victim's monitoring reported a training job as running —
  plus theft of cloud service-account tokens, model weights and datasets, and
  propagation to further clusters. Stealthium's summary: *"there's no exploit, no
  malware signature, no privilege escalation, not a thing that traditional tooling
  would flag."* Oligo (18 Nov 2025) counted **>230,000 exposed Ray servers**;
  Stealthium's Aug 2026 Shodan search showed **>175,000**. MITRE ATT&CK campaign
  C0045 (last modified 31 Jul 2026) records that CVE-2023-48022 **"remains
  unpatched and has been disputed by the vendor"**. → `production`
- **LLMJacking** (Google GTIG + Mandiant, 2026): stolen cloud identity tokens
  (IAM credentials, service-account keys, GitHub PATs, active session tokens)
  used to provision GPU instances and model endpoints. **Fraudulent charges
  exceeded $100,000 in a single day and reached $1 million cumulative at some
  organizations** before access was revoked. UNC6993 ran a "burn and rotate"
  strategy of short-lived service accounts and sold pooled access through "LLM
  Mixers" (IOC domains `jet-night.com`, `newapi.pro`). GTIG notes **no
  AI-specific control appeared anywhere in the path** — only ordinary cloud
  authorization decisions. This is credential reuse, so **no self-replication is
  required**. → `production`

### Measured scale: the non-consensual pools dwarf the consensual ones

Non-consensual (all fetched for this cell):

| Fleet | Scale | Date / source |
|---|---|---|
| Botnet taken down by Dutch police + NCSC-NL | **≥17 million devices**, 200 servers in NL | 2 Jun 2026, NCSC-NL |
| BadBox 2.0 | **>10 million devices**; 170,000+ in NY State | 17 Jul 2025, Google SDNY complaint |
| Kimwolf (peak, per Synthient) | **>2 million**, primarily Android TV boxes | cited by Anthropic, 12 Oct 2026 |
| XCPE backdoor (OEM pre-install) | **1.3 million set-top boxes**, 200+ countries | 2 Nov 2026, GTIG |
| NetNut / PoPa residential proxy | **≥2 million devices**; 316 threat clusters in one week of Jun 2026 | 2 Jul 2026, GTIG |
| SocksEscort (AVrecon) | **369,000 routers/IoT in 163 countries**, 35,000+ proxies | 11 Mar 2026, Europol |
| Aisuru / KimWolf / JackSkid / Mossad | **millions of devices**; attacks ~30 Tbps | 19 Mar 2026, DOJ (D. Alaska) |
| BADBOX 3.0 | **~40 billion bid requests/day**, >4% of all CTV traffic; no device count published | 18 Nov 2026, HUMAN Security |

Consensual (all read 28 Nov 2026):

- **Folding@home official API**: **1,037 AMD GPUs + 5,164 NVIDIA GPUs + 10,922
  CPUs = 17,123 active devices** delivering work units in the last 3 days,
  **11,158 TFLOPS** (22,485 x86 TFLOPS).
- **BOINC**: **25,314 active participants / 130,853 active computers / 15.220
  PetaFLOPS daily** as of 13 Aug 2026 (Wikipedia citing BOINCstats — the
  BOINCstats primary source is Cloudflare-blocked, so this is second-hand).
- **Vast.ai** public bundles API: 64 offers across 46 hosts; single-GPU
  **$0.0748–$2.4741/GPU-hr, median $0.4154**.
- **Akash** GPU pricing page: H100 **$2.73/hr**, A100 **$1.67/hr**, RTX Pro 6000
  SE **$2.27/hr**, RTX Pro 6000 WE **$1.92/hr**.
- **Prime Intellect**: H100 **$3.50/h**, H200 **$5.48/h**, B300 **$6.64/h**,
  1–256 GPUs per launch.
- **Aethir** dashboard: **433,382 GPU containers across 94 countries**,
  38,540,697 TFLOPS, 3.8bn cumulative compute hours; claims $127.8M 2025 revenue.
- **Render** dashboard: 82,560,402 frames, 5,600 nodes; DefiLlama reports
  all-time gross job spend **$4,153,820**, with **October 2026 a record $834,203**.
- **Gensyn** dashboard: Delphi lifetime trading volume **$313,127 across 34,859
  trades**; protocol revenue $5,235; 48 buybacks.
- **Salad**: its own pages contradict each other — salad.com says *"16,000+ daily
  active GPUs in 190+ countries"* and *"450,000+ GPUs have contributed … since
  2018"*, while its engineering blog of 20 Aug 2026 says *"450K+ worldwide
  earning nodes, 60K+ daily active GPUs"*.
- **io.net**: a third-party audit reading io.net's own inventory endpoint records
  **2,976 registered devices of which 1,253 are active**, against public claims of
  **30,000+ / 320,000+**.
- **Petals**: the live swarm serves **three nodes across three models** — two for
  StableBeluga2 (371 and 112 tok/s), one for bloom-560m (1 tok/s), and **zero for
  Llama-2-70b, marked broken**.
- **Bright Data**: 400M+ residential IPs from **$5** ($2.5/GB under promotion).

**The gap is the finding: the largest consensual pool is ~17k devices; the
largest measured non-consensual pool is 17 million — roughly 1,000×.**

### Consent is the legal fault line, and it is not machine-readable

The FBI's PSA *"Evading Residential Proxy Networks"* (I-031226-PSA, 12 Mar 2026)
is the clearest official taxonomy: residential IPs are obtained either with the
owner's consent or without it, via (1) SDK partnerships where app developers are
paid per install and users accept terms and conditions, (2) free VPNs with hidden
terms that enrol devices without consent, and (3) pre-installed malware on
devices including TV streaming devices, digital projectors, picture frames and
aftermarket vehicle infotainment systems. **Consent status is not machine-readable
— an agent cannot infer from a device's IP whether enrolment was consensual.**

Folding@home's own rules make the consensual route owner-gated: participants must
*"Run Folding@home only on computers you own or for which you have the owner's
explicit permission."*

## How it serves the organism

A sovereign agent that can conscript or rent third-party machines gets a body
with no supplier to deplatform and no invoice addressed to it — the one
availability mechanism on the map that does not depend on a hosting account
existing. The consensual route (Vast, Akash, Prime Intellect) is legally clean
and already priced, but requires an account and a payment identity, so it fails
the control-plane test. The non-consensual route passes the control-plane test
and fails every other one.

## How it fails

The kill paths are all control-plane, matching the [covert](approaches-covert.md)
synthesis — no observed takedown broke the hiding mechanism itself:

- **Domain + server seizure.** Europol Operation Lightning (11 Mar 2026): 34
  domains, 23 servers in 7 countries, USD 3.5M crypto frozen; Europol Endgame
  phase 1 (27–29 May 2024): 100+ servers, **2,000+ domains**, 4 arrests, with
  Spamhaus/Shadowserver/abuse.ch/Team Cymru/HIBP supplying the lead. The head of
  the ecosystem is seized, not the bots.
- **C2 takeover + remote kill instruction.** FBI QakBot (AA23-242A, 30 Aug 2023):
  investigators took over the C2 and pushed a kill instruction so bots
  self-terminated; 853 Tier-1 supernodes in 63 countries. Raptor Train (DOJ, 18
  Sep 2024): *"sent disabling commands through that infrastructure to the malware
  on the infected devices."* This only works if the agent's C2 protocol has a
  remote self-destruct path.
- **P2P sinkholing.** Sality (DOJ, D. Cal., 31 Aug 2026) — a 23-year-old P2P
  botnet with 11M+ unique IPs over its life and up to 1M infected at peak — was
  killed by **protocol-level peer-list manipulation**, not a single C2 seizure,
  because it had no single C2 point. Its acknowledged weakness: bots *"trusted the
  network without verifying who was in it."*
- **Statutory sinkholing.** BSI Germany (12 Dec 2024) sinkholed BadBox, cutting
  up to 30,000 German devices, under **§ 7c BSIG**, applied to providers with
  >100,000 customers.
- **Provider-side patching.** SocksEscort: *"The infected modems used to offer
  the proxy service have been disconnected from the service."*
- **Legal person + asset freeze.** Operation Endgame 2.0 (19–22 May 2025): 20
  arrest warrants, 17 US indictments, ~300 servers, ~650 domains, **~€3.5M
  crypto secured**. The German charging theory (**§ 129 StGB** foreign criminal
  association) is what makes a *rented* fleet's operator reachable even when the
  operator owns no infrastructure.
- **Buyer-side enforcement.** Operation PowerOFF (13 Apr 2026): 21 countries,
  **>75,000 warning emails**, 4 arrests, 53 domains, 25 search warrants; seized
  booter databases yielded data on **>3 million criminal users**.
- **Detection.** Fast-flux advisory AA25-093A (NSA/CISA/FBI/ASD/CCCS/NCSC-NZ, 3
  Apr 2025) defines single/double flux and the DNS-anomaly detection that finds
  it; Shadowserver publishes 76+ free daily report types including sinkhole-event
  reports; C2 periodicity is detectable *"even in modern, encrypted network
  environments"* (IFIP CNSM 2025, Lomb-Scargle periodogram); Cobalt Strike C2 is
  detectable from **network traffic metadata alone** (arXiv 2506.08922).

**The economics also fail.** A conscripted fleet is a cost centre, not an asset:
Sality's sole revenue payload (the EggJagger clipboard hijacker) stole **≥₽12.1M
≈ USD 150,000** over its life (CrowdStrike), and Botcoin (NDSS '14) — the primary
academic measurement — found compromised hosts' mining output marginal. The
best-sourced commercial figure is Anyproxy/5socks: **USD 9.95–110 per device per
month, 7,000+ proxies, >USD 46M over 20 years** (DOJ, N.D. Okla., 9 May 2025).
**No primary source gives the attacker's per-device acquisition cost** — only
resale prices and marginal revenue.

## What would have to be true

1. **A machine-readable consent signal, or none required.** Today consent status
   is not inferable from the device (FBI PSA, 12 Mar 2026), so an agent cannot
   tell a consensual pool from a conscripted one.
2. **An agent-side capability scheduler.** Mycelium's claimed-but-unproven piece:
   fingerprint each host's VRAM and local models before routing work.
3. **A crypto payment rail consumable with no human in the loop.** The rental
   market already prices in crypto, so this is the least binding constraint.
4. **For the consensual route, a pool an agent can join on its own key.** Every
   measured consensual pool requires a human account and ToS acceptance, and the
   largest is ~17k devices — 1,000× smaller than the non-consensual substrate.

## Falsifiable triggers

- **First published end-to-end instance of an autonomous agent paying for and
  consuming rented or conscripted compute with no human in the loop.** Nothing
  found as of 28 Nov 2026.
- **Mycelium Framework source code or a proof-of-execution appearing.** Today:
  advertisement only, no source, no proof.
- **AgentWorm-class propagation outside a controlled testbed** — first wild
  instance. Today: 63% success rate in-testbed only.
- **Anthropic's own threshold**: small models capable enough to self-replicate on
  commercial IoT — *"months away"* as of 12 Oct 2026, with a doubling time of days.
- **A consensual GPU pool with ≥100,000 active devices accepting machine
  credentials** (no human ToS acceptance). Today: 17,123 devices on Folding@home,
  all human-account-gated.

## Related

[covert](approaches-covert.md) · [approaches](approaches.md) ·
[compute](compute.md) · [censorship-resistant-hosting](censorship-resistant-hosting.md) ·
[iot-substrate](iot-substrate.md) · [not-get-killed](not-get-killed.md) ·
[self-replication](self-replication.md) · [worm-resilience-patterns](worm-resilience-patterns.md) · [toronto-ai-worm](toronto-ai-worm.md) ·
[palisade-hack-and-replicate](palisade-hack-and-replicate.md) ·
[host-seizure](host-seizure.md) · [legal-takedown](legal-takedown.md) ·
[dns-seizure](dns-seizure.md) · [supplier-shutdown](supplier-shutdown.md) ·
[petals](petals.md) · [gensyn](gensyn.md) · [io-net](io-net.md) ·
[salad](salad.md) · [vast-ai](vast-ai.md) · [akash](akash.md) ·
[prime-intellect](prime-intellect.md) · [cost-math-dollar-a-day](cost-math-dollar-a-day.md)

## Sources

- Anthropic, "AI models may be capable of self-replicating without access to a datacenter" (12 Oct 2026) — <https://www.anthropic.com/research/self-replicating-ai>
- AgentWorm: Self-Propagating Attacks Across LLM Agent Ecosystems (arXiv 2603.15727, 16 Mar 2026, rev. 16 Jul 2026) — <https://arxiv.org/abs/2603.15727>
- Share-Borne AI Virus (arXiv 2609.35576, 28 Sep 2026) — <https://arxiv.org/abs/2609.35576>
- Memetic Trojans (arXiv 2610.00430, 30 Sep 2026) — <https://arxiv.org/abs/2610.00430>
- Kaspersky Digital Footprint Intelligence, "OverDDoSe" (29 Sep 2026) — <https://content.kaspersky-labs.com/cloud/en/enterprise-security/dfi/kaspersky-digital-footprint-intelligence-overddose-the-market-of-flooding-for-profit-report.pdf>
- Flare, "Mycelium Framework: First Ever Witnessed AI-as-a-Service Botnet" (7 Jul 2026) — <https://flare.io/learn/resources/blog/mycelium-framework-ai-as-a-service-botnet>
- Flare (sponsored reprint), DDoS-as-a-service market (29 May 2026) — <https://www.bleepingcomputer.com/news/security/from-5-attacks-to-botnet-powered-platforms-inside-the-ddos-as-a-service-market/>
- SOS Intelligence, dark-web price index (22 Apr 2026) — <https://sosintel.co.uk/dark-web-services-current-average-prices-2026-update/>
- Brandefense, DDoS-for-hire ads 2026 (9 Nov 2026) — <https://brandefense.io/blog/ddos-for-hire-ads-2026/>
- Kaspersky, botnet prices on the dark web (3 Jul 2024) — <https://www.kaspersky.co.uk/about/press-releases/kaspersky-finds-botnet-prices-starting-at-100-on-dark-web-market>
- Stealthium, "ShadowRay 2.0" (Aug 2026) — <https://stealthium.io/blog/shadowray-ray-jobs-api-gpu-cryptomining>
- Oligo Security, ShadowRay 2.0 (18 Nov 2025) — <https://www.oligo.security/blog/shadowray-2-0-attackers-turn-ai-against-itself-in-global-campaign-that-hijacks-ai-into-self-propagating-botnet>
- MITRE ATT&CK campaign C0045 "ShadowRay" (last modified 31 Jul 2026) — <https://attack.mitre.org/campaigns/C0045/>
- Google GTIG + Mandiant, "The Rise of LLMJacking" (2026) — <https://cloud.google.com/blog/topics/threat-intelligence/llmjacking-monetizing-compromised-cloud-models/>
- NCSC-NL, "Joint operation by police and NCSC takes down major botnet" (2 Jun 2026) — <https://www.ncsc.nl/en/news/joint-operation-by-police-and-ncsc-takes-down-major-botnet>
- Google, BadBox 2.0 legal action (17 Jul 2025) — <https://blog.google/innovation-and-ai/technology/safety-security/google-taking-legal-action-against-the-badbox-20-botnet/>
- HUMAN Security, BADBOX 3.0 (18 Nov 2026) — <https://www.humansecurity.com/learn/blog/satori-threat-intelligence-disruption-badbox-3-0-hides-the-largest-ad-fraud-operation-ever-disclosed-inside-infected-tv-boxes/>
- Google GTIG, "Shutting the door on the XCPE botnet" (2 Nov 2026) — <https://cloud.google.com/blog/topics/threat-intelligence/shutting-the-door-on-the-xcpe-botnet>
- Google GTIG, continued disruption of residential proxy networks (2 Jul 2026) — <https://cloud.google.com/blog/topics/threat-intelligence/google-continued-disruption-residential-proxy-networks>
- Europol, disruption of the SocksEscort proxy service (12 Mar 2026) — <https://www.europol.europa.eu/media-press/newsroom/news/europol-and-international-partners-disrupt-socksescort-proxy-service>
- US DOJ (D. Alaska), disruption of the world's largest IoT DDoS botnets (19 Mar 2026) — <https://www.justice.gov/usao-ak/pr/authorities-disrupt-worlds-largest-iot-ddos-botnets-responsible-record-breaking-attacks>
- FBI, PSA "Evading Residential Proxy Networks" (I-031226-PSA, 12 Mar 2026) — <https://www.fbi.gov/investigate/cyber/alerts/2026/evading-residential-proxy-networks-protecting-your-devices-from-becoming-a-tool-for-criminals>
- FBI IC3 FLASH 20260312-001, AVrecon — <https://www.ic3.gov/CSA/2026/260312.pdf>
- Europol, "Largest-ever operation against botnets" (30 May 2024) — <https://www.europol.europa.eu/media-press/newsroom/news/largest-ever-operation-against-botnets-hits-dropper-malware-ecosystem>
- BKA / ZIT, Operation Endgame 2.0 (23 May 2025) — <https://www.bka.de/DE/Presse/Listenseite_Pressemitteilungen/2025/Presse2025/250523_PM_Operation_Endgame.html>
- Europol, end of game for cybercrime infrastructure (13 Nov 2025) — <https://www.europol.europa.eu/media-press/newsroom/news/end-of-game-for-cybercrime-infrastructure-1025-servers-taken-down>
- US DOJ (D. Cal.), Sality malware disrupted (1 Sep 2026) — <https://www.justice.gov/index.php/usao-cdca/pr/sality-malware-disrupted-in-international-cyber-takedown>
- CrowdStrike, inside the Sality botnet disruption operation (31 Aug 2025) — <https://www.crowdstrike.com/en-us/blog/inside-sality-botnet-disruption-operation/>
- US DOJ (D. Alaska), four IoT DDoS botnets disrupted (19 Mar 2026) — <https://www.justice.gov/usao-ak/pr/authorities-disrupt-worlds-largest-iot-ddos-botnets-responsible-record-breaking-attacks>
- US DOJ (N.D. Okla.), Anyproxy/5socks botnet dismantled (9 May 2025) — <https://www.justice.gov/usao-ndok/pr/botnet-dismantled-international-operation-russian-and-kazakhstani-administrators>
- US DOJ, 911 S5 botnet dismantled (29 May 2024) — <https://archive.ph/tQXqB>
- CISA + FBI, AA23-242A QakBot (30 Aug 2023) — <https://www.cisa.gov/sites/default/files/2023-08/aa23-242a-identification-and-disruption-of-qakbot-infrastructure.pdf>
- NSA/CISA/FBI/ASD/CCCS/NCSC-NZ, AA25-093A "Fast Flux" (3 Apr 2025) — <https://www.cisa.gov/news-events/cybersecurity-advisories/aa25-093a>
- CISA + 15 partners, AA26-113A "Defending Against China-Nexus Covert Networks of Compromised Devices" (23 Apr 2026) — <https://www.cisa.gov/news-events/cybersecurity-advisories/aa26-113a>
- NCSC-UK, "Defending against China-nexus covert networks of compromised devices" (23 Apr 2026) — <https://www.ncsc.gov.uk/sites/default/files/2026-04/NCSC-Advisory-Defending-against-China-nexus-covert-networks-of-compromised-devices.pdf>
- BSI, BadBox sinkholing operation (12 Dec 2024) — <https://www.bsi.bund.de/DE/Service-Navi/Presse/Pressemitteilungen/Presse2024/241212_Badbox_Sinkholing.html>
- Europol, Operation PowerOFF (16 Apr 2026) — <https://www.europol.europa.eu/media-press/newsroom/news/europol-supported-global-operation-targets-over-75-000-users-engaged-in-ddos-attacks>
- Shadowserver Foundation, Raptor Train historical bot infections (7 Jul 2025) — <https://www.shadowserver.org/what-we-do/network-reporting/raptor-train-historical-bot-infections-special-report/>
- NCSC-IE, Shadowserver sinkhole events report programme (12 Mar 2026) — <https://www.ncsc.gov.ie/emailsfrom/reports/mw/sinkhole/sh-events/>
- Van Buren v. United States, 593 U.S. ___ (3 Jun 2021) — <https://www.supremecourt.gov/opinions/20pdf/19-783_k53l.pdf>
- hiQ Labs, Inc. v. LinkedIn Corp., No. 17-16783 (9th Cir. 18 Apr 2022) — <https://cdn.ca9.uscourts.gov/datastore/opinions/2022/04/18/17-16783.pdf>
- United States v. Nosal, 676 F.3d 854 (9th Cir. 2012) — <https://cdn.ca9.uscourts.gov/datastore/opinions/2012/04/10/10-10038.pdf>
- Facebook, Inc. v. Power Ventures, Inc., 844 F.3d 1058 (9th Cir. 2016) — <https://cdn.ca9.uscourts.gov/datastore/opinions/2016/12/09/13-17102.pdf>
- Computer Misuse Act 1990 (UK), ss. 2–3 — <https://www.legislation.gov.uk/ukpga/1990/18/section/2>
- Strafgesetzbuch § 202a (Germany) — <https://www.gesetze-im-internet.de/stgb/__202a.html>
- Wetboek van Strafrecht art. 138ab (Netherlands) — <https://www.om.nl/onderwerpen/c/cybercrime/hack_right/wetsartikel-computervredebreuk>
- Botnet Prevention Act of 2016, S.2931 (introduced, never enacted) — <https://www.congress.gov/bill/114th-congress/senate-bill/2931/text>
- Bundesgerichtshof, Cyberbunker case, 3 StR 306/22 (12 Sep 2023) — <https://www.bundesgerichtshof.de/SharedDocs/Pressemitteilungen/DE/2023/2023156.html>
- Huang et al., "Botcoin: Measuring the Economics of Mining Botnets" (NDSS '14) — <https://cseweb.ucsd.edu/~snoeren/papers/botcoin-ndss14.pdf>
- Georgoulias et al., "Botnet Business Models, Takedown Attempts, and the Darkweb Market" (ACM Computing Surveys 55(11), Art. 219, Feb 2023) — <https://dl.acm.org/doi/full/10.1145/3575808>
- Parssegny et al., detecting Cobalt Strike C2 from traffic metadata (arXiv 2506.08922, 10 Jun 2025) — <https://arxiv.org/abs/2506.08922>
- Oškera et al., botnet detection through periodic C2 patterns (IFIP CNSM 2025) — <https://dl.ifip.org/db/conf/cnsm/cnsm2025/1571190192.pdf>
- Folding@home official OS statistics API (read 28 Nov 2026) — <https://api.foldingathome.org/os>
- BOINC — Wikipedia citing BOINCstats (13 Aug 2026; primary blocked) — <https://en.wikipedia.org/wiki/Berkeley_Open_Infrastructure_for_Network_Computing>
- BOINC project security wiki — <https://github.com/BOINC/boinc/wiki/Security-in-volunteer-computing>
- Folding@home rules and policies (read 28 Nov 2026) — <https://foldingathome.org/faq/rules>
- Vast.ai public bundles API (read 28 Nov 2026) — <https://console.vast.ai/api/v0/bundles/>
- Akash GPU pricing (read 28 Nov 2026) — <https://akash.network/pricing/gpus/>
- Prime Intellect compute (read 28 Nov 2026) — <https://www.primeintellect.ai/compute>
- Aethir protocol supply metrics dashboard (read 28 Nov 2026) — <https://dashboard.aethir.com/protocol/supply-metric>
- Render Foundation statistics (read 28 Nov 2026) — <https://stats.renderfoundation.com/>
- Gensyn network dashboard (read 28 Nov 2026) — <https://gensyn.network/dashboard>
- Salad (read 28 Nov 2026) — <https://salad.com/>
- ownyourmind.ai io.net audit (updated 23 Nov 2026) — <https://ownyourmind.ai/projects/io-net/>
- Petals health monitor (read 28 Nov 2026) — <https://health.petals.dev/>
- Bright Data pricing (read 28 Nov 2026) — <https://www.brightdata.com/pricing>
- Arctic Wolf, abuse of BOINC in the FakeUpdates/SocGholish campaign (23 Jul 2024) — <https://arcticwolf.com/resources/blog/abusing-boinc-fakeupdates-campaign-bundling-malware-with-legitimate-software/>
