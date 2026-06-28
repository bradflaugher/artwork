# AGENTS.md

Rules for agents and contributors working in this repo.

## What this repo is

A home for **artwork** — including visual pieces, manifestos, conceptual series, and textual/poetry collections. Not a software project. Treat every change as a curatorial act. There is no build system, no runtime, no dependencies to install. The repo itself is the artwork.

## Core rules

1. **Original work only.** Submit art you created. No reproductions, no unattributed appropriations, no scraped or model-mimicked copies of living artists' signature styles. If you reference an existing work, transform it enough to stand on its own and name the reference.

2. **Art first, code second.** Markdown, images, and text are first-class. Add code only when it *is* the medium. Do not add generators, linters, formatters, CI configs, package manifests, or build tooling. The repo ships only art, text, and the license.

3. **Keep the gallery clean.** Each series lives in its own directory with a manifesto or index. Do not commit scratch files, notes, TODOs, or working drafts to the tracked tree. Keep experiments outside the repo. The `.gitignore` is inherited boilerplate; it may be trimmed but does not need to be expanded for artwork.

4. **Curator filenames.** Filenames are `kebab-case-title.md` (or relevant extensions for images) — lowercase, words separated by hyphens, no spaces, no version numbers, no dates unless the date is part of the title. Forbidden: `poem1.md`, `draft_final_v2.md`, `untitled_2026.md`, `something-clean.md`. A filename should sound like a title, not a filename. If you would not print it on a book spine, do not commit it.

5. **Honor the license.** Everything here is MIT (see `LICENSE`). Contribute with that in mind — your work will be freely shared, modified, and redistributed. Attribution stays; permission is granted. Do not add per-file licenses or copyright blocks.

---

## Visual & Conceptual Art Guidelines (e.g., `unfollow/`)

1. **Subversive intent is the point.** This collection favors work that challenges, unsettles, refuses, or subverts — addictive interfaces, surveillance aesthetics, algorithmic attention, sanitized politeness. Pretty is fine; pretty *and* dangerous is better. Decorative filler belongs elsewhere.

2. **Say what the work means.** Every piece ships with an artist statement or caption. A subversive image without context is just an image. The words are part of the piece.

3. **Small, complete contributions.** One coherent series or piece per change. Finish it — image, statement, index entry — before opening a contribution. No half-installed exhibitions.

---

## Textual & Poem Guidelines (e.g., `poems/`)

### Poems are first-class pieces, not source code
- Each poem lives in its own file under `poems/`.
- A poem file contains: a title, the body of the poem, and a one-line gloss or epigraph. No exceptions — an untitled, unglossed text file is not finished work.
- Poems are complete and standalone. Do not commit drafts, fragments, or "v2" revisions alongside the original. If a poem must change, edit it in place.
- Do not delete or substantially rewrite a published poem without a reason that would make sense to a curator.

### Anthology structure
- `poems/index.md` is the table of contents and the manifesto. Every poem file must be linked from `index.md`; an unlinked poem is a lost poem.
- New poems are grouped into themed **batches**. Add a poem by creating its file and appending a link to the relevant batch section of `index.md`.
- Batch names describe the *flavor of strangeness*, not the date they were written.

### What strangeness means here
- Genuinely strange, not random. Wrong grammar on purpose. Impossible objects. Bureaucratic surrealism. Constraint forms that feel broken. Found-text that has been mutated past recognition.
- Avoid twee whimsy, greeting-card surrealism, and "and then I ate the moon" nonsense. Strangeness should feel earned and slightly uncomfortable.

### Formatting conventions
- **Title**: Every poem file must start with a level 1 heading (`# Title`).
- **Epigraph/Gloss**: Epigraphs and glosses must be placed at the very end of the poem file, formatted as a blockquote (e.g. `> Epigraph: *text*` or `> Gloss: *text*`).
- **Line endings / paragraphing**: Standard markdown styling is used. Double space or newline for stanza breaks.

### Workflow for agents
1. **Read `README.md`, `LICENSE`, and `poems/index.md` before adding anything.**
2. Pick (or invent) a batch theme. Write poems that fit it.
3. Create one `.md` file per poem under `poems/`, with title, body, and epigraph, following formatting conventions.
4. Update `poems/index.md` with links to every new file.
5. If the anthology warrants it, update `README.md`'s "Now reading" section — and bump the poem count there when it changes.
6. Do not commit scratch files, build tooling, or unrelated refactors.

### Loop notes (agent memory)
- **No build or test suite.** Verification is manual curation: `# Title`, stanza body, trailing `> Epigraph:` or `> Gloss:` blockquote, curator filename, index link, anthology voice (strange, not twee).
- **Poem count:** 29 poems (Batch 1: 13, Batch 2: 8, Batch 3: 8). Bump the count in `README.md` "Now reading" when adding a poem; add one epigraph spotlight line for the new piece.
- **Batch fit:** Geography, landscape, and celestial themes (mountains, trees, stars, wind, thunder, rain, weather, rooms) default to **Batch 1 — surreal / liminal** unless the piece is primarily a form, inventory, or procedure — then use Batch 2 or 3. Bureaucratic surrealism in the poem body still belongs in Batch 1 when the strangeness is image-first, not form-first.
- **Authoritative state:** `poems/index.md` is the anthology table of contents. Root-level planning files (e.g. `fix_plan.md`) may be stale; trust the index and working tree over out-of-date plans.
- **Do not commit** iteration scratch files such as `fix_plan.md`.
- **Loop iterations:** Before writing, grep `poems/index.md` and check recent commits — if the mission poem is already linked and spotlighted in `README.md`, skip re-implementation; Ship only persists memory and opens the PR.
- **fix_plan.md workflow:** When all tasks are checked and no `- [ ]` lines remain, the middle-manager loop must append new actionable `- [ ] task` lines before execute/verify loops can proceed. A plan with only `[x]` items stalls the pipeline.
- **Ship verification:** After a themed poem ships, `rg -i <theme> poems/` should hit the poem body and `poems/index.md`; README epigraph spotlight is optional but expected for new pieces.
- **Wind mission (loop 1):** Complete. `the-wind-returns-things-to-the-wrong-sky.md` — Batch 1, courier/misdelivery surrealism (wind returns things to the wrong sky). Pairs thematically with `the-rain-reverses.md` (weather that leaves instead of arrives).
- **Thunder mission (loop 1):** Complete. `the-thunder-arrives-after-the-fact.md` — Batch 1, delayed-causality / bureaucratic weather surrealism (thunder files late after lightning). Pairs with `the-rain-reverses.md` and `the-wind-returns-things-to-the-wrong-sky.md` as a weather trilogy.
- **Rebase gotcha:** `mm/loop-1` on origin may be ahead of local `main`; rebase onto `origin/mm/loop-1` before push (never force-push). Resolve index/README conflicts by keeping all batch links and bumping poem count.
- **Middle-manager branches.** Loop work ships on `mm/loop-N` branches; commit message format: `middle-manager: <mission summary>` (≤72 chars).

### Verification (no build system)
There is no test suite. Before committing a new poem, run structural checks:

```bash
grep '^# ' poems/<slug>.md          # level-1 title present
grep '^> Gloss:\|^> Epigraph:' poems/<slug>.md   # trailing blockquote
grep -c '^- \[' poems/index.md     # link count (must match README poem count)
grep -l '<slug>' poems/index.md README.md
git diff --stat                    # expect only poem file, index.md, README.md
```

Celestial/astronomy and weather poems belong in **Batch 1 — surreal / liminal** (delayed causality, liminal time, misdelivered nature) unless they are procedural/bureaucratic (Batch 3).
