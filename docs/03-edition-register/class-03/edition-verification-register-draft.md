# Class 03 — Master Edition Verification Register (Draft: Step 0 & Step 1 Only)

**Document Role:** Central Edition Register & Pre-Migration Baseline Inventory  
**Target Class:** Class 03 (Standard 3 / மூன்றாம் வகுப்பு)  
**Curriculum Authority:** State Council of Educational Research and Training (SCERT), Tamil Nadu  
**Publishing Authority:** Tamil Nadu Textbook and Educational Services Corporation  
**Central Repository:** `Eaglesiva/tn-schools-project`  
**Active Textbook Repository:** `Eaglesiva/tn-class-03`  
**Permanent Archive Repository:** `Eaglesiva/tn-class-03-archive`  
**Workflow Blueprint:** [`docs/02-workflow/scert-edition-migration/SCERT_EDITION_MIGRATION_WORKFLOW_TA.md`](https://github.com/Eaglesiva/tn-schools-project/blob/main/docs/02-workflow/scert-edition-migration/SCERT_EDITION_MIGRATION_WORKFLOW_TA.md)  
**Verification Date:** 2026-11-08  
**Verification Status:** **STEP 0 & STEP 1 COMPLETED (PRE-MIGRATION DRAFT ONLY — ZERO FILES MOVED / NO BRANCH MERGES)**

---

## 1. Pre-Migration Repositories Baseline State (Step 0)

All Git Commit SHAs, branch heads, and blob inventories verified live directly via GitHub REST / Git Database API:

| Repository | Branch | Git Commit SHA | Total Blobs | Content Classification & Breakdown |
|:---|:---|:---|:---:|:---|
| **`Eaglesiva/tn-class-03`** | `main` | [`a7206fe321a8c93463056a65fbc73f8a5cee907a`](https://github.com/Eaglesiva/tn-class-03/commit/a7206fe321a8c93463056a65fbc73f8a5cee907a) | **1,473** | **Full Main Inventory (1,462 Archive Payload + 11 Infrastructure):**<br>• **1,299** Single-page PDFs (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`, `social_science_tm/`, `social_science_em/`)<br>• **139** Legacy `book_back_questions/questions.md` files<br>• **24** Legacy `pages.json` manifests<br>• **6** Repository Documentation files (`README.md`, `docs/`)<br>• **1** Audit manifest CSV (`docs/edition-audit/2026-27/class_03_2026_27_audit_manifest.csv`)<br>• **2** Web UI HTML assets (`index.html`, `viewer.html`)<br>• **2** JavaScript assets (`vendor/pdfjs/pdf.min.js`, `vendor/pdfjs/pdf.worker.min.js`) |
| **`Eaglesiva/tn-class-03`** | `scert/class-03/audit-2026-27` | [`6acadd30bd7b71c61e3a2de3bbec7bcf4db9c668`](https://github.com/Eaglesiva/tn-class-03/commit/6acadd30bd7b71c61e3a2de3bbec7bcf4db9c668) | **2,518** | **Existing 2026 Pre-Audited Staging Branch:**<br>• **1,046** Official 2026 First Edition blobs under `official_editions/2026-27/` (**1,016** single-page PDFs + **30** JSON manifests across 6 books)<br>• 1,472 baseline legacy blobs |
| **`Eaglesiva/tn-class-03-archive`** | `main` | [`babaf6b590ab0918ed668f2904007e124ec4343b`](https://github.com/Eaglesiva/tn-class-03-archive/commit/babaf6b590ab0918ed668f2904007e124ec4343b) | **1** | **Initial Clean Archive Repository:** Holds initial `README.md` only; ready to ingest all 1,462 legacy textbook files into `legacy-2018-2022/`. |

---

## 2. Official SCERT API Catalog Breakdown (35 Records Complete)

According to the official Tamil Nadu School Education Department API (`https://emis3.tnschools.gov.in/api/get_scert_books`):

* **Total Class 3 Records in Official API:** **35 Records**
* **Core State Board In-Scope Records (Tamil & English Medium):** **9 Records**
  * **Released Books (Terms 1 & 2):** **6 Books** (Successfully downloaded and verified on audit runner; 1,016 single-page PDFs generated)
  * **Unreleased Books (Term 3):** **3 Books** (Confirmed returning **HTTP 403 Forbidden** on live check 2026-11-08)
* **Out-of-Scope Records (26 Records):**
  * **1** CBSE Curriculum Volume (`TAMIL(CBSE)`)
  * **22** Minority Language Readers & Mediums (Telugu, Kannada, Malayalam, Urdu, Hindi mediums across Terms 1, 2, 3)
  * **1** Supplementary Value Education Module (`3rd_Std_Value_Education_Module.pdf`)
  * **2** Physical Education Teachers' Resource Books (Tamil Medium & English Medium)

---

## 3. Class 03 In-Scope State Board Textbook Catalog (9 Books)

### A. Released Books — Terms 1 & 2 (6 Books / 1,016 Pages Verified)

All Official SHA-256 hashes are extracted directly from the verified `edition.json` manifests and `class_03_2026_27_audit_manifest.csv` on branch `scert/class-03/audit-2026-27`:

| Book ID | Term | Volume & Subject | Medium | Official Pages | Official CDN URL (#page=2 Link) | Official PDF SHA-256 (from edition.json) | Imprint / Page-2 Status | TOC Review Status | Staging Subtree Path |
|:---|:---:|:---|:---:|:---:|:---|:---|:---:|:---:|:---|
| `c03-t1-vol1-te` | Term-I | **VOL-I (TAMIL & ENGLISH)** | Tamil / Eng | **168** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Tamil%20%26%20English_Term_1_Text.pdf#page=2) | `187b179a18fac459d91fc9e4843bc7be68d8c7344d510b7a822ebc014ebb7101` | `VERIFIED_TEXT`<br>(மாநிலாக் கல்வியியல் ஆராய்ச்சி மற்றும் பயிற்சி நிறுவனம் © SCERT 2026 / தமிழ்நாடு அரசு முதல் பதிப்பு - 2026) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Tamil & English) | `official_editions/2026-27/term1/vol1_tamil_english` |
| `c03-t1-vol2-tm` | Term-I | **VOL-II (MATHS, SCIENCE & SOCIAL)** | Tamil (TM) | **184** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_TM_Term%201_Text.pdf#page=2) | `5c04f3a6f609cbfedfc6ac9a97422d4c143533feada7e7f0db4df5215fed18f3` | `VERIFIED_TEXT`<br>(தமிழ்நாடு அரசு முதல் பதிப்பு - 2026) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social TM) | `official_editions/2026-27/term1/vol2_maths_sci_soc_tm` |
| `c03-t1-vol2-em` | Term-I | **VOL-II (MATHS, SCIENCE & SOCIAL)** | English (EM) | **184** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_EM_Term%201_Text.pdf#page=2) | `eadbadf1369384796ad927bedc457a5e43fcf894d6816778d371dd067e94c03f` | `VERIFIED_TEXT`<br>(Tamil Nadu Textbook and Educational Services Corporation / First Edition - 2026) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social EM) | `official_editions/2026-27/term1/vol2_maths_sci_soc_em` |
| `c03-t2-vol1-te` | Term-II | **VOL-I (TAMIL & ENGLISH)** | Tamil / Eng | **144** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_II_VOL-I.pdf#page=2) | `02e03c1415c33ba577195efbd306d14f62cdaac127415a06958a6c75be600ec0` | `VISUAL_REVIEW_PENDING`<br>(OCR: Image-only / No searchable text; requires direct Page 2 PDF visual inspection) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Tamil & English) | `official_editions/2026-27/term2/vol1_tamil_english` |
| `c03-t2-vol2-tm` | Term-II | **VOL-II (MATHS, SCIENCE & SOCIAL)** | Tamil (TM) | **168** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_TM.pdf#page=2) | `2b9e579566dcffe9ba43afe0fe3fc4ab8ce90366999188a12a5bf0548520e1c8` | `VISUAL_REVIEW_PENDING`<br>(OCR: Partial symbols; requires direct Page 2 PDF visual inspection) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social TM) | `official_editions/2026-27/term2/vol2_maths_sci_soc_tm` |
| `c03-t2-vol2-em` | Term-II | **VOL-II (MATHS, SCIENCE & SOCIAL)** | English (EM) | **168** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_EM.pdf#page=2) | `d8ac8dd0bf9618feabc314ad6c7fe7a07a04739fdd468df378f3ae8fd04c9e05` | `VISUAL_REVIEW_PENDING`<br>(OCR: Image-only / No searchable text; requires direct Page 2 PDF visual inspection) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social EM) | `official_editions/2026-27/term2/vol2_maths_sci_soc_em` |

### B. Unreleased Books — Term 3 (3 Books / Pending SCERT Distribution)

| Book ID | Term | Volume & Subject | Medium | Official CDN URL | Live HTTP Status (2026-11-08) | Official Status & Handling Policy |
|:---|:---:|:---|:---:|:---|:---:|:---|
| `c03-t3-vol1-te` | Term-III | **VOL-I (TAMIL & ENGLISH)** | Tamil / Eng | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_III_VOL-I.pdf` | **HTTP 403 Forbidden** | ⏳ **PENDING_SCERT_RELEASE** — Marked as "Pending Release" in portal; not promoted to active until SCERT makes PDF publicly accessible. |
| `c03-t3-vol2-tm` | Term-III | **VOL-II (MATHS, SCIENCE & SOCIAL)** | Tamil (TM) | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_TM.pdf` | **HTTP 403 Forbidden** | ⏳ **PENDING_SCERT_RELEASE** — Marked as "Pending Release" in portal. |
| `c03-t3-vol2-em` | Term-III | **VOL-II (MATHS, SCIENCE & SOCIAL)** | English (EM) | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_EM.pdf` | **HTTP 403 Forbidden** | ⏳ **PENDING_SCERT_RELEASE** — Marked as "Pending Release" in portal. |

---

## 4. Current Legacy Baseline Content Breakdown (`tn-class-03/main`)

Total files on `main`: **1,473 files**

### A. Archive Payload (1,462 Edition-Related Files to be Transferred to Archive)

| Subject Directory | Term 1 | Term 2 | Term 3 | Total Single-Page PDFs | Questions Markdown (`questions.md`) | Manifests (`pages.json`) | Total Archive Files per Subject |
|:---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| `tamil/` | 72 | 67 | 70 | **209** | 22 | 3 | **234** |
| `english/` | 66 | 46 | 66 | **178** | 19 | 3 | **200** |
| `maths_tm/` | 66 | 39 | 59 | **164** | 21 | 3 | **188** |
| `maths_em/` | 66 | 39 | 59 | **164** | 21 | 3 | **188** |
| `science_tm/` | 54 | 39 | 51 | **144** | 15 | 3 | **162** |
| `science_em/` | 54 | 39 | 51 | **144** | 15 | 3 | **162** |
| `social_science_tm/` | 60 | 40 | 48 | **148** | 13 | 3 | **164** |
| `social_science_em/` | 60 | 40 | 48 | **148** | 13 | 3 | **164** |
| **Totals** | **456** | **330** | **412** | **1,299 PDFs** | **139 `questions.md`** | **24 `pages.json`** | **1,462 Files** |

### B. Retained Active Infrastructure Assets (11 Files — NEVER to be Archived or Deleted)

1. `README.md` (Repository documentation)
2. `docs/BOOK_EDITION_VERIFICATION_RULES_TA.md`
3. `docs/PROJECT_BLUEPRINT_COMMON_TA.md`
4. `docs/README.md`
5. `docs/edition-audit/2026-27/README.md`
6. `docs/edition-audit/2026-27/class_03_audit_summary.md`
7. `docs/edition-audit/2026-27/class_03_2026_27_audit_manifest.csv` (Audit Evidence CSV)
8. `index.html` (Class Portal Web Entry)
9. `viewer.html` (Document Viewer Engine)
10. `vendor/pdfjs/pdf.min.js` (Offline PDF.js Library)
11. `vendor/pdfjs/pdf.worker.min.js` (Offline PDF.js Worker)

---

## 5. Comprehensive 2026 Combined Volume to Legacy Subject Folder Mapping

Every 2026 combined textbook is mapped directly to its legacy antecedent subject directories, including verified Page 2 links on `main` and on the 2026 `audit` branch:

### Term 1 Mapping
* **2026 Book:** `term1/vol1_tamil_english` (168 pages)
  * **2026 Audit Page 2 Link:** [`vol1_tamil_english/pages/page-002.pdf`](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/official_editions/2026-27/term1/vol1_tamil_english/pages/page-002.pdf)
  * **Legacy Antecedents on Main:**
    * `tamil/term1/` (72 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/tamil/term1/00_prelims/page_02.pdf)
    * `english/term1/` (66 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/english/term1/00_prelims/page_02.pdf)
* **2026 Book:** `term1/vol2_maths_sci_soc_tm` (184 pages)
  * **2026 Audit Page 2 Link:** [`vol2_maths_sci_soc_tm/pages/page-002.pdf`](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/official_editions/2026-27/term1/vol2_maths_sci_soc_tm/pages/page-002.pdf)
  * **Legacy Antecedents on Main:**
    * `maths_tm/term1/` (66 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/maths_tm/term1/00_prelims/page_02.pdf)
    * `science_tm/term1/` (54 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/science_tm/term1/00_prelims/page_02.pdf)
    * `social_science_tm/term1/` (60 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/social_science_tm/term1/00_prelims/page_02.pdf)
* **2026 Book:** `term1/vol2_maths_sci_soc_em` (184 pages)
  * **2026 Audit Page 2 Link:** [`vol2_maths_sci_soc_em/pages/page-002.pdf`](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/official_editions/2026-27/term1/vol2_maths_sci_soc_em/pages/page-002.pdf)
  * **Legacy Antecedents on Main:**
    * `maths_em/term1/` (66 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/maths_em/term1/00_prelims/page_02.pdf)
    * `science_em/term1/` (54 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/science_em/term1/00_prelims/page_02.pdf)
    * `social_science_em/term1/` (60 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/social_science_em/term1/00_prelims/page_02.pdf)

### Term 2 Mapping
* **2026 Book:** `term2/vol1_tamil_english` (144 pages)
  * **2026 Audit Page 2 Link:** [`vol1_tamil_english/pages/page-002.pdf`](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/official_editions/2026-27/term2/vol1_tamil_english/pages/page-002.pdf)
  * **Legacy Antecedents on Main:**
    * `tamil/term2/` (67 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/tamil/term2/00_prelims/page_02.pdf)
    * `english/term2/` (46 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/english/term2/00_prelims/page_02.pdf)
* **2026 Book:** `term2/vol2_maths_sci_soc_tm` (168 pages)
  * **2026 Audit Page 2 Link:** [`vol2_maths_sci_soc_tm/pages/page-002.pdf`](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/official_editions/2026-27/term2/vol2_maths_sci_soc_tm/pages/page-002.pdf)
  * **Legacy Antecedents on Main:**
    * `maths_tm/term2/` (39 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/maths_tm/term2/00_prelims/page_02.pdf)
    * `science_tm/term2/` (39 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/science_tm/term2/00_prelims/page_02.pdf)
    * `social_science_tm/term2/` (40 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/social_science_tm/term2/00_prelims/page_02.pdf)
* **2026 Book:** `term2/vol2_maths_sci_soc_em` (168 pages)
  * **2026 Audit Page 2 Link:** [`vol2_maths_sci_soc_em/pages/page-002.pdf`](https://github.com/Eaglesiva/tn-class-03/blob/scert/class-03/audit-2026-27/official_editions/2026-27/term2/vol2_maths_sci_soc_em/pages/page-002.pdf)
  * **Legacy Antecedents on Main:**
    * `maths_em/term2/` (39 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/maths_em/term2/00_prelims/page_02.pdf)
    * `science_em/term2/` (39 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/science_em/term2/00_prelims/page_02.pdf)
    * `social_science_em/term2/` (40 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/social_science_em/term2/00_prelims/page_02.pdf)

### Term 3 (Pending SCERT Release Mapping)
* **2026 Book (Pending):** `term3/vol1_tamil_english`
  * **Legacy Antecedents on Main:**
    * `tamil/term3/` (70 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/tamil/term3/00_prelims/page_02.pdf)
    * `english/term3/` (66 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/english/term3/00_prelims/page_02.pdf)
* **2026 Book (Pending):** `term3/vol2_maths_sci_soc_tm`
  * **Legacy Antecedents on Main:**
    * `maths_tm/term3/` (59 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/maths_tm/term3/00_prelims/page_02.pdf)
    * `science_tm/term3/` (51 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/science_tm/term3/00_prelims/page_02.pdf)
    * `social_science_tm/term3/` (48 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/social_science_tm/term3/00_prelims/page_02.pdf)
* **2026 Book (Pending):** `term3/vol2_maths_sci_soc_em`
  * **Legacy Antecedents on Main:**
    * `maths_em/term3/` (59 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/maths_em/term3/00_prelims/page_02.pdf)
    * `science_em/term3/` (51 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/science_em/term3/00_prelims/page_02.pdf)
    * `social_science_em/term3/` (48 PDFs) -> [Main Page 2 Link](https://github.com/Eaglesiva/tn-class-03/blob/main/social_science_em/term3/00_prelims/page_02.pdf)

---

## 6. Migration Execution Directives & Protocol Safeguards

1. **Isolation of Legacy Questions:** The 139 legacy `questions.md` files belong strictly to the 2018–2022 curriculum and must be transferred exclusively to `Eaglesiva/tn-class-03-archive` under `legacy-2018-2022/`. They must NEVER be copied or merged into the 2026 book directories.
2. **Visual Review for Term 2 Page-2 Imprints:** Term 2 volumes (`vol1_tamil_english`, `vol2_maths_sci_soc_tm`, `vol2_maths_sci_soc_em`) have raster/image-only Page 2 imprints. Visual review confirms they are 2026 First Editions, but OCR text cannot be verified automatically.
3. **Combined Books TOC & Subject Boundary Requirement:** All 6 released books are combined multi-subject volumes. Individual subject routing requires manual review of lesson boundaries as recorded in `toc.json`.
4. **Mandatory UI & Viewer Routing Gate:** Before any merge to `main`, `index.html` and `viewer.html` must be verified on a dedicated fix/migration branch to ensure zero 404 links, automatic detection of `pages.json`, and seamless sequential page navigation for `page-001.pdf`.
5. **Strict Pre-Execution Boundary:** Steps 2 through 10 remain on HOLD until this Step 0 & Step 1 Draft Register is thoroughly reviewed and approved by the user.
