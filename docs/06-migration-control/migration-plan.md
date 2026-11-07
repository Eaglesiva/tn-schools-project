# Migration Plan — Safe Branch and Repository Consolidation

## Phase A — Preserve and centralize
- Copy common rules and templates into this repository.
- Copy each class audit summary and manifest into `docs/07-audit-evidence/class-XX/`.
- Create class Edition Registers with immutable Page-2 and page-map links.
- Record every existing branch and the unique material in it.
- Keep all original class branches untouched during this phase.

## Phase B — Classify books
- For every book, compare official source, Page 2, page count, all pages, TOC and question mapping.
- Mark each book CURRENT / ARCHIVE / PENDING / BLOCKED.
- No branch name alone is accepted as evidence of edition freshness.

## Phase C — Prepare production main
- Copy selected official edition pages into the exact production paths expected by the viewer.
- Update only the required `pages.json` and index/viewer routes.
- Preserve current quiz, answer and question IDs where they still apply.
- Move older books plus their associated historical data into the matching Archive repository.
- Use a copy-first approach. Verify file counts, checksums, page order and links before removing any source copies.

## Phase D — Cloudflare validation
- Confirm the Pages production branch and build settings for every class.
- Exclude documentation-only paths from deployment triggers where supported.
- Ensure the build output contains only intended web assets and the PDFs required by the viewer.
- Test live production after every class change.

## Phase E — Retire old branches
- Only after all unique files have been copied, all register links work, and production has been tested can a branch be considered for deletion.
- Keep a final branch-to-destination map in this repository.
