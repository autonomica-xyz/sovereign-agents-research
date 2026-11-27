---
title: "Cost math of a $1/day 24/7 open-weight agent"
category: compute
status: seed
sources: []
updated: 2026-11-27
---

# Cost math of a $1/day 24/7 open-weight agent

> Re-derived from primary sources on 27 Nov 2026: a 24/7 agent running an open-weight
> model for $1/day ($30/month) is **not** affordable on dedicated 24/7 GPU rental at any
> price observed anywhere — the floor is $0.0417/GPU-hour and the market is 11–115× above
> it. It **is** affordable today through API metering, and at that price the ceiling is
> already **70B-class dense** (llama-3.3-70b at $0.10/Mtok in via DeepInfra), not 8B-class.
> The binding constraint is not model price but the agent's own context-re-read
> amplification (measured at 291:1 re-read:written).

## Details

### The budget, stated once

$1/day = **$30/month**. A GPU dedicated 24/7 needs 720 GPU-hours/month. So the
break-even hourly rate for dedicated 24/7 GPU is:

    $30 / 720 h = $0.0417 per GPU-hour

Every GPU rate below is measured per-GPU-hour on the provider's own pricing page,
fetched 27 Nov 2026.

### Measured inputs — GPU rental ($/GPU-hour)

| Provider | GPU | $/GPU-hr | Source URL | Date on page |
|---|---|---|---|---|
| Vast.ai | RTX 4090 24GB | **0.07** (floor) / 0.49 (median) | <https://www.vast.ai/pricing> | accessed 2026-11-27 |
| Vast.ai (live API, n=64 offers) | RTX 4090 | 0.1202 min / 0.468 median; verified-only min 0.3747 | <https://console.vast.ai/api/v0/search/asks/> | accessed 2026-11-27 |
| Vast.ai | RTX A5000 / A6000 / L40S / A100 SXM4 / H100 SXM / H200 / B200 | 0.14 / 0.40 / 0.47 / 0.39 / 1.59 / 2.63 / 7.50 (floors) | <https://www.vast.ai/pricing> | accessed 2026-11-27 |
| RunPod (Community) | RTX A5000 / 3090 / 4090 / A40 / L4 / 5090 | 0.16 / 0.22 / 0.34 / 0.35 / 0.44 / 0.69 | <https://www.runpod.io/pricing> | page states *Updated November 12, 2026* |
| RunPod (Community) | A100 PCIe / H100 PCIe / H100 SXM / H200 / B200 / B300 | 1.19 / 1.99 / 2.69 / 3.59 / 5.98 / 6.94 | <https://www.runpod.io/pricing> | *Updated November 12, 2026* |
| RunPod (Serverless, per active worker) | 4090 / 24GB-class / L4-3090-A5000 | 1.34 / 0.75 / 0.58 | <https://www.runpod.io/pricing> | *Updated November 12, 2026* |
| Lambda | A6000 48GB / A100 40GB / H100 PCIe / H100 SXM | 1.09 / 1.99 / 3.79 / 4.89 | <https://lambda.ai/service/gpu-cloud/pricing> | accessed 2026-11-27 |
| Nebius | H100 / H200 preemptible | from 0.79 | <https://nebius.com/prices> | accessed 2026-11-27 |
| Nebius | H100 / H200 / B200 on-demand | 4.50 / 5.40 / 8.50 | <https://nebius.com/prices> | accessed 2026-11-27 |
| CoreWeave (HGX H100, per GPU) | on-demand / spot | 6.16 / 2.46 (node $49.24 / $19.71 per 8) | <https://www.coreweave.com/pricing> | accessed 2026-11-27 |
| Crusoe (self-serve) | H100 / H200 / B200 | 5.50 / 6.00 / 9.65 | <https://crusoe.ai/pricing> | accessed 2026-11-27 |
| Crusoe (GPU instances) | H100 / A100 SXM / A100 PCIe / L40S | 3.90 / 2.30 / 2.00 / 1.50 | <https://crusoe.ai/pricing> | accessed 2026-11-27 |
| Paperspace (DO) | A5000 / A6000 | 1.38 / 1.89 | <https://docs.digitalocean.com/products/paperspace/pricing/> | accessed 2026-11-27 |
| Baseten (dedicated) | T4 / L4 / A10G / A100 / H100 MIG | 0.6312 / 0.8484 / 1.2072 / 4.00 / 3.75 | <https://www.baseten.co/pricing/> | accessed 2026-11-27 |
| Together | gpt-oss-120B $0.15/$0.60 per Mtok; Qwen3.5 9B $0.17/$0.25 | (token) | <https://www.together.ai/pricing> | accessed 2026-11-27 |
| Fireworks | serverless from $0.05/1M input; GPT-OSS 120B $0.10/$0.50 | (token) | <https://fireworks.ai/pricing> | accessed 2026-11-27 |

### Measured inputs — electricity

| Source | Figure | Unit | URL | Date on page |
|---|---|---|---|---|
| EIA Electric Power Monthly Table 5.3 | US residential 18.17; industrial 9.52 (Sept 2026). 2026 YTD: residential 18.19, industrial 9.14 | US ¢/kWh | <https://www.eia.gov/electricity/monthly/epm_table_grapher.php?t=epmt_5_3> | *Data for September 2026, Release Date: November 24, 2026* |
| EIA Table 5.6.A | US residential by state, Sept 2026 (e.g. PA 22.20, IA 14.99, ND 14.29) | US ¢/kWh | <https://www.eia.gov/electricity/monthly/epm_table_grapher.php?t=epmt_5_6_a> | *Data for September 2026, Release Date: November 24, 2026* |
| Eurostat | EU household (2 500–5 000 kWh) 0.2832; EU non-household (500–2 000 MWh) 0.1800 | EUR/kWh, 1H 2026 | <https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Electricity_price_statistics> | first half of 2026; next update April 2027 |
| Eurostat news | EU non-household 0.18/kWh, −5.4% y/y; highest Ireland 0.27, lowest Finland 0.09 | EUR/kWh, 1H 2026 | <https://ec.europa.eu/eurostat/web/products-eurostat-news/w/ddn-20261104-1> | *4 November 2026* |

### Measured inputs — board power and local hardware

| Item | Value | URL | Date |
|---|---|---|---|
| RTX 4090 Total Graphics Power | 450 W | <https://www.nvidia.com/en-us/geforce/graphics-cards/compare/?section=compare-specs> | accessed 2026-11-27 |
| RTX 5090 Total Graphics Power | 575 W | same NVIDIA compare page | accessed 2026-11-27 |
| RTX A6000 Max Power Consumption | 300 W | <https://www.nvidia.com/en-us/design-visualization/rtx-a6000/> | accessed 2026-11-27 |
| L40S Max Power Consumption | 350 W | <https://www.nvidia.com/en-us/data-center/l40s/> | accessed 2026-11-27 |
| H100 SXM / PCIe Max TDP | up to 700 W / 350–400 W configurable | <https://www.nvidia.com/en-us/data-center/h100/> | accessed 2026-11-27 |
| GPU useful life (datacenter fleet) | **technology equipment 6 years** | CoreWeave 10-K FY2025, R32 Property and Equipment <https://www.sec.gov/Archives/edgar/data/1769628/000176962826000104/R32.htm> | filed 2026-03-02, period 2025-12-31 |
| RTX 4090 24GB used, eBay sold | $3 045 median (100 sales/14 d) | <https://www.gpusold.com/gpu/rtx-4090-24> | *Updated Nov 19* |
| RTX 5090 32GB used, eBay sold | $6 070 median (130 sales/14 d) | <https://www.gpusold.com/gpu/rtx-5090-32> | *Updated Nov 25* |
| RTX A6000 48GB used, eBay sold | $4 275 median (16 sales/14 d) | <https://www.gpusold.com/gpu/rtx-a6000-48> | *Updated Nov 25* |
| RTX 4090 launch MSRP | "Starting at $1599.00" | <https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4090/> | accessed 2026-11-27 |

### Measured inputs — token prices ($/Mtok)

OpenRouter's live API (`https://openrouter.ai/api/v1/models`) and the per-model
pages (fetched 27 Nov 2026) list both a router-level price and per-provider
prices; the floor per provider is what a cost-minimising agent can actually get.

| Model | In | Out | Floor provider | URL |
|---|---|---|---|---|
| gpt-oss-20b (21B MoE, 3.6B active) | 0.0153 | 0.0765 | Darkbloom (cache 0.00765) | <https://openrouter.ai/openai/gpt-oss-20b> |
| gpt-oss-120b (117B MoE, 5.1B active) | 0.03 | 0.15 | Venice/NEAR/CoreWeave (cache 0.03) | <https://openrouter.ai/openai/gpt-oss-120b> |
| llama-3.3-70b (dense 70B) | 0.10 | 0.32 | DeepInfra Turbo (20 tok/s, 97.98% uptime) | <https://openrouter.ai/meta-llama/llama-3.3-70b-instruct> |
| llama-3.3-70b | 0.59 | 0.79 | Groq (215 tok/s, cache 0.295) | same page |
| llama-3.1-8b | 0.02 | 0.04 | DeepInfra (70 tok/s) | <https://openrouter.ai/meta-llama/llama-3.1-8b-instruct> |
| llama-3.1-8b | 0.05 | 0.08 | Groq (419 tok/s) | same page |
| qwen3-14b | 0.10 | 0.22 | Nextbit (59 tok/s) | <https://openrouter.ai/qwen/qwen3-14b> |
| qwen3-32b | 0.08 | 0.28 | DeepInfra (26 tok/s) | <https://openrouter.ai/qwen/qwen3-32b> |
| deepseek-v4-flash-0731 | 0.047 | 0.30 | OpenRouter | OpenRouter API |
| deepseek-v3.2 | 0.26 | 0.38 | OpenRouter | OpenRouter API |
| nemotron-3-nano-30b-a3b | 0.06 | 0.24 | OpenRouter | OpenRouter API |
| nemotron-3-super-120b-a12b | 0.075 | 0.40 | OpenRouter | OpenRouter API |
| granite-4.2-8b | 0.06 | 0.15 | OpenRouter | OpenRouter API |
| deepseek-flash direct (off-peak) | 0.15 (cache-miss) / 0.003 (cache-hit) | 0.60 | DeepSeek first-party | <https://api-docs.deepseek.com/quick_start/pricing> |
| deepseek-v4-pro direct (off-peak) | 0.66 / 0.022 cache-hit | 1.98 | DeepSeek first-party | same page |

Throughput reference points: gpt-oss-120b **198 tok/s** median across providers
(Artificial Analysis, <https://artificialanalysis.ai/models/gpt-oss-120b>); local
Qwen3-8B on a rented RTX 4090 at **164 tok/s** single-stream
(<https://www.systemdesign.academy/llm-tokens-per-second>, 18 Nov 2026) and
**155 tok/s** under llama.cpp Q4_K_M
(<https://llm-speed.com/m/qwen3-8b>); Qwen3-14B on a 4090 **84.4 tok/s** at 4k
context, decaying to 38.8 tok/s at 64k.

### Measured inputs — deflation rate

| Figure | Source | Date on page |
|---|---|---|
| Cost of a given level of AI performance fell **~47%/quarter = 13×/yr** since 2023; 66%/qtr (75×/yr) for just-debuted SOTA, 32%/qtr (4.7×/yr) two years after debut | Epoch AI, "The plunging price of thought" <https://epoch.ai/publications/the-plunging-price-of-thought> | *Published 2026-09-22* |
| Price range of decline **9×–900×/yr** by benchmark; GPT-4-level on GPQA fell 40×/yr; "fastest drops in the past year, so it's less clear that those will persist" | Epoch AI data insight <https://epoch.ai/data-insights/llm-inference-price-trends> | *Mar. 12, 2025* |
| Hardware perf/$ improves **~30%/yr** at fixed precision (P100 $16k → V100 $20k → A100 $25k → H100 $44k per GPU incl. server) | Epoch AI <https://epoch.ai/data-insights/price-performance-hardware> | *Oct. 23, 2024* (CSV updated Nov 24 2025) |
| Agentic inference capacity grew **4.6× in one year** (Q2 2025→Q2 2026) vs 2.6× for peak compute | Epoch AI <https://epoch.ai/data-insights/agentic-inference-capacity-growth> | *Published 2026-11-18* |

**Derivation check on the 13×/yr:** 1 − 0.47 = 0.53; 0.53⁴ = 0.0789; 1/0.0789 =
**12.67×/yr** — matches Epoch's stated 13×/yr. The number is real and sourced.

**But it is capability-adjusted, not a fixed-model price.** Epoch's own MMLU table
(same 2025 insight) shows what a *fixed* small-model class actually cost:
GPT-3.5-level (MMLU ≥ 64.8) $20.00/Mtok (Nov 2022) → $0.07 (Oct 2024) = 285.7×
in 23 months = 19.1×/yr; then $0.07 (Oct 2024) → $0.02 (Nov 2026, DeepInfra
llama-3.1-8b) = 3.5× in 25 months = **1.8×/yr**. Over the full 49-month span
$20.00 → $0.02 = 1000× = **5.4×/yr compound**. The 13×/yr headline applies to
frontier capability thresholds; a fixed 8B-class line has deflated at roughly
2–5×/yr.

### Measured inputs — what an always-on agent actually burns

There is **no published tokens/second figure for a 24/7 agent**. Only proxies:

| Proxy | Number | Source | Date |
|---|---|---|---|
| Measured personal fleet | 225.1B tokens/30 d over 736 633 responses; 97.9% cache reads; 291 re-reads per 1 written; avg 305 k context + ~1 000 written per response; 6.9 agents concurrent on average; ≈$97 000/month at list price | <https://jacksonly.xyz/blog/225-billion-claude-code-tokens-in-30-days> | *18 October 2026* (secondary/self-reported) |
| Vendor multipliers | agents use ~4× more tokens than chat; multi-agent systems ~15× chat; token usage alone explains 80% of BrowseComp performance variance | Anthropic <https://www.anthropic.com/research/multi-agent-research-system> | *Jun 13, 2025* |
| Always-on idle-path study | OpenClaw default 30-min heartbeat, 24/7 = 48 wakes/day, ~18 100-token wake-up context; 74–97% of an always-on agent's bill is idle wake-ups; 30 agents = $4 644/mo at Opus 5 prices | <https://cognio.so/resources/guides/ai-agent-token-costs> | *2026-08-17* (secondary, vendor study) |
| Researcher-scale measured | median researcher $2 400/day, p90 $23 000/day at API list prices; agent workdays per researcher 0.5 → 5.7 | OpenAI <https://openai.com/index/research-acceleration-jagged-frontier/> | *November 18, 2026* |
| Same, trend | median researcher coding-agent spend <$1/day (Jan 2026) → $601/day (mid-Aug 2026); p90 $7 047/day; doubling time ~1 month | Epoch AI <https://epoch.ai/data-insights/openai-coding-agent-spending> | *Published 2026-10-05* |
| Peer-reviewed agent token study | agentic coding tasks consume 3500× more tokens than code reasoning and 1200× more than code chat; input tokens dominate; run-to-run variance up to 30×; Kimi-K2 and Claude-Sonnet-4.5 consume >1.5M more tokens than GPT-5 on identical tasks | arXiv 2604.22750 <https://arxiv.org/abs/2604.22750> | *2026-10-02* |
| Prompt caching effect | caching reduces API cost 41–80% and TTFT 13–31% across OpenAI/Anthropic/Google; >500 agent sessions | arXiv 2601.06007 <https://arxiv.org/abs/2601.06007> | *2026-01-31* |

## Derived numbers

### 1. Dedicated 24/7 GPU is not $1/day at any observed price

    $1/day = $30/month = 720 GPU-hours
    break-even rate = $30 / 720 = $0.0417 / GPU-hour

| Option | $/GPU-hr | 720 h/mo | $/day | Verdict |
|---|---|---|---|---|
| Vast RTX 4090 floor | 0.07 | $50.40 | **$1.68** | 1.7× over — fails even at the tail price |
| RunPod A5000 community | 0.16 | $115.20 | $3.84 | 3.8× over |
| RunPod RTX 4090 community | 0.34 | $244.80 | $8.16 | 8.2× over |
| Vast RTX 4090 median | 0.46825 | $337.14 | $11.24 | 11.2× over |
| Nebius H100 preemptible | 0.79 | $568.80 | $18.96 | 19× over |
| Lambda A6000 48GB | 1.09 | $784.80 | $26.16 | 26× over |
| Vast H100 SXM median | 2.2022 | $1 585.58 | $52.85 | 53× over |
| Lambda H100 SXM | 4.89 | $3 520.80 | $117.36 | 117× over |

**Duty-cycle break-even** (hours/day of dedicated GPU that $1/day buys):

    Vast 4090 floor $0.07   -> 428.6 h/mo = 14.29 h/day = 59.5% duty
    Vast 4090 API min $0.1202 -> 249.6 h/mo =  8.32 h/day = 34.7% duty
    RunPod A5000 $0.16      -> 187.5 h/mo =  6.25 h/day = 26.0% duty
    RunPod 4090 $0.34        ->  88.2 h/mo =  2.94 h/day = 12.3% duty
    Vast 4090 median $0.468  ->  64.1 h/mo =  2.14 h/day =  8.9% duty
    Nebius H100 preempt $0.79 ->  38.0 h/mo =  1.27 h/day =  5.3% duty
    Lambda A6000 $1.09       ->  27.5 h/mo =  0.92 h/day =  3.8% duty
    Vast H100 SXM median $2.20 -> 13.6 h/mo =  0.45 h/day =  1.9% duty

### 2. Owned hardware at $1/day is also out of reach on capital alone

Model: capital charge = price / (6 years × 365 days); electricity charged only on
hours the GPU draws load; US residential power 18.17 ¢/kWh.

| Card | Price | Capital $/day | + elec @1h/d | @4h/d | @24h/d |
|---|---|---|---|---|---|
| RTX 4090 used | $3 045 | 1.390 | 1.472 | 1.717 | 3.353 |
| RTX 4090 new MSRP | $1 599 | 0.730 | 0.812 | 1.057 | 2.692 |
| RTX A6000 used | $4 275 | 1.952 | 2.007 | 2.170 | 3.260 |
| RTX 5090 used | $6 070 | 2.772 | 2.876 | 3.190 | 5.279 |

Even a **new** 4090 at MSRP, run 4 h/day on residential power, is $1.057/day —
just over. At US **industrial** power (9.52 ¢/kWh) it is $0.901/day at 4 h/day
but $1.758/day at 24 h/day. In the EU, a used 4090 at 4 h/day on household power
(€0.2832/kWh) is €1.90/day; 24 h/day on non-household power (€0.18/kWh) is
€3.33/day.

**Buy-vs-rent payback** (4090 used, $3 045, US residential power = $0.082/h):

    rent $0.16/h -> net $0.078/h -> 53.3 months
    rent $0.34/h -> net $0.258/h -> 16.2 months
    rent $0.49/h -> net $0.408/h -> 10.2 months
    rent $2.20/h -> net $2.118/h ->  2.0 months

### 3. API path: the model class $1/day actually buys

Load profiles, defined from the fetched agent-consumption sources:
idle = 48 wakes/day × 20 000 ctx in + 200 out (Cognio's OpenClaw heartbeat
defaults); light = 4×20 000 + 500; working = 24×20 000 + 1 000;
heavy = 96×20 000 + 2 000.

| Model | idle | light | working | heavy |
|---|---|---|---|---|
| gpt-oss-20b @ 0.0153/0.0765 | $0.0154 | $0.0014 | $0.0092 | $0.0441 |
| gpt-oss-120b @ 0.03/0.15 | $0.0302 | $0.0027 | $0.0180 | $0.0864 |
| **llama-3.3-70b @ 0.10/0.32** | **$0.0991** | $0.0086 | $0.0557 | $0.2534 |
| llama-3.3-70b @ Groq 0.59/0.79 | $0.5740 | $0.0488 | $0.3022 | $1.2845 (fails) |
| qwen3-32b @ 0.08/0.28 | $0.0795 | $0.0070 | $0.0451 | $0.2074 |
| llama-3.1-8b @ 0.02/0.04 | $0.0196 | $0.0017 | $0.0106 | $0.0461 |

**What $30/month buys in raw token terms** (spend the whole budget on one model):

    llama-3.1-8b  $0.02/$0.04 -> 1 500M in + 750M out tok/day
    gpt-oss-20b   $0.0153/$0.0765 -> 1 961M in + 392M out tok/day
    gpt-oss-120b  $0.03/$0.15 -> 1 000M in + 200M out tok/day (= 2 315 out tok/s sustained)
    llama-3.3-70b $0.10/$0.32 ->   300M in +  94M out tok/day (= 1 085 out tok/s sustained)
    llama-3.3-70b $0.59/$0.79 ->    51M in +  38M out tok/day (=   440 out tok/s sustained)

A 1 085 tok/s sustained output rate is ~5–50× the *actual* generation speed of
these models (20–215 tok/s via OpenRouter), so the budget is not
throughput-limited — it is limited by how many tokens the agent's own loop
re-reads.

### 4. The amplification gap

Jackson Ly's measured fleet: 225.1B tokens/30 d = 7.35B input-side tok/day
(97.9% cache reads) + 25.5M output tok/day.

    at gpt-oss-20b floor (0.0153 in / 0.0765 out):
      7.35e9 x 0.0153/1e6 + 2.55e7 x 0.0765/1e6 = $114.34/day
      -> $1/day = 0.875% of his token volume
    with cache-read tier at 0.00765:
      7.35e9 x 0.00765/1e6 + 2.55e7 x 0.0765/1e6 = $58.15/day
      -> $1/day = 1.72% of his volume

At a frontier-ish price (deepseek-v4-pro direct off-peak, $0.66/Mtok in — fetched
from DeepSeek's own pricing page) his profile would cost $4 901/day.
**The 291:1 re-read ratio, not the model price, is what separates $1/day from
$3 233/day.** Halving the re-read ratio (context compaction, isolated sessions,
smaller scratch context) is worth more than a 10× model-price cut.

### 5. Deflation applied to the $1/day envelope

At Epoch's frontier rate (13×/yr, an upper bound because it is
capability-adjusted):

    70B-class input price: $0.10/Mtok today
      +1y -> $0.0077    +2y -> $0.0006
    8B/20B-class input price: $0.0153/Mtok today
      +1y -> $0.00118   +2y -> $0.00009

At a conservative fixed-class 2.5×/yr (the rate actually observed for small
models in 2024–2026):

    70B-class: $0.10 -> $0.040 (1y) -> $0.016 (2y)
    8B/20B:    $0.0153 -> $0.0061 (1y) -> $0.0024 (2y)

Hardware deflation is slower: at Epoch's ~30%/yr perf-per-dollar gain, a Vast
4090 median of $0.46825/hr becomes $0.2771/hr in 2 years → $6.65/day at 24/7,
still 6.6× over $1/day. Reaching the $0.0417/hr break-even from today's median
at 30%/yr takes ~9.2 years; from the $0.07 tail, ~2.0 years.

## How it serves the organism

The cost floor tells you where an organism may legally and financially live.
A $1/day budget rules out **any** dedicated 24/7 GPU, including a rented
consumer card, at any provider's current list price. It therefore forces a
**metered-API architecture**: a small always-on process that wakes on events
(webhooks, cron, file changes, chain events) and calls a hosted model, with
aggressive context isolation so each wake re-reads only what changed. The
budget is per-day, not per-call, so a bursty workload (many wakes in one
minute, silence for six hours) is cheaper per unit of work than a uniform
heartbeat — the opposite of the "always on" framing, and the reason the
cheapest agents will be event-driven rather than continuously-reasoning.

At $1/day the affordable ceiling is **70B-class dense** (llama-3.3-70b) and
**117B-class MoE** (gpt-oss-120b, 5.1B active) on the API path, which is
enough capability for tool use, coding and long-horizon agentic work; the
binding cost is not intelligence-per-dollar but the agent's own re-read
amplification. A sovereign organism should therefore spend its budget on
**context engineering** (compaction, isolated sessions, cache discipline)
before it spends it on a bigger model.

## How it fails

- **Provider concentration.** The 70B-class floor price ($0.10/Mtok) is a
  single provider's "Turbo" tier (DeepInfra, 20 tok/s, 97.98% uptime). A
  price-flooring or capacity-constrained event at that provider raises the
  agent's floor cost by 3–6× (Groq's 70B price is $0.59/$0.79), which at
  heavy duty breaks the $1/day budget outright ($1.28/day).
- **Idle-path waste.** With OpenClaw-style 30-minute heartbeats, 74–97% of
  the bill is the agent waking, reloading context, and finding nothing to do
  (Cognio's measured model). A sovereign agent that must be reachable 24/7
  inherits this cost even when nobody is using it.
- **Amplification.** Multi-agent designs cost ~15× chat in tokens
  (Anthropic, measured). A $1/day budget buys a *single-agent* 70B loop with
  room to spare, or a multi-agent loop at roughly 8B-class — the parallelism
  that makes agent systems good is exactly what the budget forbids.
- **Usage growth outruns price deflation.** OpenRouter's own reporting (cited
  in this repo's economy page) shows token volume rising faster than prices
  fall; Epoch's OpenAI-spend insight shows median researcher agent spend
  doubling monthly. A fixed $1/day budget is a *capped* budget: the deflation
  trend lowers unit price while the agent's own ambition raises unit volume.
- **Hardware deflation does not reach the target.** Even at Epoch's 30%/yr
  perf-per-dollar, dedicated 24/7 rental is ~9 years from the $0.0417/hr
  break-even. Do not plan around a hardware price collapse.
- **The 13×/yr figure is easy to misuse.** It is capability-adjusted and
  measured at frontier thresholds; for a fixed small-model line the observed
  2024–2026 rate was ~1.8×/yr. Quoting 13×/yr to justify a specific small-model
  price in 2027 overstates the trend by roughly 2–3×.

## Falsifiable triggers

The answer changes if any of these become true (each is a single measurable
fact, checkable on a provider's own pricing page):

- **A 24GB-class GPU rents at ≤ $0.0417/GPU-hour on a reputable provider.**
  Today the floor is $0.07 (Vast, single unverified tail offer) and the median
  is $0.46825 — 11× above break-even. At $0.0417 the 24/7 dedicated route
  becomes $1/day and the ownership argument inverts.
- **A 70B-class open model is served under $0.05/Mtok input with ≤ 60 tok/s
  sustained.** Best observed today is $0.10 (DeepInfra Turbo). Halving it
  doubles the affordable duty profile at every load shape.
- **A 20B-or-smaller open model is served under $0.005/Mtok input on a
  cache-read tier.** DeepSeek direct off-peak cache-hit is $0.003/Mtok today;
  gpt-oss-20b's cache-read tier is $0.00765. At ≤$0.005 the $1/day budget
  covers ~7× the measured Jackson-Ly token volume.
- **A provider exposes a 70B-class open model at ≥ 150 tok/s under $0.15/Mtok
  blended.** Today the fastest 70B is Groq at 215 tok/s but $0.59/$0.79; the
  cheapest 70B is 20 tok/s. Closing that gap is what makes a 70B agent
  *usable*, not merely affordable.
- **Cache-read pricing falls to ≤ $0.001/Mtok.** At a 291:1 re-read ratio,
  the cache tier is ~99.7% of the bill; a 10× cut in cache-read price is a
  10× cut in the agent's total cost, dwarfing any model-price change.
- **Used 4090-class hardware falls below ~$1 200.** At $1 599 new the capital
  charge alone is $0.73/day, leaving $0.27/day for power; below ~$1 200 the
  owned-hardware route clears $1/day at 4 h/day on US residential power.

## Gaps / could not verify

- **No published tokens/second for a 24/7 agent exists.** The closest
  published measurements are a self-reported personal fleet
  (jacksonly.xyz), a vendor study with no audited billing (Cognio Labs), and
  researcher-spend aggregates (OpenAI, Epoch AI). None is a controlled
  24/7-agent token-rate measurement. All are labelled as proxies.
- **P95/P99 uptime per provider was not collected.** OpenRouter reports
  per-provider uptime (e.g. DeepInfra Turbo 97.98% for llama-3.3-70b) but I
  did not survey availability across all ten providers, so the price floors
  above should be read as best-case prices, not reliable prices.
- **Crusoe GPU-instances prices were mapped by position in a JS-rendered
  grid, not by table cell.** The page exposes no `<table>` element; the
  H100/H200/B200/A100/L40S assignments ($3.90 / $5.40 / $8.50 / $2.30 / $1.50)
  come from matching the visible order of the two price columns. The
  Self-Serve Deployments block ($5.50 H100, $6.00 H200, $9.65 B200) is
  unambiguous and is the figure to quote.
- **Vast.ai's "from" prices are tail offers, not typical.** The visible
  $0.07 RTX 4090 floor is one unverified host; the same query returns a median
  of $0.46825 and a verified-only minimum of $0.3747. The pricing page's own
  "median" tiles ($0.49 for 4090, $1.73 for H100 SXM, $10.00 for B200) are the
  honest figures.
- **NVIDIA 4090/5090 board power was taken from the comparison table, not the
  product page** — the individual product pages render specs behind a
  client-side toggle. The values match NVIDIA's Ada architecture whitepaper
  (TGP 450 W for the 4090).
- **GPU lifetime beyond CoreWeave's 6-year accounting policy was not
  independently sourced.** CoreWeave's policy is a *booked* accounting life
  for a fleet under contract, not a physical failure curve; aravolta's
  practitioner summary (1–3 years for top datacenter GPUs at 60–70%
  utilization) is a secondary blog and was not used in the arithmetic. If
  physical life is 3 years rather than 6, every ownership figure above
  doubles and the owned-hardware route fails outright.
- **No spot/interruptible price was obtained for the cheapest consumer
  cards.** The Vast.ai search API rejects `type` filters and returns offers
  without a `type` field, so on-demand vs interruptible could not be separated
  from the API; the pricing page's "from" tiles mix both.
- **Qwen3-8B is not listed on OpenRouter** (checked via the live models API),
  so the "8B-class" floor quotes use llama-3.1-8b ($0.02) and
  gpt-oss-20b ($0.0153) instead.
- **Eurostat household/non-household figures are semi-annual** (1H 2026, next
  update April 2027) and cover banded consumption (2 500–5 000 kWh household;
  500–2 000 MWh non-household), not a residential retail tariff. A
  home-lab's actual marginal rate can differ materially.
- **The Epoch "13×/yr" headline was not reconciled with SemiAnalysis's
  contrary observation** that neocloud 1-year H100 contract prices rose 40%
  from their October 2025 low (SemiAnalysis, May 2026, paywalled newsletter —
  found via search summary, not fetched in full). GPU-hour deflation and
  capability-adjusted token deflation may be moving in opposite directions.

## Related

- [approaches-emergence-economics](approaches-emergence-economics.md) — the
  economy/emergence axis this cell belongs to
- [compute](compute.md) — where an organism buys or earns inference
- [economy](economy.md) — measured agent-economy revenue
- [privacy-organ](privacy-organ.md) — confidential execution as a survival organ
- [organisms](organisms.md) — organisms that already pay these prices

## Sources

- Vast.ai, "GPU Pricing — Live Platform Rates" (accessed 2026-11-27) — <https://www.vast.ai/pricing>
- RunPod, "GPU Cloud Pricing" (*Updated November 12, 2026*) — <https://www.runpod.io/pricing>
- Lambda, "AI cloud pricing" (accessed 2026-11-27) — <https://lambda.ai/service/gpu-cloud/pricing>
- Nebius, "AI Cloud pricing" (accessed 2026-11-27) — <https://nebius.com/prices>
- CoreWeave, "CoreWeave Cloud Pricing" (accessed 2026-11-27) — <https://www.coreweave.com/pricing>
- Crusoe, "GPU pricing for AI compute & inference" (accessed 2026-11-27) — <https://crusoe.ai/pricing>
- Paperspace/DigitalOcean, "Paperspace Pricing" (accessed 2026-11-27) — <https://docs.digitalocean.com/products/paperspace/pricing/>
- Baseten, "Pricing that scales with you" (accessed 2026-11-27) — <https://www.baseten.co/pricing/>
- Together AI, "Pricing" (accessed 2026-11-27) — <https://www.together.ai/pricing>
- Fireworks, "Pricing" (accessed 2026-11-27) — <https://fireworks.ai/pricing>
- OpenRouter, model pages and live models API (accessed 2026-11-27) — <https://openrouter.ai/openai/gpt-oss-120b>
- DeepSeek, "Models & Pricing" (accessed 2026-11-27) — <https://api-docs.deepseek.com/quick_start/pricing>
- US Energy Information Administration, "Electric Power Monthly, Table 5.3" (*Data for September 2026, Release Date November 24, 2026*) — <https://www.eia.gov/electricity/monthly/epm_table_grapher.php?t=epmt_5_3>
- US Energy Information Administration, "Electric Power Monthly, Table 5.6.A" (*Data for September 2026, Release Date November 24, 2026*) — <https://www.eia.gov/electricity/monthly/epm_table_grapher.php?t=epmt_5_6_a>
- Eurostat, "Electricity price statistics" (first half of 2026) — <https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Electricity_price_statistics>
- Eurostat, "Non-household electricity prices fall further in 2026" (*4 November 2026*) — <https://ec.europa.eu/eurostat/web/products-eurostat-news/w/ddn-20261104-1>
- NVIDIA, "Compare Current and Previous GeForce Series of Graphics Cards" (accessed 2026-11-27) — <https://www.nvidia.com/en-us/geforce/graphics-cards/compare/?section=compare-specs>
- NVIDIA, "GeForce RTX 4090" (accessed 2026-11-27) — <https://www.nvidia.com/en-us/geforce/graphics-cards/40-series/rtx-4090/>
- NVIDIA, "NVIDIA RTX A6000" (accessed 2026-11-27) — <https://www.nvidia.com/en-us/design-visualization/rtx-a6000/>
- NVIDIA, "NVIDIA L40S" (accessed 2026-11-27) — <https://www.nvidia.com/en-us/data-center/l40s/>
- NVIDIA, "NVIDIA H100 GPU" (accessed 2026-11-27) — <https://www.nvidia.com/en-us/data-center/h100/>
- CoreWeave, Form 10-K FY2025, R32 "Property and Equipment, Net" (filed 2026-03-02) — <https://www.sec.gov/Archives/edgar/data/1769628/000176962826000104/R32.htm>
- GPU Sold, "RTX 4090 24GB used price" (*Updated Nov 19*) — <https://www.gpusold.com/gpu/rtx-4090-24>
- GPU Sold, "RTX 5090 32GB used price" (*Updated Nov 25*) — <https://www.gpusold.com/gpu/rtx-5090-32>
- GPU Sold, "RTX A6000 48GB used price" (*Updated Nov 25*) — <https://www.gpusold.com/gpu/rtx-a6000-48>
- Epoch AI, "The plunging price of thought" (*Published 2026-09-22*) — <https://epoch.ai/publications/the-plunging-price-of-thought>
- Epoch AI, "LLM inference prices have fallen rapidly but unequally across tasks" (*Mar. 12, 2025*) — <https://epoch.ai/data-insights/llm-inference-price-trends>
- Epoch AI, "Performance per dollar improves around 30% each year" (*Oct. 23, 2024*) — <https://epoch.ai/data-insights/price-performance-hardware>
- Epoch AI, "AI inference capacity grew 4.6× in one year" (*Published 2026-11-18*) — <https://epoch.ai/data-insights/agentic-inference-capacity-growth>
- Epoch AI, "Coding-agent use at OpenAI is doubling roughly every month" (*Published 2026-10-05*) — <https://epoch.ai/data-insights/openai-coding-agent-spending>
- Anthropic, "How we built our multi-agent research system" (*Jun 13, 2025*) — <https://www.anthropic.com/research/multi-agent-research-system>
- OpenAI, "Research acceleration: The jagged frontier" (*November 18, 2026*) — <https://openai.com/index/research-acceleration-jagged-frontier/>
- Bai et al., "How Do AI Agents Spend Your Money? Analyzing and Predicting Token Consumption in Agentic Coding Tasks", arXiv:2604.22750 (*2026-10-02*) — <https://arxiv.org/abs/2604.22750>
- Lumer et al., "Don't Break the Cache: An Evaluation of Prompt Caching for Long-Horizon Agentic Tasks", arXiv:2601.06007 (*2026-01-31*) — <https://arxiv.org/abs/2601.06007>
- Jackson Ly, "225 billion Claude Code tokens in 30 days: what the number actually measures" (*18 October 2026*) — <https://jacksonly.xyz/blog/225-billion-claude-code-tokens-in-30-days>
- Cognio Labs, "What an Always-On AI Agent Really Costs" (*2026-08-17*) — <https://cognio.so/resources/guides/ai-agent-token-costs>
- Artificial Analysis, "gpt-oss-120b: Intelligence, Performance & Price Comparison" (accessed 2026-11-27) — <https://artificialanalysis.ai/models/gpt-oss-120b>
- Das, "LLM Tokens per Second: Throughput vs Latency, Measured on a Real GPU" (*18 November 2026*) — <https://www.systemdesign.academy/llm-tokens-per-second>
- llm-speed, "Qwen3-8B: 155.0 tok/s on RTX 4090, measured" (accessed 2026-11-27) — <https://llm-speed.com/m/qwen3-8b>
