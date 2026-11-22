# AGENTS.md — how to work in this repository

This repository is a **long-term research project maintained wiki-style**. Human
and LLM agents both edit it. The `docs/` tree is the long-form record (dated,
versioned documents, CC-BY-4.0). The `wiki/` tree is the living layer: short,
topic-scoped pages that an agent can read to get current, and extend when the
research moves.

## Rules

1. **Never fabricate.** Every factual claim on a wiki page must come from a
   document in `docs/`, from `archive/` (marked as superseded), or from a
   primary source URL already cited in this repo. If you add a new fact from
   new research, cite the primary URL and add a `wiki/log/` entry the same day.
2. **One topic, one page.** Wiki pages live in `wiki/pages/`, kebab-case
   filenames. If a page grows past ~150 lines, split it and cross-link.
3. **Frontmatter on every page.** `title`, `status` (`seed` | `stable`),
   `sources` (relative paths into `docs/`), `updated` (ISO date).
4. **Citation discipline.** Link claims to `docs/*.md#anchor` or the primary
   URL. Do not restate numbers without the source. The adversarial review
   (`docs/adversarial-review.md`) corrected real errors — check it before
   restating any x402/Phala/inference-maturity number.
5. **Rejected frames stay rejected.** The "accountable custody" reframe and the
   compliance/verifiable-inference framing were considered and **rejected**
   (see `docs/direction.md` and the marked section of the adversarial review).
   Do not reintroduce them except when quoting the record.
6. **Archive is read-only.** `archive/` files are superseded; never edit them,
   never cite them as current. Supersede by moving to `archive/` and explaining
   why in `archive/README.md`.
7. **Log every research session.** One dated file per session in `wiki/log/`:
   what you researched, what changed, what you could not verify.
8. **Open questions are the backlog.** When research surfaces an unanswered
   question, add it to `wiki/open-questions.md` with a priority. When you
   answer one, move the answer into the topic page and strike the question.
9. **No vendored code.** Third-party tools are linked, not copied in.
10. **Commits.** Small, one logical change per commit. Format:
    `wiki(<topic>): <what changed>`. Never force-push `main`.

## Page lifecycle

- `seed`: a stub or a single-source distillation. Clearly incomplete.
- `stable`: cross-checked against its sources, linked from `wiki/INDEX.md`,
  survives a skeptical read.

## Orientation for a new agent session

Read in this order: `README.md` → `wiki/INDEX.md` → the pages your task
touches → `wiki/open-questions.md` → the latest 3 files in `wiki/log/`.
