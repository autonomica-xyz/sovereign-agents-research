---
title: "Tribler superorganism-experiment review"
status: stable
sources: [docs/superorganism-review.md]
updated: 2026-11-24
---

# superorganism-experiment: deep-dive review

Source: [superorganism-review.md](../../docs/superorganism-review.md) — full
component/stack analysis, works-vs-stubs table, security section and the L0–L5
mapping live there.

- EternalSeedBox nodes renew their lease, spawn a child, or sweep funds to a
  healthier peer. The paper's simulation decides every 12 h; the code default
  is every 6 h (`DECISION_INTERVAL` 21600 s). The simulation had 268 births
  and 190 deaths over 510 days, with a heritable caution trait. The code is
  checked parameter by parameter in [eternalseedbox](eternalseedbox.md).
- Mycelium variant: takes donated GPUs, serves Mesh-LLM-style inference.
- Weak points:
  - SporeStack, the only hosting rail, closed to new signups on 7 Nov 2026.
  - Every node pulls one GitHub repo every 60 s.
  - No real income was demonstrated.
  - The failsafe sends a dying colony's coins to the operator's cold wallet.
  - The README calls the project "under direct human control".
- Upstream: `Tribler/superorganism-experiment` (last push 5 Jul 2026), led by
  [johan-pouwelse](johan-pouwelse.md). Its 2017–2020 ancestor is
  [dollynator](dollynator.md).
- Detailed review verdicts: [§3 works vs stubs](../../docs/superorganism-review.md),
  [§6 mapping to full sovereignty](../../docs/superorganism-review.md),
  [§8 next steps](../../docs/superorganism-review.md).

