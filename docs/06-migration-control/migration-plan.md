# Migration Plan — Safe Branch and Repository Consolidation

## Phase A — Preserve and centralize
- Copy common rules and templates into this repository.
- Copy each class audit summary and manifest into `docs/07-audit-evidence/class-XX/`.
- Create class Edition Registers with immutable Page-2 and page-map links.
- Record every existing branch and the unique material in it.
- Keep all original class branches untouched during this phase.

## Phase B — Discover and classify books (book-first)
- Read the complete Active main Git Tree first and count actual books / volumes and all duplicate candidates.
- For each book, identify the exact Class / Subject / Medium / Term / Volume and open its actual Page 2 split to read the printed imprint.
- Compare official source, Page 2, page count, all pages, TOC and book-back question mapping.
- If two copies share the same year / edition imprint, verify 100% content identity before choosing: exact master SHA-256 or all page Blob SHAs plus manifest/order/TOC checks.
- If 100% identical, keep one canonical latest/official copy in Active and do not create an Archive copy for the duplicate (`IDENTICAL_DUPLICATE_NO_ARCHIVE`). If same imprint but content differs, stop for manual review.
- Mark each book `NEW_EDITION` / `LEGACY_EDITION` / `IDENTICAL_DUPLICATE_NO_ARCHIVE` / `SINGLE_CURRENT_EDITION` / `LEGACY_ONLY_RELEASE_PENDING` / `EDITION_UNVERIFIED`.
- No branch name, filename, folder name or page count alone is accepted as evidence of edition freshness.

## Phase C — Book-package migration (small resumable batches)
- Complete the book inventory, Page 2 edition decision and full support-file mapping before moving content. Do not start unrelated TOC, viewer redesign, question correction, answer writing or quiz regeneration before the book split is complete.
- Move/copy one complete book package at a time: page PDFs, manifests, TOC/edition metadata, book-specific questions/answers/quizzes and source references.
- Limit each transfer/commit batch to 200–300 file operations. If one book is larger, divide only that same book into ordered sub-batches; do not switch books until every sub-batch of the current book passes.
- Persist a checkpoint after every successful blob and batch commit. On interruption, inspect the destination tree and skip files whose destination path and Blob SHA already match; retry only missing/failed files.
- Use controlled concurrency and back-off for 403/429 secondary rate limits. Diagnose 422 tree errors before retry; never loop the same failed request.
- Commit and SHA-verify each batch before starting the next. Record source/destination path, Blob SHA, batch range, count and commit SHA.
- Move older books plus their associated historical data into the matching Archive repository. Use copy-first. Verify every book package and all batch counts/checksums before removing source copies from a Migration Branch.
- Promote the selected new/current edition into Active. Keep identical duplicate copies out of Archive; retain only one canonical Active copy.

## Phase D — Cloudflare validation
- Confirm the Pages production branch and build settings for every class.
- Exclude documentation-only paths from deployment triggers where supported.
- Ensure the build output contains only intended web assets and the PDFs required by the viewer.
- Test live production after every class change.

## Phase E — Retire old branches
- Only after all unique files have been copied, all register links work, and production has been tested can a branch be considered for deletion.
- Keep a final branch-to-destination map in this repository.
