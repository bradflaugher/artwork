# AGENTS.md

This repository is a **textual artwork collection**. The primary artifacts are poems — strange ones — committed as plain markdown files. There is no build system, no runtime, no dependencies to install. The repo is the artwork.

## Repo rules

### Poems are first-class pieces, not source code
- Each poem lives in its own file under `poems/`.
- A poem file contains: a title, the body of the poem, and a one-line gloss or epigraph. No exceptions — an untitled, unglossed text file is not finished work.
- Poems are complete and standalone. Do not commit drafts, fragments, or "v2" revisions alongside the original. If a poem must change, edit it in place.
- Do not delete or substantially rewrite a published poem without a reason that would make sense to a curator.

### Curator filenames
- Filenames are `kebab-case-title.md` — lowercase, words separated by hyphens, no spaces, no version numbers, no dates unless the date is part of the title.
- Forbidden: `poem1.md`, `draft_final_v2.md`, `untitled_2026.md`, `something-clean.md`.
- A filename should sound like a title, not a filename. If you would not print it on a book spine, do not commit it.

### No tooling, no scratch files
- Do not add generators, linters, formatters, CI configs, package manifests, or build tooling. The repo ships only text and the license.
- Do not commit scratch files, notes, TODOs, or working drafts to the tracked tree. Keep experiments outside the repo.
- The `.gitignore` is inherited boilerplate; it may be trimmed but does not need to be expanded for artwork.

### License and attribution
- The project is MIT-licensed (see `LICENSE`). Attribution to the copyright holder must remain on every distribution.
- Poems are released under the same MIT terms as the code. Do not add per-file licenses or copyright blocks to poem files — the root `LICENSE` covers them.

### Anthology structure
- `poems/index.md` is the table of contents and the manifesto. Every poem file must be linked from `index.md`; an unlinked poem is a lost poem.
- New poems are grouped into themed **batches**. Add a poem by creating its file and appending a link to the relevant batch section of `index.md`.
- Batch names describe the *flavor of strangeness*, not the date they were written.

### What strangeness means here
- Genuinely strange, not random. Wrong grammar on purpose. Impossible objects. Bureaucratic surrealism. Constraint forms that feel broken. Found-text that has been mutated past recognition.
- Avoid twee whimsy, greeting-card surrealism, and "and then I ate the moon" nonsense. Strangeness should feel earned and slightly uncomfortable.

## Formatting conventions

### Poem layout formatting
- **Title**: Every poem file must start with a level 1 heading (`# Title`).
- **Epigraph/Gloss**: Epigraphs and glosses must be placed at the very end of the poem file, formatted as a blockquote (e.g. `> Epigraph: *text*` or `> Gloss: *text*`).
- **Line endings / paragraphing**: Standard markdown styling is used. Double space or newline for stanza breaks.

## Workflow for agents

1. **Read `README.md`, `LICENSE`, and `poems/index.md` before adding anything.**
2. Pick (or invent) a batch theme. Write poems that fit it.
3. Create one `.md` file per poem under `poems/`, with title, body, and epigraph, following formatting conventions.
4. Update `poems/index.md` with links to every new file.
5. If the anthology warrants it, update `README.md`'s "Now reading" section.
6. Do not commit scratch files, build tooling, or unrelated refactors.
