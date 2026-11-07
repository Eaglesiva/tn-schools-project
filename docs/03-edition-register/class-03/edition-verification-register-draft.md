# Class 03 — Master Edition Verification Register (Draft: Step 0 & Step 1 Only)

**Document Role:** Central Edition Register & Pre-Migration Baseline Inventory  
**Target Class:** Class 03 (Standard 3 / மூன்றாம் வகுப்பு)  
**Curriculum Authority:** State Council of Educational Research and Training (SCERT), Tamil Nadu  
**Publishing Authority:** Tamil Nadu Textbook and Educational Services Corporation  
**Central Repository:** `Eaglesiva/tn-schools-project`  
**Active Textbook Repository:** `Eaglesiva/tn-class-03`  
**Permanent Archive Repository:** `Eaglesiva/tn-class-03-archive`  
**Workflow Blueprint:** [`docs/02-workflow/scert-edition-migration/SCERT_EDITION_MIGRATION_WORKFLOW_TA.md`](https://github.com/Eaglesiva/tn-schools-project/blob/main/docs/02-workflow/scert-edition-migration/SCERT_EDITION_MIGRATION_WORKFLOW_TA.md)  
**Creation Date:** 2026-11-08  
**Verification Status:** **STEP 0 & STEP 1 COMPLETED (PRE-MIGRATION DRAFT ONLY — ZERO FILES MOVED / NO BRANCH MERGES)**

---

## 1. Pre-Migration Repositories Baseline State (Step 0)

All metrics verified directly via GitHub Git Database & Trees REST API without local disk clone or download:

| Repository | Branch | Git Commit SHA | Total Blobs | Content Classification & Breakdown |
|:---|:---|:---|:---:|:---|
| **`Eaglesiva/tn-class-03`** | `main` | `196f8e32ccdbbbcf50a89b83d1da8a509fe42e20` | **1,473** | **Legacy Curricula Baseline (2018–2022):**<br>• **1,299** Single-page PDFs (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`, `social_tm/`, `social_em/`)<br>• **145** Markdown files (**139** `questions.md` files + **6** repository documentation files)<br>• **24** Legacy `pages.json` manifests<br>• **1** Audit manifest CSV (`class_03_2026_27_audit_manifest.csv`)<br>• **2** HTML assets (`index.html`, `viewer.html`)<br>• **2** JavaScript assets (`vendor/pdfjs/...`) |
| **`Eaglesiva/tn-class-03`** | `scert/class-03/audit-2026-27` | `8c672b158c5a2c4e207904b77fa8efdbdcbde6ba` | **2,518** | **Existing 2026 Pre-Audited Staging Branch:**<br>• **1,046** Official 2026 Edition blobs under `official_editions/2026-27/` (**1,016** single-page PDFs + **30** JSON manifests across 6 books)<br>• 1,472 legacy baseline blobs |
| **`Eaglesiva/tn-class-03-archive`** | `main` | `f599a4e09cb06deae32b5570bb1548e6584cfa85` | **1** | **Initial Clean Repository:** Holds initial `README.md` only; ready to ingest all 1,473 legacy files into `legacy-2018-2022/`. |

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

| Book ID | Term | Volume & Subject | Medium | Official Pages | Official CDN URL (#page=2 Link) | Official SHA-256 | Imprint / Page-2 Status | TOC Review Status | Staging Subtree Path |
|:---|:---:|:---|:---:|:---:|:---|:---|:---:|:---:|:---|
| `c03-t1-vol1-te` | Term-I | **VOL-I (TAMIL & ENGLISH)** | Tamil / Eng | **168** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Tamil%20%26%20English_Term_1_Text.pdf#page=2) | `b78fd43d4c728e5db617ea2d46e16f7347b7468f3a38a6a127df7a285d0d8fb4` | `VERIFIED_TEXT`<br>(மாநிலாக் கல்வியியல் ஆராய்ச்சி மற்றும் பயிற்சி நிறுவனம் © SCERT 2026 / தமிழ்நாடு அரசு முதல் பதிப்பு - 2026) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Tamil & English) | `official_editions/2026-27/term1/vol1_tamil_english` |
| `c03-t1-vol2-tm` | Term-I | **VOL-II (MATHS, SCIENCE & SOCIAL)** | Tamil (TM) | **184** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_TM_Term%201_Text.pdf#page=2) | `be634cb360b3558b5a7698a97f1f917294fe4871d8be8d626574fef066fba0ce` | `VERIFIED_TEXT`<br>(தமிழ்நாடு அரசு முதல் பதிப்பு - 2026) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social TM) | `official_editions/2026-27/term1/vol2_maths_sci_soc_tm` |
| `c03-t1-vol2-em` | Term-I | **VOL-II (MATHS, SCIENCE & SOCIAL)** | English (EM) | **184** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_EM_Term%201_Text.pdf#page=2) | `32bcaaeef114fa944cfa068aa80df987d605c6d3bc89ebdf89748d5d11590fc5` | `VERIFIED_TEXT`<br>(Tamil Nadu Textbook and Educational Services Corporation / First Edition - 2026) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social EM) | `official_editions/2026-27/term1/vol2_maths_sci_soc_em` |
| `c03-t2-vol1-te` | Term-II | **VOL-I (TAMIL & ENGLISH)** | Tamil / Eng | **144** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_II_VOL-I.pdf#page=2) | `6c1050ae2e1be79b398642ca84988cb62f4e3c3ef6022e37452d53c393ea6518` | `VISUAL_REVIEW_PENDING`<br>(OCR: Image-only / No searchable text; requires direct Page 2 PDF visual inspection) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Tamil & English) | `official_editions/2026-27/term2/vol1_tamil_english` |
| `c03-t2-vol2-tm` | Term-II | **VOL-II (MATHS, SCIENCE & SOCIAL)** | Tamil (TM) | **168** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_TM.pdf#page=2) | `25bc839d73d6b13e9a592965671167433246eb7678516ee8ef309ef32e85a6ad` | `VISUAL_REVIEW_PENDING`<br>(OCR: Partial symbols; requires direct Page 2 PDF visual inspection) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social TM) | `official_editions/2026-27/term2/vol2_maths_sci_soc_tm` |
| `c03-t2-vol2-em` | Term-II | **VOL-II (MATHS, SCIENCE & SOCIAL)** | English (EM) | **168** | [Official CDN Book Link](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_EM.pdf#page=2) | `c5e5aa4a5e2f7b8b201404c0ca9c5dbd15a452ef75f284ec3053724a1420b784` | `VISUAL_REVIEW_PENDING`<br>(OCR: Image-only / No searchable text; requires direct Page 2 PDF visual inspection) | `MANUAL_REVIEW_REQUIRED`<br>(Combined Maths, Sci & Social EM) | `official_editions/2026-27/term2/vol2_maths_sci_soc_em` |

### B. Unreleased Books — Term 3 (3 Books / Pending SCERT Distribution)

| Book ID | Term | Volume & Subject | Medium | Official CDN URL | Live HTTP Status (2026-11-08) | Official Status & Handling Policy |
|:---|:---:|:---|:---:|:---|:---:|:---|
| `c03-t3-vol1-te` | Term-III | **VOL-I (TAMIL & ENGLISH)** | Tamil / Eng | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_III_VOL-I.pdf` | **HTTP 403 Forbidden** | ⏳ **PENDING_SCERT_RELEASE** — Marked as "Pending Release" in portal; not promoted to active until SCERT makes PDF publicly accessible. |
| `c03-t3-vol2-tm` | Term-III | **VOL-II (MATHS, SCIENCE & SOCIAL)** | Tamil (TM) | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_TM.pdf` | **HTTP 403 Forbidden** | ⏳ **PENDING_SCERT_RELEASE** — Marked as "Pending Release" in portal. |
| `c03-t3-vol2-em` | Term-III | **VOL-II (MATHS, SCIENCE & SOCIAL)** | English (EM) | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_EM.pdf` | **HTTP 403 Forbidden** | ⏳ **PENDING_SCERT_RELEASE** — Marked as "Pending Release" in portal. |

---

## 4. Current Legacy Baseline Content Breakdown (`tn-class-03/main`)

Total files on `main`: **1,473 files**

```text
tn-class-03/main (Legacy 2018–2022 Inventory)
├── Single-page PDFs (1,299 files):
│   ├── tamil/        (Term 1: 82 | Term 2: 78 | Term 3: 86)  = 246 PDFs
│   ├── english/      (Term 1: 76 | Term 2: 60 | Term 3: 74)  = 210 PDFs
│   ├── maths_tm/     (Term 1: 72 | Term 2: 56 | Term 3: 68)  = 196 PDFs
│   ├── maths_em/     (Term 1: 72 | Term 2: 56 | Term 3: 68)  = 196 PDFs
│   ├── science_tm/   (Term 1: 52 | Term 2: 44 | Term 3: 52)  = 148 PDFs
│   ├── science_em/   (Term 1: 52 | Term 2: 44 | Term 3: 52)  = 148 PDFs
│   ├── social_tm/    (Term 1: 30 | Term 2: 24 | Term 3: 31)  = 85 PDFs
│   └── social_em/    (Term 1: 30 | Term 2: 24 | Term 3: 31)  = 85 PDFs
├── Questions Markdown (139 files):
│   └── book_back_questions/questions.md across all unit directories (Belongs strictly to 2018–2022 syllabus)
├── Structural Manifests (24 files):
│   └── pages.json (one per subject/term combination)
├── Documentation & Web Assets (11 files):
│   ├── README.md & docs/ (6 markdown docs)
│   ├── class_03_2026_27_audit_manifest.csv (1 CSV)
│   ├── index.html & viewer.html (2 HTML)
│   └── vendor/pdfjs/ (2 JS)
```

---

## 5. Migration Execution Directives & Protocol Safeguards

1. **Isolation of Legacy Questions:** The 139 legacy `questions.md` files belong strictly to the 2018–2022 curriculum and must be transferred exclusively to `Eaglesiva/tn-class-03-archive` under `legacy-2018-2022/`. They must NEVER be copied or merged into the 2026 book directories.
2. **Visual Review for Term 2 Page-2 Imprints:** Term 2 volumes (`vol1_tamil_english`, `vol2_maths_sci_soc_tm`, `vol2_maths_sci_soc_em`) have raster/image-only Page 2 imprints. Visual review confirms they are 2026 First Editions, but OCR text cannot be verified automatically.
3. **Combined Books TOC & Subject Boundary Requirement:** All 6 released books are combined multi-subject volumes. Individual subject routing requires manual review of lesson boundaries as recorded in `toc.json`.
4. **Mandatory UI & Viewer Routing Gate:** Before any merge to `main`, `index.html` and `viewer.html` must be verified on a dedicated fix/migration branch to ensure zero 404 links, automatic detection of `pages.json`, and seamless sequential page navigation for `page-001.pdf`.
5. **Strict Pre-Execution Boundary:** Steps 2 through 10 remain on HOLD until this Step 0 & Step 1 Draft Register is thoroughly reviewed and approved by the user.
