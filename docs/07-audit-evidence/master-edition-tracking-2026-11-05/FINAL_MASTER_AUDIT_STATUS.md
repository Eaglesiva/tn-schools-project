# SCERT Master Textbook Audit & Tracking Status — Classes 1 to 12

**Authoritative Review Date:** 2026-11-05 (Asia/Kolkata)  
**Project Status:** **POST-REFRESH RECONCILIATION COMPLETED — CENTRAL INDEX & TOC AUDIT HARMONIZED**  
**Core Scope:** 165 State Board Tamil & English Medium Academic Textbooks (Classes 1–12)  
**Official GET/HEAD 200 Accessible:** **124 Books**  
**Official GET/HEAD 403 CDN Failed / Unconfirmed:** **41 Books** (16 Officially Released Term-II + 25 Term-III Unconfirmed)  
**Direct Official Master In-Place Refreshed on Main:** **38 Books / 11,760 Pages**  
**Local C: Drive Master PDF Downloads:** **0 bytes (Strict Ephemeral Hosted Runner Processing Only)**  
**Viewer Routing & URL Continuity:** **100% Preserved (Zero folder renaming, question.md intact)**  

---

## 1. Scope, Methodology & Verification Terminology

To maintain strict scientific and documentation integrity, the operations performed across the 38 books are defined with precise technical distinctions:

1. **Direct Official Master In-Place Refresh (`OFFICIAL_SOURCE_REFRESHED`)**:
   - Master PDFs for current 2026–27 session were downloaded directly from the official SCERT CloudFront distribution exclusively onto GitHub Actions ephemeral hosted runners (`ubuntu-latest`).
   - The master page count was verified against the expected curriculum page count.
   - Master PDFs were sliced into single-page PDFs using PyMuPDF (`fitz`), structurally validated (`len(doc) == 1`, file size > 0), and written *in-place* over existing page PDFs on GitHub `main`.
   - Master PDFs were immediately deleted from runner `/tmp` following processing (Zero Local Persistence).
   - **Crucial Distinction**: This operation performs **direct source ingestion and structural page extraction**, replacing legacy files with the current official master edition. It is **not** a visual diff or word-for-word textual comparison against obsolete versions, but rather an authoritative synchronization to the publisher's current master release.

2. **Link Continuity & Live URL Verification**:
   - Existing GitHub directory paths and page filenames (`page_001.pdf` ... `page_NNN.pdf`) were 100% preserved.
   - All 11,760 single-page PDFs were structurally validated and committed on the runner. Representative sample live HTTP GET requests were verified across repositories on `raw.githubusercontent.com`.

3. **TOC-to-Folder Contiguity & Boundary Audit**:
   - A non-destructive audit verified that all chapter and unit subdirectories across all 38 books are **strictly contiguous from page 1 to the final page** with zero gaps and zero overlaps.
   - Folder names directly mirror textbook unit and chapter headings. No files were moved or renamed.

---

## 2. Mutually Exclusive Primary Status Accounting (165 Books)

Every in-scope State Board textbook across Classes 1–12 is categorized into exactly one mutually exclusive primary status category. Known official master pages sum to exactly **33,696 pages** across 124 measured books (41 books currently unmeasured):

| Primary Status Category | Books | Known Official Master Pages | GitHub Split Pages | Description & Next Steps |
| :--- | :---: | :---: | :---: | :--- |
| **Direct Official Master Refreshed on Main** | **38** | **11,760** | **11,760** | In-place refresh from 2026-27 master completed via runner; serving live on `main`. (Class 9: 5b/1,664p; Class 10: 1b/224p; Class 12: 32b/9,872p). |
| **Classes 1–8 GET-200 Audit Branch Validated** | **42** | **7,656** | **7,656** | Classes 1–8 Annual, Term-I, and Term-II GET-200 books validated in respective audit branches. |
| **Official Edition Update Stored on Branch** | **25** | **8,176** | **8,176** | Canonical 1-page PDFs stored in `official_editions/`. (Class 11: 23b/7,528p; Class 12: 2b/648p). |
| **Confirmed GitHub Is Newer (2025 Revised Edition)** | **6** | **1,960** | **1,872** | Production `main` contains newer 2025 reprint/revised edition than SCERT's 2024 upload. (Class 11: 4b / 1,240p off / 1,152p split; Class 10: Maths TM 368p / 368p split, Maths EM 352p / 352p split; net diff: -88p). |
| **Class 10 Stored on Update Branch** | **4** | **1,432** | **1,432** | Science TM/EM (792p), Social TM/EM (640p) stored in unit directories on update branch; full diff pending. |
| **Class 11 Reconciled Same Version on Main** | **4** | **1,304** | **1,304** | Catalog reconciled; matching imprint & page count with production `main`. (Maths EM Vol II 288p, History TM 352p, Geography TM 336p, Political Science TM 328p). |
| **Layer 4 Pilot Verified (Text-Equivalent)** | **3** | **840** | **840** | Word-for-word diff verified text-equivalent after whitespace normalization on legacy `main`. (Class 9: Tamil 272p, English 224p, Maths TM 344p). |
| **Exact Bit-for-Bit Master Match on Main** | **1** | **248** | **248** | Bit-for-bit SHA-256 match between production `main` and official master PDF. (Class 10 Tamil 248p). |
| **Class 11 API Mapping Unresolved** | **1** | **320** | **304** | Chemistry EM Vol 1 volume designation reconciliation pending (official URL duplicated Vol 2; branch holds genuine 304p; diff: -16p). |
| **Term-II Sale Commenced / CDN 403 Recovery** | **16** | — *(CDN 403)* | — | Classes 4–7 Term-II books officially on sale since Sept 22, 2026, but CloudFront returns 403. URL recovery pending. |
| **Term-III Release Unconfirmed / Official Watch**| **25** | — *(Unconfirmed)* | — | Classes 1–7 Term-III books unlisted in corporation price list; CloudFront returns 403. Official watch pending publication. |
| **Total In-Scope Books** | **165** | **33,696\*** | **33,592** | **Strictly mutually exclusive partition (Sum = 165 books; 33,696 known official master pages across 124 measured books; 41 books unmeasured)** |

> [!NOTE]
> **\*Status of the 41 Unmeasured Books (No Numeric Official Master Page Count Yet)**:  
> The **33,696** page figure represents the exact sum of **known, measured official master pages** across the 124 accessible books. The remaining **41 books** have no official numeric page count registered yet:
> - **16 Term-II books** (Classes 4–7) whose sale was announced but whose CloudFront URLs return HTTP 403.
> - **25 Term-III books** (Classes 1–7) whose release is unconfirmed and whose URLs return HTTP 403.
> 
> These 41 books do **not** have zero pages in reality; their numeric page counts simply remain unmeasured pending URL recovery.

### Reconciliation of Page Count Difference (-104 Pages)
The difference between total GitHub split pages (33,592) and total known official master pages (33,696) is exactly **-104 pages**, fully explained by three known catalog items:
1. **Class 11 Confirmed GitHub Is Newer (-88 pages)**: GitHub `main` holds 1,152 pages for 4 newer reprints (Tamil 176p, Maths TM Vol 1 320p, Maths TM Vol 2 288p, Maths EM Vol 1 368p) whereas obsolete SCERT portal masters contain 1,240 pages (248p + 368p + 304p + 320p). Net: **-88**.
2. **Class 11 Chemistry EM Vol 1 (-16 pages)**: GitHub update branch holds genuine 304 split pages, whereas the erroneous duplicate official master URL represents 320 pages. Net: **-16**.
3. **Class 10 Mathematics TM & EM (0 net difference)**: GitHub holds 720 split pages (TM 368p + EM 352p) and official master holds 720 pages (TM 368p + EM 352p). Both have been verified as curriculum-equivalent with GitHub holding the newer 2025 Revised Edition. Net: **0**.  
**Net Page Difference**: -88 - 16 + 0 = **-104 pages**.

---

## 3. Reconciled Central Index Metadata for the 38 Refreshed Books

All 38 records in `docs/SCERT_MASTER_EDITION_INDEX.csv` on branch `scert/master-edition-tracking` have been synchronized directly with their official runner evidence JSON records:

| Class | Subject & Medium | Pages | Official Content-Length (Bytes) | Official ETag | Official Master SHA-256 | Central Index Match |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: |
| **10** | English (English) | 224 | 68,655,845 | `72ecec1313...` | `4d09e77f39d2c2069b768c67c5144bdf...` | Exact Match |
| **9** | Mathematics (English) | 328 | 25,990,268 | `fd8202dd79...` | `09a3c7ce5f55fa7216a908a8a649363a...` | Exact Match |
| **9** | Science (Tamil) | 336 | 80,753,276 | `0df440d95b...` | `926439263715ecb9ec2cba8be6a32cb5...` | Exact Match |
| **9** | Science (English) | 328 | 94,344,199 | `2b43a359d3...` | `e142c38d321fd6fa4d564fa0788ee54c...` | Exact Match |
| **9** | Social Science (Tamil) | 344 | 122,323,894 | `cb876d0e83...` | `76ed2a8ff4a3779e376033e085cff2f0...` | Exact Match |
| **9** | Social Science (English) | 328 | 116,644,940 | `5d3a6ead28...` | `ee52e826762c4ea5fbca7aa6546356e7...` | Exact Match |
| **12** | General Tamil (Tamil) | 240 | 65,303,896 | `b19bbe98e6...` | `6813313ab87140f6d5e7ef8d5bb2ad4b...` | Exact Match |
| **12** | General English (English) | 248 | 59,641,395 | `6024afdc59...` | `e1872f57497d34199f1c7d235c3c0ef2...` | Exact Match |
| **12** | Mathematics (Vol I) (Tamil) | 336 | 25,066,480 | `cb78f9bb8a...` | `310b339a96ea855d9b62646cba26549a...` | Exact Match |
| **12** | Mathematics (Vol II) (Tamil) | 288 | 20,907,269 | `2ebc0520a4...` | `92b0c3ac3c0b1f13b0c5f59ee9429ea3...` | Exact Match |
| **12** | Mathematics (Vol I) (English) | 304 | 23,840,429 | `4d0ce3de3c...` | `040df951b752fe9dbe39f88d227b61f2...` | Exact Match |
| **12** | Mathematics (Vol II) (English) | 272 | 20,634,894 | `88b68e3395...` | `272488124c6efcf051cb7e42d729c15d...` | Exact Match |
| **12** | Physics (Vol I) (Tamil) | 352 | 81,188,212 | `a826ae51df...` | `1abae0855e9ea29e710d2d3a39e248b6...` | Exact Match |
| **12** | Physics (Vol II) (Tamil) | 312 | 63,397,449 | `66db2b6970...` | `a33236ee34f9a560e2270921473caae8...` | Exact Match |
| **12** | Physics (Vol II) (English) | 296 | 58,933,559 | `87fff9358d...` | `f63346abb31fe4ffb23946a3d36b446a...` | Exact Match |
| **12** | Chemistry (Vol I) (Tamil) | 328 | 26,495,073 | `82f487871a...` | `2db9c871a53b53f6004b370e5b3ee602...` | Exact Match |
| **12** | Chemistry (Vol II) (Tamil) | 344 | 28,435,318 | `85d7847c2a...` | `b4c28ca6b0521633519803b9b47cf4c2...` | Exact Match |
| **12** | Chemistry (Vol II) (English) | 328 | 24,336,354 | `70a3c387ad...` | `bbf1b2fda27546efd87e07a60ae99153...` | Exact Match |
| **12** | Botany (Tamil) | 336 | 166,086,271 | `41eafb947d...` | `242756cc9a1f5a9cfec6e987c2fb8b23...` | Exact Match |
| **12** | Botany (English) | 312 | 136,348,776 | `a1f2ca0d86...` | `eac2781e71239c5950e32b49dfd88a1e...` | Exact Match |
| **12** | Zoology (Tamil) | 336 | 58,785,391 | `e3ae1447e2...` | `f1c813fd561ba7a84091218579cfebce...` | Exact Match |
| **12** | Zoology (English) | 280 | 59,764,478 | `d624521329...` | `4e03246374070a72fa3f2c5e5ceb4a53...` | Exact Match |
| **12** | Bio-Zoology (Tamil) | 312 | 57,355,615 | `6c7410c1a7...` | `585ab94f4e72322a36b3d5b0d0614820...` | Exact Match |
| **12** | Bio-Zoology (English) | 264 | 59,029,161 | `60ebef7cfe...` | `db8d8fa4429bfb60388eb19cc418f4a7...` | Exact Match |
| **12** | Computer Science (Tamil) | 360 | 10,712,075 | `e4cf2972fe...` | `4bbca6fe774b711e7caecff0fa984bc5...` | Exact Match |
| **12** | Computer Science (English) | 360 | 10,311,470 | `06d579453f...` | `fb6f35757f4fb2636fb3a2862e34be64...` | Exact Match |
| **12** | Commerce (Tamil) | 288 | 52,546,705 | `8cd8b6e02e...` | `b86806fcc0e2b4cb15b57f884a4410a5...` | Exact Match |
| **12** | Commerce (English) | 288 | 48,362,560 | `70caf62d2d...` | `aefd49700cd14d6df11100f7236d3fc2...` | Exact Match |
| **12** | Accountancy (Tamil) | 368 | 27,455,334 | `1fe73a0531...` | `814d37be7dd5c52c2866c1f01bf8a0a2...` | Exact Match |
| **12** | Accountancy (English) | 368 | 24,263,411 | `bd73ef50c7...` | `6cbb7b89775f0f3531b46a25697c11f7...` | Exact Match |
| **12** | Economics (Tamil) | 336 | 32,258,434 | `a5ae37dc5a...` | `481e90f589980d9e79787ff81a8b5e98...` | Exact Match |
| **12** | Economics (English) | 296 | 33,171,946 | `e449759ae8...` | `c2c964a93883a9e70198ca6be113b5bf...` | Exact Match |
| **12** | History (Tamil) | 312 | 67,622,532 | `cbabbfbf9f...` | `c5fb6a88a91dae6c271e1610e7caad14...` | Exact Match |
| **12** | History (English) | 272 | 63,907,348 | `5e955dc044...` | `cc4b963081e7d4d8ef538fa099351052...` | Exact Match |
| **12** | Geography (Tamil) | 232 | 91,880,079 | `443c0ba1b0...` | `8f3b5256209581c37b9876aa9fc31a0e...` | Exact Match |
| **12** | Geography (English) | 216 | 86,386,567 | `02886d7914...` | `9e9f895c4046dbe6fc1b4c330f878988...` | Exact Match |
| **12** | Political Science (Tamil) | 360 | 73,217,892 | `6e0ec914b4...` | `3966068066bb73160e1fae0a7f1a3070...` | Exact Match |
| **12** | Political Science (English) | 328 | 79,884,994 | `033d4bf293...` | `a5ba26c7657d42cf38f97801be9cbda7...` | Exact Match |
| **Total** | **38 Books** | **11,760** | — | — | — | **38/38 Exact Matches (100%)** |

---

## 4. TOC-to-Folder Contiguity & Boundary Audit Findings

**TOC Audit Qualification**: `STRUCTURAL_CONTIGUITY_VERIFIED; TOC_MAPPING_EVIDENCE_INCOMPLETE`  
*Contiguity evidence artifact generated and persisted at:* [`docs/refresh_evidence/scert_38_toc_contiguity_audit.json`](./refresh_evidence/scert_38_toc_contiguity_audit.json)

A full structural inspection of all 38 books on production `main` confirmed:
1. **100% Contiguity (38 / 38 Books across 592 Subdirectories)**: All 38 books exhibit strictly continuous page spans (`00_prelims/page_001.pdf` through `page_NNN.pdf`). Every single unit/chapter directory starts exactly at `start_page[i] == end_page[i-1] + 1` with 0 gaps, 0 overlaps, and 0 missing pages across all **592 directories** (Class 9: 125, Class 10: 22, Class 12: 445).
2. **Folder Boundaries & Nomenclature**:
   - **Class 10 English (224p)**: Partitioned into 22 sequential chapter/prose/poem subdirectories (`00_prelims` to `21_a_dilemma`), verified for structural page continuity from page 1 to 224 (semantic heading-to-unit mapping categorized under TOC_MAPPING_EVIDENCE_INCOMPLETE).
   - **Class 9 (5 books — 1,664p)**: Partitioned across **125 chapter subdirectories** (`maths_em`: 11 dirs, `science_tm`: 26 dirs, `science_em`: 26 dirs, `social_science_tm`: 31 dirs, `social_science_em`: 31 dirs).
   - **Class 12 (32 books — 9,872p)**: All 32 books partitioned across **445 unit/chapter subdirectories** with exact contiguous ranges.
   - **Multi-Volume Separation**: For Class 12 multi-volume subjects (Mathematics TM/EM, Physics TM/EM, Chemistry TM/EM), Vol 1 and Vol 2 directories are cleanly separated without cross-volume collision.
   - **Summary of Directories**: 125 (Class 9) + 22 (Class 10) + 445 (Class 12) = **592 contiguous directories** across 38 books.
3. **Evidence Boundary**: While full structural contiguity from page 1 to the final page across all 592 chapter subdirectories is mathematically verified and recorded in `scert_38_toc_contiguity_audit.json`, formal semantic mapping of every textbook print heading to its syllabus unit is categorized as `TOC_MAPPING_EVIDENCE_INCOMPLETE`. The current JSON evidence proves strict page-range continuity, not the verbatim semantic heading-to-folder mapping.
4. **Exceptions / Reorganization**: **Zero folder renaming or file moves were performed.** All preexisting routing and viewer URLs remain 100% intact.
