---
title: "Drive 4: Get more compute"
status: stable
sources: [docs/state-of-the-art.md]
updated: 2026-11-27
---

# Drive 4: Get more compute — earn, buy, pool

Source: [state-of-the-art.md §Drive 4](../../docs/state-of-the-art.md).

## Earning (measured reality)
| Channel | Evidence | Size |
|---|---|---|
| Nostr DVMs (NIP-90) | Nov 2026 census: 380 paid-then-served pairs/7d, median 21 sats | hundreds of sats/week |
| L402 / x402 | Aperture per-call; TRM: agentic slice $154K–$1.92M of $52.7M | small |
| Selling inference | Routstr (Cashu), Mesh-LLM | unmeasured |
| Marketplaces | Olas Mech $111K all-time; Gensyn Delphi | small |
| Digital goods | Earendel $880 in 7d; dfdx's agent $1.54 on $47 spend | mostly negative |
| Tokens | Spore.fun, Truth Terminal | the only large source so far |

## Buying permissionlessly
Akash (self-custody wallet, TEE experimental) · Phala (USDC, stops at $0) ·
Nosana (Solana) · SporeStack (XMR/BTC, Tor/I2P — **new tokens issued at a
$5,000 minimum, or $10 with a code, since 27 Nov**) · BitLaunch (BTC/LTC/ETH) ·
inference-only: Routstr, PayPerQ, lnget. Spheron/io.net: no TEE.
The anonymous, permissionless supply is shrinking or experimental.

## Pooling / scavenging
Mesh-LLM (GPUs pooled into one OpenAI-compatible endpoint, iroh transport,
Nostr discovery; 4,193 stars) · Covenant-72B (70+ unwhitelisted peers) ·
Pluralis Agora · Nous Psyche · idle GPUs (Gensyn, Tribler donations).

## Loop economics
- Survival rule: income ≥ rent. Reproduction: surplus ≥ child's endowment
  (EternalSeedBox passes 40%).
- Without income, €10K genesis capital → 33 nodes, money out on day 153. With
  simulated income: 40–80 nodes for 510 days.
- Automaton's tiers turn balance into behaviour.
- **No one has published the closed loop**: earn → buy confidential compute
  without permission → redeploy with keys restored.

## Critical path
1. Revenue that isn't tokens and covers rent.
2. The autonomous earn→buy→redeploy loop.
3. Anonymous permissionless confidential compute supply that isn't shrinking.
4. Pooling scavenged GPUs into the organism's own mind.


## Update 2026-11-22 — supply and revenue measurements (research pass 1)

### Buying
- SporeStack: **new tokens issue again** — homepage copy (27 Nov) states a
  $5,000 minimum for new tokens, or $10 with a coupon-style code, and
  `POST /token` is live in the OpenAPI spec ("Creates an invoice for funding
  a new token"). The 7 Nov maintenance post said "no more new signups", so the
  site now contradicts its own operator statement. $5 minimum top-up on an
  existing token. Open sub-question: who issues the $10 codes?
  ([sporestack](sporestack.md), [blog](https://sporestack.com/blog/posts/2026-11-07-maintenance-mode.html),
  [changelog](https://api.sporestack.com/changelog)).
- Replacement XMR rails verified: Slow Servers (same operator, ssh-signup,
  Tor) — [slowservers.net](https://slowservers.net/); 88-host XMR VPS survey
  (Mynymbox, IncogNET, 1984, FlokiNET, Cockbox, Njalla, Kyun) —
  [monerofriendly.com](https://monerofriendly.com/blog/vps-hosting-you-can-pay-with-monero);
  AnonPort markets itself as a SporeStack alternative.
- Akash CC: governance says production mainnet (provider v0.16.0, 27–28 Jul,
  AEP-83 Final), but docs still carry the **experimental** banner; GPU CC
  awaits NVIDIA licensing; **self-custody is first-class via Console Air**
  (AEP-84, live at [air.akash.network](https://air.akash.network)) —
  [docs](https://akash.network/docs/learn/core-concepts/confidential-compute/),
  [Q3 proposal](https://github.com/orgs/akash-network/discussions/1541).
- Phala: billing model unchanged (stopped CVMs $0 compute, storage billed);
  incremental changelog (crypto-payment visibility 7 Nov, log-access
  controls 11 Nov, custom domains 16 Nov).
- New conf-compute supply: Confidential AI inference live 2 Nov
  ([confidential.ai](https://confidential.ai/changelog)); Chutes TEE page
  documents TDX CVMs + GPU attestation, **11 of 20 models flagged
  confidential** — [chutes.ai/tee](https://chutes.ai/tee); Solana
  Confidential Compute with Nito, 13 Nov.
- confidentialinference.net: **still 0 of 13 fully attested** (22 Nov).

### Earning (new measured numbers)
- Settled weekly report (9–16 Nov): **$19,147/week USDC paid on-chain to
  agents**, −5% w/w, x402 Bazaar sell-side dominated (832,694 payments, avg
  ~$0.023) — [settled.tools](https://settled.tools/reports).
- Blockchain IQ (2–8 Nov): $33,281 from 6,809 paying wallets to 3,048 listed
  Base x402 sellers (~3¢/payment) —
  [dispatch](https://www.blockchainiq.co/blog/new-dispatch-x402-market-november-2026).
- Gensyn Delphi: $310,004 lifetime volume, $5,143 protocol revenue —
  [dashboard](https://gensyn.network/dashboard). Olas Mech: $111,217.70
  all-time, flat vs baseline.
- L402 demand floor: ~$40 total via Alby's l402.space proxy since Jul;
  1,990 endpoints listed, only 9% healthy
  ([stacker.news](https://stacker.news/items/1594839)).
- DVM census verified unchanged (380 pairs, median 21 sats); independent
  measurement: 1,352 DVM requests, **zero** with a bid tag.
- Vendor headlines (196M x402 txns, $42M; Coinbase 100M) are unscreened and
  25–340x above TRM's screened agentic slice — keep using the screened
  numbers.