# Archive Repository Policy — TN Samacheer Kalvi Classes 1–12

**Status:** Active Implementation in Progress (Class-by-Class Sequential Execution).  
- **Class 01 Archive (`tn-class-01-archive`):** ✅ **100% PRODUCTION ARCHIVED & LOCKED** on `main` branch (SHA: [`1a38a4c6d8dcaba7b4e1b511a089656fca4260d7`](https://github.com/Eaglesiva/tn-class-01-archive/commit/1a38a4c6d8dcaba7b4e1b511a089656fca4260d7)) — 1,189 legacy files preserved under `legacy-2018-2022/`.  
- **Class 02 Archive (`tn-class-02-archive`):** ✅ **100% PRODUCTION ARCHIVED & LOCKED** on `main` branch (SHA: [`8c0f7397f6d6e8033d399ed88cb49fa725083401`](https://github.com/Eaglesiva/tn-class-02-archive/commit/8c0f7397f6d6e8033d399ed88cb49fa725083401)) — 1,176 legacy files preserved under `legacy-2018-2022/`.  
- **Classes 03–12 Archives (`tn-class-03-archive` to `tn-class-12-archive`):** Maintained in clean baseline state; strictly gated under sequential Step 0–8 migration approval protocol.  
**Scope:** `Eaglesiva/tn-class-01-archive` through `tn-class-12-archive`.

## Purpose

Archive repositories hold only superseded or withdrawn textbook editions and their provenance. They are not a second production source and must never replace the current class repository.

## Archive approval gate

A book may be copied into its class archive repository only after the Common Master Cross-Verification Index records an explicit `ARCHIVE_APPROVED` decision and all of the following are true:

1. A replacement edition is confirmed from an official SCERT / textbook-corporation source.
2. The replacement's Page 2 imprint and release details are checked.
3. The complete book is compared (page count, text/content, TOC, lesson boundaries and Book-back material).
4. The replacement is present in the class repository and its `pages.json`, `edition.json`, `toc.json` and viewer routing have passed tests.
5. Direct links and stable book / edition IDs are recorded in the master index.
6. The user approves the migration.

A Page-2 imprint difference, equal page count, or an old publication year alone is not sufficient to archive a book.

## What to preserve for each archived edition

- Original source PDF or page-split PDFs, without recompression or content alteration.
- Page-2 PDF and official source URL.
- Stable class / subject / medium / term / volume / edition ID.
- `pages.json`, `edition.json`, `toc.json` and any routing metadata needed to reproduce the old book.
- Official source URL, retrieval date, release notice, Page-2 imprint transcription and a visual Page-2 proof.
- Original PDF SHA-256 and MD5 hashes where available.
- Book-back / question-source links and the related audit manifest.
- A short archive README explaining why the edition was superseded and which edition replaced it.

## Separation rules

- Shared project plans, cross-class audit records and common policies belong in `tn-schools-project`.
- Class-specific audit reports and workflows belong in the matching `tn-class-XX` repository.
- Current production book/page assets remain in the matching `tn-class-XX` repository.
- Only approved superseded textbook editions move to `tn-class-XX-archive`.
- Do not copy the entire current repository into the archive.
- Do not delete or rename the original source until the archive copy and all links are verified.

## Cloudflare

Archive repositories should not be configured as Cloudflare Pages production sources. The actual Cloudflare dashboard settings have not yet been inspected; verify that no archive repository is connected to a Pages project before placing content there.
