# Master Progress — TN Schools Classes 1–12

**Snapshot:** 2026-11-07  
**Status:** Inventory and evidence-centralization in progress. No production book has been replaced and no historical branch has been deleted.

## Class-by-class edition position

| Class | What the repository audit currently shows | Safe interim decision |
|---|---|---|
| 1 | The audit branch contains 6 official 2026 Term-I/II combined books (Tamil+English and Maths+EVS, Tamil/English) that differ from the old main page sets. Term-III official files returned 403 in the 2026-11-04 audit. | New T1/T2 editions are candidates for current production, but the combined-volume TOC/viewer mapping must be checked first. Keep old T3 until official replacement is verified. |
| 2 | The audit branch contains 6 official 2026 Term-I/II combined books. One T1 Tamil+English volume has the same Page-2 imprint as the local copy but 46 pages differ; other new volumes differ by imprint/page count/content. Term-III returned 403 in the audit. | Use the official T1/T2 editions after TOC/viewer mapping. Retain T3 old pages for now. |
| 3 | The audit branch contains official 2026 T1/T2 combined books with different content/page counts from main. T3 distribution was not available in the audit snapshot. | T1/T2 candidates; review combined TOC and viewer paths before production. Retain unreleased T3 material. |
| 4 | Three official 2026 Term-I books are in the audit branch. T1 Tamil+English has the same Page-2 imprint and page count as main, but the full comparison differs. T2/T3 official PDFs returned 403 in the audit. | T1 candidate only after viewer mapping; keep old T2/T3 until verified replacements are available. |
| 5 | Three official 2026 Term-I books are in the audit branch; all differ from main despite some similar/same Page-2 imprint text. T2/T3 official PDFs returned 403 in the audit. | T1 candidate only after viewer mapping; retain old T2/T3 for now. |
| 6 | Five official 2026 Term-I books (Tamil+English, Maths TM/EM, Science+Social TM/EM) are in the audit branch. Several have the same 2018 Page-2 imprint and page count but different complete content. T2/T3 returned 403 in the audit. | T1 candidate only after combined-book TOC/viewer mapping; keep old T2/T3. |
| 7 | Five official 2026 Term-I books are in the audit branch. Maths T1 books have same Page-2 imprint/page count as main but full content differs; other combined books differ too. T2/T3 returned 403 in the audit. | T1 candidate only after viewer mapping; keep old T2/T3. |
| 8 | All 8 official 2026–27 full-year books are in the audit branch. Page counts and some Page-2 imprints match main, but whole-book comparisons are recorded as different. | New full-year books are current-edition candidates; verify page links/subject mapping before switching production. |
| 9 | All 8 books in main match the official 2024 Reprint Page-2 imprint and page counts (2,504 pages total). Full page-by-page content diff is still pending. A separate refresh branch also exists. | Keep main as current for now; do not archive or replace. Complete full-content check before final SAME_VERSION status. |
| 10 | Main has 8 annual books. Tamil is proven by official master SHA-256/MD5 match. Science/Social official split sets (1,432 pages) are on the official-version-updates branch but not fully compared with main. English and Maths remain pending. Content branches contain recent Tamil answer/quiz work. | Keep main production unchanged. Do not merge edition or content branches wholesale; reconcile unique question/answer work and compare science/social pages first. |
| 11 | Audit records 4 main books as newer 2025 Revised, 4 as matching 2024 Reprint. 23 official update sets and 1 unresolved Chemistry EM Vol-1 mapping are on the official-version-updates branch (7,832 split pages). Full page-by-page diff against main is pending. | Keep main and update branch intact. Do not treat split validation as full content equivalence; resolve Chemistry EM Vol-1 API ambiguity. |
| 12 | Audit records 32 books on main as matching 2024 Reprint imprint/page count. Physics EM Vol-1 and Chemistry EM Vol-1 differ from main and are stored as 648 official split pages on the update branch. Full page-by-page diff against main is pending. | Keep main and update branch intact until full page comparison and viewer mapping are complete. |

## Evidence and verification limits

- Existing audit manifests contain Page-2 imprint text, official URL, local Page-2 text, page counts, split paths, and comparison statuses for many classes.
- Page-2 PDF links will be recorded per book in the class edition registers. The PDF viewer/screenshot interface was not available for direct visual screenshots in this workspace, so the Page-2 text currently cited here is the extracted audit-manifest evidence, not a claim that each PDF was visually opened during this consolidation.
- Page-2 imprint alone is not an edition identity check. Some books have matching imprint/page count but different content. Full-page comparison, TOC and book-back mapping remain mandatory.
- The audit manifests largely reflect evidence snapshots from 2026-11-04 to 2026-11-05. Current official API status should be refreshed before final sign-off, especially for books previously returning HTTP 403.

## What has been done in the common repository

- Central README and repository map added.
- Common blueprint, Step 1–3 Book-back workflow and edition verification rules copied from class repositories.
- Branch inventory recorded; no branches removed.
- Cloudflare safe deployment policy documented; Cloudflare dashboard settings have not been changed.
- Individual class audit summaries/manifests and precise Page-2 link registers are being copied and indexed.

## Production safety state

**No class main branch book files were changed by this consolidation. No Archive repository content was overwritten. No branch was merged or deleted.**


## Chat continuation — live repository consolidation (2026-11-07, 18:30 IST)

### Completed in this continuation

- Re-queried the live branch lists for all 12 current class repositories and exhausted each branch-search continuation. The observed inventory is 12 `main` branches plus 22 non-main branches (34 current-class branches total). Class 10 has seven non-main branches; Classes 9, 11 and 12 have two, two and three respectively. The Common repository currently has only `main`.
- Updated [branch inventory](../06-migration-control/branch-inventory.md) with the live branch snapshot (commit `cf72d4d78bb18e19f7116c02f35544c0595b01f4`).
- Copied the canonical [SCERT Class-wise Edition Verification Blueprint](../01-blueprint/SCERT_CLASSWISE_EDITION_VERIFICATION_BLUEPRINT.md) into Common from the Class 10 repository; the original source remains in Class 10.
- Copied the shared cross-class audit reports, legacy working blueprint and global CSV manifests from the Class 10 working branch into [Common audit evidence](../07-audit-evidence/README.md). These are retained as dated historical evidence, not final edition decisions.
- Copied class-specific 2026–27 audit manifests and summaries into each corresponding current repository under `docs/edition-audit/2026-27/` for Classes 1–12. Added a README pointer in each class repository. The original working branches remain unchanged.
- Added the Common audit evidence index and linked it from the Common repository README.

### Not yet completed / safety holds

- No textbook PDF/page assets, `pages.json`, viewer routing, Book-back questions, answers or quiz content were moved or replaced in this continuation.
- No branch was merged or deleted. All original audit/content branches remain intact.
- Page-2 imprint text is available in the existing manifests and direct Page-2 PDF links are recorded in the class registers where already prepared. A fresh visual review of every Page-2 PDF and complete per-book register consolidation is still pending; extracted manifest text must not be represented as a new visual inspection.
- Full-book comparisons, TOC boundaries, subject mapping, Book-back alignment and production viewer checks remain mandatory before CURRENT/ARCHIVE decisions.
- Cloudflare deployment policy is documented, but the Cloudflare dashboard settings have not been inspected or changed. Common remains documentation-only and is not a Pages production source.

**Next safe step:** finish the unified per-book register (Classes 1–12) with immutable commit links to each full page set, Page-2 split PDF, page map, official source, imprint, page count and comparison status; then review class-specific remaining documents and Cloudflare settings before any production migration.


### Consolidation continuation — master register and deployment review (2026-11-07)

- Created [MASTER CROSS-VERIFICATION INDEX](../03-edition-register/MASTER_CROSS_VERIFICATION_INDEX.md) in Common. It embeds the individual registers for Classes 1–12 and currently consolidates **124 book / volume / medium rows**, with direct Page-2, official PDF and GitHub evidence links.
- Created/normalized the Class 7–12 registers. Corrected malformed Markdown links in Classes 1–6 so the existing-main Page-2 proofs are clickable.
- Verified that representative Page-2 PDF paths exist in the relevant branches for Classes 1, 2, 6, 7, 8, 9, 10, 11 and 12 using GitHub file retrieval. This confirms the linked files exist; it is **not** a claim that every page has been visually reviewed in this pass.
- Copied the class-specific audit manifests / summaries for Classes 1–12 into each class repository's `main/docs/edition-audit/2026-27/` and added a class-local navigation README. The original working branches remain unchanged.
- Added the canonical cross-class blueprint, dated global audit snapshots, and a Common evidence index to `tn-schools-project`. Shared files were copied from the Class 10 work branch; source originals were retained.
- Inspected the GitHub Actions workflows on Classes 9–12. The observed refresh/update workflows target their named refresh/audit branches; Class 10's manual edition-sync defaults to `feature/scert-edition-pilot`; Class 10 Page-2 preview uploads a temporary Actions artifact. No direct Cloudflare deployment API call or automatic push to `main` was found in the inspected workflows.
- Updated [Cloudflare deployment policy](../04-quality-control/CLOUDFLARE_DEPLOYMENT_POLICY.md) with these findings and the remaining dashboard checks.

### Current verified boundary

- **Page-2 link existence:** representative direct GitHub PDF paths were checked successfully.
- **Page-2 visual confirmation:** not yet completed for every registered book. Manifest imprint strings are extracted evidence and must not be described as fresh visual inspection.
- **Edition decision:** no new global CURRENT/ARCHIVE decisions have been made. Classes 10–12 include explicit pending, legacy/newer-main and API-mapping cases; the register preserves those statuses.
- **Cloudflare:** GitHub workflow behavior is partly understood, but production branch / output directory / preview policy / build watch paths remain dashboard-only settings and are unverified. No deployment setting or production book asset was changed.
- **Branch cleanup:** no non-main branch has been deleted or merged. Document migration is currently additive and verified; remaining branch-specific evidence still needs classification before any branch can be retired.


- Finalized and refreshed the single [MASTER CROSS-VERIFICATION INDEX](../03-edition-register/MASTER_CROSS_VERIFICATION_INDEX.md) after correcting the Class 11 volume-specific links and normalizing Class 7–9 register paths. Current index commit: `fac63c446a3413f905b175f18055defccae481f6`.
- Corrected the live branch count in [branch inventory](../06-migration-control/branch-inventory.md): 12 main + 22 non-main = 34 current-class branches. No branch deletion or merge was performed.
- Added a link from each Class 1–12 repository's local audit README back to its section in the Common master index.
