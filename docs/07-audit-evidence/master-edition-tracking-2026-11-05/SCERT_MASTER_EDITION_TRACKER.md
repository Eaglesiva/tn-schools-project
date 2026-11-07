# SCERT Master Edition Tracker — 2026–27

**Status:** Catalog Reconciliation & Post-Refresh Harmonization Completed (165 in-scope State Board records tracked; 124 accessible / 41 CDN 403s: 16 officially released Term-II recovery pending, 25 Term-III unconfirmed; 38 books / 11,760 pages refreshed directly from official source on production main; 30 cloud-updated editions / 9,912 split pages on update branches)  
**Last consolidated:** 2026-11-05 (Asia/Kolkata)  
**Class 1–8 API snapshot date:** 2026-11-04  
**Class 9–12 API snapshot date:** 2026-11-05  
**Temporary canonical home:** Eaglesiva/tn-class-10, branch `scert/master-edition-tracking`

This repository document is the shared navigation and normalized index. Per-class raw API snapshots, detailed manifests and page-split evidence remain in their respective class repositories. Do not create duplicate class reports where a verified remote report already exists.

## 1. Shared files

- [Master Edition Index CSV — 165 in-scope records, Classes 1–12](./SCERT_MASTER_EDITION_INDEX.csv)
- [Final Master Audit Status — Mutually Exclusive Metrics & Reconciled Register](./FINAL_MASTER_AUDIT_STATUS.md)
- [Local vs GitHub Artifact Inventory](./LOCAL_VS_GITHUB_ARTIFACT_INVENTORY.md)
- [Class 9 audit instructions (completed/archive)](./NEXT_AUDIT_CLASS_09_TA.md)
- [Class 10 audit summary](https://github.com/Eaglesiva/tn-class-10/blob/scert/class-10/audit-2026-27/docs/class_10_audit_summary.md)
- [Class 10 audit manifest](https://github.com/Eaglesiva/tn-class-10/blob/scert/class-10/audit-2026-27/docs/class_10_2026_27_audit_manifest.csv)
- [Class 11 audit summary](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/audit-2026-27/docs/class_11_audit_summary.md)
- [Class 11 audit manifest](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/audit-2026-27/docs/class_11_2026_27_audit_manifest.csv)
- [Class 12 audit summary](https://github.com/Eaglesiva/tn-class-12/blob/scert/class-12/audit-2026-27/docs/class_12_audit_summary.md)
- [Class 12 audit manifest](https://github.com/Eaglesiva/tn-class-12/blob/scert/class-12/audit-2026-27/docs/class_12_2026_27_audit_manifest.csv)
- [Canonical verification blueprint](https://github.com/Eaglesiva/tn-class-10/blob/main/docs/SCERT_CLASSWISE_EDITION_VERIFICATION_BLUEPRINT.md)

This documentation branch was created from the Class 10 repository. It does not modify production code, book files, viewer routing or the live site.

## 2. Consolidated Class 1–8 status

The class audit manifests contain 83 in-scope State Board Tamil/English academic records. Across the same snapshots, Classes 1–8 have 289 total API records, including minority-language, CBSE, supplementary and teacher-resource entries that are excluded from this core register.

| Class | All API records | In-scope | Official GET 200 | Official GET 403 | Pages in GET-200 master PDFs | Audit branch |
|---:|---:|---:|---:|---:|---:|---|
| 1 | 34 | 9 | 6 | 3 | 848 | scert/class-01/audit-2026-27-term1-vol1 |
| 2 | 34 | 9 | 6 | 3 | 824 | scert/class-02/audit-2026-27 |
| 3 | 35 | 9 | 6 | 3 | 1,016 | scert/class-03/audit-2026-27 |
| 4 | 30 | 9 | 3 | 6 | 472 | scert/class-04/audit-2026-27 |
| 5 | 30 | 9 | 3 | 6 | 544 | scert/class-05/audit-2026-27 |
| 6 | 49 | 15 | 5 | 10 | 864 | scert/class-06/audit-2026-27 |
| 7 | 49 | 15 | 5 | 10 | 880 | scert/class-07/audit-2026-27 |
| 8 | 28 | 8 | 8 | 0 | 2,208 | scert/class-08/audit-2026-27 |
| **Total** | **289** | **83** | **42** | **41** | **7,656** | **8 class audit branches** |

The 7,656 figure is the sum of official master-PDF page counts in 42 GET-200 records. It is not the printed-page total and does not, on its own, prove content equivalence with the existing GitHub copy.

## 3. Critical HTTP 403 interpretation

HTTP 403 is a retrieval result, not a publication decision.

- Classes 1–3: the three Term-III State Board API records returned 403 in the 2026-11-04 audit. The sales notices checked announce Term-I and Term-II. The official 2026–2027 price list (`PRICELIST.pdf`) covers only Term-I and Term-II, and does not list Term-III. These records remain CDN_UNAVAILABLE_AT_CHECK / RELEASE_STATUS_UNCONFIRMED.
- Classes 4–7: Term-II and Term-III URLs returned 403. Term-II sales for Classes 1–7 were officially announced from 22-09-2026. Therefore a Class 4–7 Term-II 403 is a CDN/URL access problem, not evidence that the books were not released.
- Term-III: the API records exist, but the current 2026–27 sales notices checked do not give a Term-III release date. Keep the state unconfirmed until an official notice or accessible official PDF establishes it.
- Class 8: all eight in-scope annual textbook URLs returned GET 200 in the audit manifest.

Official sources:
- [Textbook Corporation — 2026–27 sale notices](https://www.textbookcorp.in/schools)
- [Textbook Corporation — textbook price list](https://textbookcorp.in/textbook/schools/books)
- [SCERT official textbook listing](https://tnschools.gov.in/scert-textbook)
- [Official SCERT listing API](https://emis3.tnschools.gov.in/api/get_scert_books)

## 4. Academic year versus printed edition

Keep four separate facts for every book:

1. Academic/distribution year (for this register: 2026–27).
2. Printed first edition, revised edition or reprint, extracted from the actual book, usually page 2.
3. Date checked and source API record.
4. Exact GitHub stored edition: repository, branch and immutable edition path.

A book distributed in 2026–27 may still show a printed imprint such as First Edition 2018/2019 or Reprint 2024. This does not automatically mean the book is obsolete. Do not label every 2026–27 download as a 2026 printed edition or Reprint 2024.

The CSV preserves the raw page-2 text. IMAGE_ONLY_OR_NO_TEXT means the imprint has not been read from the image and needs visual inspection. An extracted text fragment also needs interpretation before assigning a printed year.

## 5. Existing class audit reports — do not recreate

Classes 1–8 already have separate GitHub audit branches. Each contains a class summary, audit manifest CSV, official API snapshot JSON and an official_editions directory.

| Class | Summary | Manifest | API snapshot |
|---:|---|---|---|
| 1 | [summary](https://github.com/Eaglesiva/tn-class-01/blob/scert/class-01/audit-2026-27-term1-vol1/class_01_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-01/blob/scert/class-01/audit-2026-27-term1-vol1/class_01_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-01/blob/scert/class-01/audit-2026-27-term1-vol1/class_01_official_api_snapshot.json) |
| 2 | [summary](https://github.com/Eaglesiva/tn-class-02/blob/scert/class-02/audit-2026-27/class_02_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-02/blob/scert/class-02/audit-2026-27/class_02_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-02/blob/scert/class-02/audit-2026-27/class_02_official_api_snapshot.json) |
| 3 | [summary](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/class_03_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/class_03_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/class_03_official_api_snapshot.json) |
| 4 | [summary](https://github.com/Eaglesiva/tn-class-04/blob/scert/class-04/audit-2026-27/class_04_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-04/blob/scert/class-04/audit-2026-27/class_04_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-04/blob/scert/class-04/audit-2026-27/class_04_official_api_snapshot.json) |
| 5 | [summary](https://github.com/Eaglesiva/tn-class-05/blob/scert/class-05/audit-2026-27/class_05_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-05/blob/scert/class-05/audit-2026-27/class_05_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-05/blob/scert/class-05/audit-2026-27/class_05_official_api_snapshot.json) |
| 6 | [summary](https://github.com/Eaglesiva/tn-class-06/blob/scert/class-06/audit-2026-27/class_06_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-06/blob/scert/class-06/audit-2026-27/class_06_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-06/blob/scert/class-06/audit-2026-27/class_06_official_api_snapshot.json) |
| 7 | [summary](https://github.com/Eaglesiva/tn-class-07/blob/scert/class-07/audit-2026-27/class_07_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-07/blob/scert/class-07/audit-2026-27/class_07_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-07/blob/scert/class-07/audit-2026-27/class_07_official_api_snapshot.json) |
| 8 | [summary](https://github.com/Eaglesiva/tn-class-08/blob/scert/class-08/audit-2026-27/class_08_audit_summary.md) | [CSV](https://github.com/Eaglesiva/tn-class-08/blob/scert/class-08/audit-2026-27/class_08_2026_27_audit_manifest.csv) | [JSON](https://github.com/Eaglesiva/tn-class-08/blob/scert/class-08/audit-2026-27/class_08_official_api_snapshot.json) |

## 6. Status of Classes 9, 10, 11, and 12

### Class 9 (8 records — 2,504 pages)
- **Status**: 5 Direct Master Refreshed on Main (1,664p) / 3 Layer 4 Pilot Verified (840p)
- **Production Main Tip Commit**: [`d6fc546d`](https://github.com/Eaglesiva/tn-class-09/commit/d6fc546d58aab5f520c5cfbebddb2a829ce86bae) (Mathematics EM, Science TM, Science EM, Social Science TM, Social Science EM)
- **Audit Branch**: [`scert/class-09/audit-2026-27`](https://github.com/Eaglesiva/tn-class-09/tree/scert/class-09/audit-2026-27)
- **Breakdown**:
  - **Refreshed on Main (5 books - 1,664p)**: Maths EM (328p), Science TM (336p), Science EM (328p), Social Science TM (344p), Social Science EM (328p) refreshed in-place from 2026–27 masters across 125 contiguous subdirectories.
  - **Layer 4 Pilot Verified (3 books - 840p)**: English (224p, commit `a2c6840f`), Tamil (272p, commit `6b28a78d`), Maths TM (344p, commit `86f68c34`) verified text-equivalent.

### Class 10 (8 records — 2,624 pages)
- **Status**: 1 Direct Master Refreshed on Main (224p) / 1 Exact Master SHA Match (248p) / 2 Confirmed GitHub Is Newer (720p) / 4 Stored Updates (1,432p)
- **Production Main Tip Commit**: [`22f176e2`](https://github.com/Eaglesiva/tn-class-10/commit/22f176e29b3e92be4ff6a110ac8285a1ce371765) (English 224p in-place refreshed)
- **Audit Branch**: [`scert/class-10/audit-2026-27`](https://github.com/Eaglesiva/tn-class-10/tree/scert/class-10/audit-2026-27)
- **Update Branch**: [`scert/class-10/official-version-updates`](https://github.com/Eaglesiva/tn-class-10/tree/scert/class-10/official-version-updates) (1,432 split pages in unit folders)
- **Breakdown**:
  - **English (224p)**: `OFFICIAL_SOURCE_REFRESHED` (Refreshed in-place on production `main` across 22 contiguous subdirectories).
  - **Tamil (248p)**: `EXACT_MASTER_SHA256_MATCH` (Bit-for-bit SHA-256 match on `main`).
  - **Maths TM (368p) & EM (352p)**: `CONFIRMED_GITHUB_IS_NEWER` (GitHub main holds 2025 Revised Edition with InDesign Dec 2024 compilation & helplines 1098/14417; SCERT portal master is 2024 reprint with InDesign Dec 2023. Verified curriculum-equivalent across all 720 pages; retaining GitHub newer edition on main).
  - **Science TM (360p), Science EM (360p), Social TM (368p), Social EM (344p)**: `VERSION_DIFFERENT; OFFICIAL_SPLIT_STORED_IN_UPDATE_BRANCH` (1,432 pages stored on update branch).

### Class 11 (32 records — 10,288 pages)
- **Status**: 4 Same Version (1,304p) / 4 GitHub Newer (1,152p) / 23 Stored Updates (7,528p) / 1 API Mapping Unresolved (304p)
- **Audit Branch**: [`scert/class-11/audit-2026-27`](https://github.com/Eaglesiva/tn-class-11/tree/scert/class-11/audit-2026-27)
- **Update Branch**: [`scert/class-11/official-version-updates`](https://github.com/Eaglesiva/tn-class-11/tree/scert/class-11/official-version-updates) (24 edition directories, 7,832 pages)
- **Breakdown**:
  - **GitHub Is Newer (4 books - 1,152p)**: Tamil (176p), Maths TM Vol 1 (320p), Maths TM Vol 2 (288p), Maths EM Vol 1 (368p) — preserved on `main`.
  - **Same Version (4 books - 1,304p)**: Maths EM Vol 2 (288p), History TM (352p), Geography TM (336p), Political Science TM (328p) — preserved on `main`.
  - **Official Edition Updates (23 books - 7,528p)**: Stored as 1-page PDFs on branch `scert/class-11/official-version-updates`.
  - **API Mapping Unresolved (1 book - 304p)**: Chemistry EM Vol 1 (SCERT API duplicated Vol 2 URL; GitHub update branch holds 304 split pages with genuine Vol 1 source URL; preserved intact without deletion).
- **Source Verification (Layer 1)**: All 32/32 books confirmed `GET_200` and `HEAD_200` with byte-exact Content-Length and ETag captured via HTTP HEAD; Master PDF SHA-256 explicitly recorded as `NOT_CAPTURED` per Zero Local Download policy.
- **Split Validation (Layer 3)**: All 24 stored edition folders (7,832 pages) verified directly from remote tree (`c1a58225`), strictly sequential from `page_001.pdf` to `page_xxx.pdf`, 0 gaps, 0 duplicates, with all four manifests present (`edition.json`, `edition.md`, `manifest.json`, `pages.json`).

### Class 12 (34 records — 10,520 pages)
- **Status**: 32 Direct Master Refreshed on Main (9,872p) / 2 Stored Updates (648p)
- **Production Main Tip Commit**: [`c15e34ad`](https://github.com/Eaglesiva/tn-class-12/commit/c15e34ad9ca2f53ccd020b2625995d2c20aaf952) (All 32 books refreshed in-place from 2026-27 master)
- **Audit Branch**: [`scert/class-12/audit-2026-27`](https://github.com/Eaglesiva/tn-class-12/tree/scert/class-12/audit-2026-27)
- **Update Branch**: [`scert/class-12/official-version-updates`](https://github.com/Eaglesiva/tn-class-12/tree/scert/class-12/official-version-updates) (2 edition directories, 648 pages)
- **GitHub Main Volume Mapping**:
  - Physics TM (664p): Vol-I = 352p, Vol-II = 312p
  - Physics EM (648p): Vol-I = 352p (update branch), Vol-II = 296p (main)
  - Chemistry TM (672p): Vol-I = 328p, Vol-II = 344p
  - Chemistry EM (624p): Vol-I = 296p (update branch), Vol-II = 328p (main)
- **Breakdown**:
  - **Refreshed on Main (32 books - 9,872p)**: All 32 books in-place refreshed and serving live on `main` across 445 contiguous subdirectories.
  - **Official Edition Updates (2 books - 648p)**: Stored as 1-page PDFs on branch `scert/class-12/official-version-updates`:
    - Physics EM Vol 1: 352 pages (`physics_em/editions/2026-27-scert-official/vol1/`)
    - Chemistry EM Vol 1: 296 pages (`chemistry_em/editions/2026-27-scert-official/vol1/`)
- **Source Verification (Layer 1)**: All 34/34 books confirmed `GET_200` and `HEAD_200` with byte-exact Content-Length and ETag captured via HTTP HEAD; Master PDF SHA-256 recorded as `NOT_CAPTURED` per Zero Local Download policy.
- **Split Validation (Layer 3)**: Both stored edition folders (648 pages) verified directly from remote tree (`4d5cf835`), strictly sequential 1-352 and 1-296, 0 gaps, 0 duplicates, with all four manifests present.

---

## 7. Master Index Summary Table (Classes 1–12 Reconciled)

| Class | API Subject Groups | Nested Academic Entries | In-Scope State Board Books | Verified Stored Pages on Update Branches | Catalog Audit Status |
| :---: | :---: | :---: | :---: | :--- |
| **1** | 34 | 9 | 0 | Audit complete (`scert/class-01/audit-2026-27-term1-vol1`) |
| **2** | 34 | 9 | 0 | Audit complete (`scert/class-02/audit-2026-27`) |
| **3** | 35 | 9 | 0 | Audit complete (`scert/class-03/audit-2026-27`) |
| **4** | 30 | 9 | 0 | Audit complete (`scert/class-04/audit-2026-27`) |
| **5** | 30 | 9 | 0 | Audit complete (`scert/class-05/audit-2026-27`) |
| **6** | 49 | 15 | 0 | Audit complete (`scert/class-06/audit-2026-27`) |
| **7** | 49 | 15 | 0 | Audit complete (`scert/class-07/audit-2026-27`) |
| **8** | 28 | 8 | 0 | Audit complete (`scert/class-08/audit-2026-27`) |
| **9** | 28 | 8 | 0 | 5 Refreshed on Main (1,664p) / 3 Pilot Verified (840p) |
| **10** | 32 | 8 | 1,432 | 1 Refreshed on Main (224p) / 1 SHA Match (248p) / 2 Confirmed Newer (720p) / 4 Stored Updates (1,432p) |
| **11** | 73 (groups) | 136 (nested) | 32 | 7,832* | 4 Same (1,304p) / 4 Newer (1,152p) / 23 Stored Updates (7,528p) / 1 Mapping Unresolved (304p) |
| **12** | 73 (groups) | 136 (nested) | 34 | 648 | 32 Refreshed on Main (9,872p) / 2 Stored Updates (648p) |
| **Total** | **495 (groups)** | — | **165** | **9,912** | **165 rows synchronized in Master Edition Index CSV (33,696 known official master pages across 124 measured books / 33,592 split pages; 41 books unmeasured)** |

---

## 8. Status vocabulary

- `API_LISTED` — exact official API record exists.
- `SALE_ANNOUNCED` — current official notice covers that class/term/year.
- `CDN_HTTP_200` — official URL returned a successful PDF response.
- `CDN_HTTP_403` — URL returned 403 at check time; do not infer publication status from this alone.
- `PRINT_IMPRINT_TEXT_EXTRACTED` — page-2 text extracted; interpretation still required.
- `PRINT_IMPRINT_IMAGE_ONLY` — page 2 needs visual inspection before recording imprint.
- `AUDIT_BRANCH_SPLIT_VALIDATED` — audit manifest and split-validation artifact report structural validation.
- `TOC_MAPPING_PENDING` — combined volume still needs verified subject/unit boundaries before viewer routing.
- `GITHUB_MAIN_NOT_UPDATED` — files exist on audit branch only; this does not mean production main or live site changed.
- `GITHUB_MISSING` — use only after checking correct repository, branch, subject/medium/term mapping and page manifests.
- `OFFICIAL_NOT_IN_API` — use only after checking a refreshed official API snapshot.
- `RELEASE_STATUS_UNCONFIRMED` — official record exists but release timing/publication is not established by notices checked.
- `MANUAL_REVIEW_REQUIRED` — evidence is incomplete, ambiguous or contradictory.
- `API_MAPPING_UNRESOLVED` — official API record has duplicate or ambiguous URL; preserved with verified branch split data pending official fix.
- `HEAD_200` — HTTP HEAD query confirmed resource accessibility, Content-Length, and ETag without downloading payload.

## 9. Shared update rules

1. Before editing, fetch the latest `scert/master-edition-tracking` branch.
2. Work class-by-class; preserve exact API record, filename, URL, term, medium and timestamp.
3. Keep academic year and printed imprint separate.
4. Record HTTP status separately from official sale-announcement status.
5. For HTTP 403, check exact URL/encoding, redirects, API mapping and sale notices. Do not call it unreleased automatically.
6. Keep official master PDFs in temporary runner storage; do not commit them.
7. During catalog-first audit, do not permanently split/upload new editions or change production viewer/main without explicit approval.
8. Keep raw per-class evidence in class repositories and the normalized cross-class index here.
9. Antigravity must commit and push its updates to this same branch so ChatGPT and Antigravity read the same version.
10. Do not merge this documentation branch into Class 10 main until reviewed. A dedicated tracker repository can be created later and the documents migrated.