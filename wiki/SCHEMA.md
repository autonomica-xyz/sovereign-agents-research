---
title: Wiki schema — how pages are written, linked and checked
updated: 2026-11-23
---

# Wiki schema

This wiki follows the "LLM wiki" pattern: many small pages, one concept each,
densely cross-linked, every fact dated and sourced, so an agent can load only
the pages a task touches. Hub pages (definition, drives, approaches) give
synthesis; **atomic pages** hold the facts.

Every page takes the organism's view: what helps it survive, avoid being
killed, stay resilient and get more compute. Privacy is a survival organ.
Compliance, regulator-facing verification and operator kill-switches are out of
scope (see [direction](../docs/direction.md)).

## Atomic page template

```markdown
---
title: "Human-readable title"
category: concept | technology | money-rail | compute | organism | research | attack | actor | open-problem | history | legal | fiction | reference
status: seed | stable
sources: [docs/state-of-the-art.md]   # long-form docs this page draws on (may be [])
updated: YYYY-MM-DD
---

# Title

> Two to five line summary: what it is, the most important dated fact,
> and its current state (live, dormant, dead, closed, unverified).

## Details
Dated facts, numbers with their source, uncertainty marked ("self-reported",
"reported", "unverified here").

## How it serves the organism
Why a digital organism would use it (or, for attacks, what it teaches).

## How it fails
How it breaks, who can switch it off, what it leaks. For attacks: what it does
to the organism and the defences.

## Related
[page](page.md) · [page](page.md) · …

## Sources
- Publisher, "Title" (date) — <https://…>
```

### Categories

| Category | Holds |
|---|---|
| concept | Ideas and design patterns (anti-twin quorum, rehydration) |
| technology | Building blocks (TDX, dstack, Nostr, iroh) |
| money-rail | Ways to hold, earn and pay (Lightning, Cashu, x402) |
| compute | Places to get a body or inference (Akash, Phala Cloud, BitLaunch) |
| organism | Agents and agent projects that exist or existed |
| research | Papers and experiments (DGM, RepliBench, Avida) |
| attack | Kill vectors and real incidents |
| actor | People and organisations |
| open-problem | Unsolved problems, file names prefixed `op-` |
| history | Precursors and lineage (cypherpunks, DACs, Plantoid) |
| legal | Legal wrappers seen as survival tools (DAO LLCs, foundations) |
| fiction | Novels and thought experiments used as design references |
| reference | Synthesis and navigation: timeline, comparison matrix, checklist, glossary, reading list, people directory |

## Naming

- kebab-case file names in `wiki/pages/`; the name is the concept, not a
  sentence (`threshold-custody.md`, not `how-to-split-keys.md`).
- Incidents carry a date suffix: `phala-dstack-incident-2026-10.md`.
- Open problems: `op-<short-name>.md`.
- Never rename a page without updating every link (the linter will catch
  stragglers).

## Linking

- Link the first mention of any concept that has a page. Relative links only
  (`[iroh](iroh.md)` within pages, `pages/iroh.md` from `wiki/`).
- Every atomic page links to at least two others in **Related**.
- Every atomic page is listed in [INDEX](INDEX.md) under its category. The
  atomic-page section of the index is generated from frontmatter.

## Facts and sources

- Every fact has a date (event date or "as of" date) and a source URL or a
  `docs/` link. Self-reported numbers say so.
- Mark dead and dormant projects explicitly, with the date of the last sign
  of life.
- No fabricated numbers or quotes. If a claim only appears on X, cite the
  post and say "on X".
- Do not paste internal machine paths, store ids, tokens or private names.

## Ingest process

1. Search primary sources (project docs, repos, papers, incident reports) and
   X; save the URL and date of each claim.
2. Update the existing atomic page if one fits; otherwise create one from the
   template. Keep pages under about 120 lines; split if longer.
3. Add links both ways (new page ↔ the pages it relates to) and update hub
   pages if the synthesis changes.
4. Run `python3 scripts/gen_index.py` to list it in [INDEX](INDEX.md), regenerate [sources](sources.md), add
   unanswered questions to [open-questions](open-questions.md).
5. Write a dated entry in [log/](log/): what was researched, what changed, what
   could not be verified.
6. Run the linter; commit with `wiki(<topic>): <change>`.

## Lint rules

`python3 scripts/wiki_lint.py` checks:

- every relative link in every Markdown file resolves;
- forbidden strings are absent (internal paths and ids, and a short list of
  project-specific banned phrases);
- atomic pages have the four frontmatter fields, a valid category, a `> `
  summary, the required sections, at least one URL or `docs/` link under
  Sources, and an INDEX entry.

Options: `--sources` regenerates [sources.md](sources.md); `--external` checks
that cited URLs respond (some sites block scripts; treat 403/429 as "check by
hand", not dead).

Mermaid diagrams must render with `npx @mermaid-js/mermaid-cli`.
