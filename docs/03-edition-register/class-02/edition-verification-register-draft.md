# Class 02 — Master Edition Verification & Migration Register (Draft)

**Document Type:** Pilot Master Register (Draft for Review & Approval)  
**Target Class:** Class 02 (Tamil Nadu State Board)  
**Central Repository:** `Eaglesiva/tn-schools-project`  
**Active Repository:** `Eaglesiva/tn-class-02` (Main SHA: `196f8e32ccdbbbcf50a89b83d1da8a509fe42e20`)  
**Archive Repository:** `Eaglesiva/tn-class-02-archive` (Main SHA: `7f3cb55440bb58d6210e8396901c725f87c52c42`)  
**Audit Source Branch:** `scert/class-02/audit-2026-27` (Commit SHA: `d2e168f2b2f646d4f29ff428caefbb599dd8ed28`)  
**Current Gate:** **STEP 2 (EDITION VERIFICATION), STEP 3 (MAPPING), STEP 4 & 5 (MIGRATION PLAN) — AWAITING USER APPROVAL PRIOR TO STEP 6 EXECUTION**

---

## 1. Executive Summary & Policy Rules

> [!IMPORTANT]
> **Safety Protocol:**
> 1. No files have been moved, deleted, renamed, or migrated yet.
> 2. Zero local cloning, downloading, or PDF splitting on user machine (GitHub API only).
> 3. All 114 legacy questions markdown files belong to the 2018–2022 syllabus and will be archived exclusively into `tn-class-02-archive`. Zero legacy questions will be mixed into 2026 books.
> 4. All 824 2026 single-page PDFs already exist and are 100% split-validated on `scert/class-02/audit-2026-27`. Re-extraction is strictly forbidden.

---

## 2. Master Verification Table (Class 02 — 9 Records)

| ID | Book Identity | Official SCERT Master CDN & Page 2 Direct Link | 2026 First Edition Imprint & Source Location (Audit Branch) | Existing Legacy Baseline (2018/2022) Imprint & Location (`main` branch) | Evidence Status | Migration Readiness |
|:---|:---|:---|:---|:---|:---|:---|
| **C2-T1-V1** | **Class 2 / Term-I**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 160 | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Tamil%20&%20English%20Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Tamil%20&%20English%20Term%201_Text.pdf#page=2) | **Imprint:** தமிழ்நாடு அரசு முதல் பதிப்பு - 2026; © SCERT 2026<br>**Branch:** `scert/class-02/audit-2026-27`<br>**Path:** `official_editions/2026-27/term1/vol1_tamil_english/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term1/vol1_tamil_english/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2019, திருத்திய பதிப்பு 2022<br>**Paths:** `tamil/term1/` (82 PDFs), `english/term1/` (78 PDFs)<br>[Legacy Tamil Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/tamil/term1/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SPLIT_VALIDATED`<br>(160/160 pages) | Ready for Migration |
| **C2-T1-V2-TM** | **Class 2 / Term-I**<br>VOL-II (Maths & EVS TM)<br>Medium: Tamil<br>Pages: 144 | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd_Maths%20&%20EVS_TM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd_Maths%20&%20EVS_TM_Term%201_Text.pdf#page=2) | **Imprint:** II தமிழ்நாடு அரசு முதல் பதிப்பு - 2026; © SCERT 2026<br>**Branch:** `scert/class-02/audit-2026-27`<br>**Path:** `official_editions/2026-27/term1/vol2_maths_evs_tm/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term1/vol2_maths_evs_tm/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>**Paths:** `maths_tm/term1/` (76 PDFs), `science_tm/term1/` (54 PDFs)<br>[Legacy Maths Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_tm/term1/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SPLIT_VALIDATED`<br>(144/144 pages) | Ready for Migration |
| **C2-T1-V2-EM** | **Class 2 / Term-I**<br>VOL-II (Maths & EVS EM)<br>Medium: English<br>Pages: 144 | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Maths%20&%20Environmental%20Science_Term-1_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Maths%20&%20Environmental%20Science_Term-1_Text.pdf#page=2) | **Imprint:** II Government of Tamil Nadu - First Edition 2026; © SCERT 2026<br>**Branch:** `scert/class-02/audit-2026-27`<br>**Path:** `official_editions/2026-27/term1/vol2_maths_evs_em/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term1/vol2_maths_evs_em/pages/page-002.pdf) | **Imprint:** First Edition 2019, Revised 2022<br>**Paths:** `maths_em/term1/` (76 PDFs), `science_em/term1/` (54 PDFs)<br>[Legacy Maths EM Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_em/term1/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SPLIT_VALIDATED`<br>(144/144 pages) | Ready for Migration |
| **C2-T2-V1** | **Class 2 / Term-II**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 136 | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_II_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_II_VOL-I.pdf#page=2) | **Imprint:** தமிழ்நாடு அரசு முதல் பதிப்பு - 2026; © SCERT 2026 (Image verification)<br>**Branch:** `scert/class-02/audit-2026-27`<br>**Path:** `official_editions/2026-27/term2/vol1_tamil_english/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term2/vol1_tamil_english/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2019, திருத்திய பதிப்பு 2022<br>**Paths:** `tamil/term2/` (50 PDFs), `english/term2/` (47 PDFs)<br>[Legacy Tamil Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/tamil/term2/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SPLIT_VALIDATED`<br>(136/136 pages) | Ready for Migration |
| **C2-T2-V2-TM** | **Class 2 / Term-II**<br>VOL-II (Maths & EVS TM)<br>Medium: Tamil<br>Pages: 120 | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_TM.pdf#page=2) | **Imprint:** II தமிழ்நாடு அரசு முதல் பதிப்பு - 2026; © SCERT 2026<br>**Branch:** `scert/class-02/audit-2026-27`<br>**Path:** `official_editions/2026-27/term2/vol2_maths_evs_tm/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term2/vol2_maths_evs_tm/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>**Paths:** `maths_tm/term2/` (50 PDFs), `science_tm/term2/` (40 PDFs)<br>[Legacy Maths TM Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_tm/term2/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SPLIT_VALIDATED`<br>(120/120 pages) | Ready for Migration |
| **C2-T2-V2-EM** | **Class 2 / Term-II**<br>VOL-II (Maths & EVS EM)<br>Medium: English<br>Pages: 120 | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_EM.pdf#page=2) | **Imprint:** II Government of Tamil Nadu - First Edition 2026; © SCERT 2026<br>**Branch:** `scert/class-02/audit-2026-27`<br>**Path:** `official_editions/2026-27/term2/vol2_maths_evs_em/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term2/vol2_maths_evs_em/pages/page-002.pdf) | **Imprint:** First Edition 2019, Revised 2022<br>**Paths:** `maths_em/term2/` (50 PDFs), `science_em/term2/` (36 PDFs)<br>[Legacy Maths EM Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_em/term2/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SPLIT_VALIDATED`<br>(120/120 pages) | Ready for Migration |
| **C2-T3-V1** | **Class 2 / Term-III**<br>VOL-I (Tamil & English)<br>Medium: Bilingual | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_III_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_III_VOL-I.pdf#page=2) | Official 2026 Term-3 not yet released by government (CDN HTTP 403) | **Imprint:** 2018 / 2022 Edition<br>**Paths:** `tamil/term3/` (56 PDFs), `english/term3/` (63 PDFs)<br>[Legacy Tamil Term 3 Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/tamil/term3/00_prelims/page_02.pdf) | `GET_HTTP_403_PENDING_RELEASE` | **HOLD** (Pending Government Release) |
| **C2-T3-V2-TM** | **Class 2 / Term-III**<br>VOL-II (Maths & EVS TM)<br>Medium: Tamil | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_TM.pdf#page=2) | Official 2026 Term-3 not yet released by government (CDN HTTP 403) | **Imprint:** 2018 / 2022 Edition<br>**Paths:** `maths_tm/term3/` (63 PDFs), `science_tm/term3/` (51 PDFs)<br>[Legacy Maths TM Term 3 Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_tm/term3/00_prelims/page_02.pdf) | `GET_HTTP_403_PENDING_RELEASE` | **HOLD** (Pending Government Release) |
| **C2-T3-V2-EM** | **Class 2 / Term-III**<br>VOL-II (Maths & EVS EM)<br>Medium: English | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_EM.pdf#page=2) | Official 2026 Term-3 not yet released by government (CDN HTTP 403) | **Imprint:** 2018 / 2022 Edition<br>**Paths:** `maths_em/term3/` (63 PDFs), `science_em/term3/` (51 PDFs)<br>[Legacy Maths EM Term 3 Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_em/term3/00_prelims/page_02.pdf) | `GET_HTTP_403_PENDING_RELEASE` | **HOLD** (Pending Government Release) |

---

## 3. Step 3: Questions & Quiz Separation Strategy

- **Legacy Questions (114 files):**
  - All 114 `questions.md` on `main` belong strictly to 2018–2022 editions.
  - They will be migrated 1:1 into `tn-class-02-archive/legacy-2018-2022/`.
  - Zero legacy question files will be copied or linked into 2026 books.
- **2026 Questions:**
  - Audit branch currently has 0 question files under `official_editions/2026-27/`.
  - In accordance with the workflow, Edition Migration does NOT fabricate or re-extract questions. 2026 textbook questions will be added in a separate phase via the Book Back Quiz Workflow.

---

## 4. Step 5: Migration Execution Plan (Awaiting Approval)

### Phase 1 — Archive Ingestion:
1. Target Repo: `Eaglesiva/tn-class-02-archive`
2. Migration Branch: `migration/class-02-legacy-import` (created from `main` SHA `7f3cb55440bb58d6210e8396901c725f87c52c42`)
3. Source: `Eaglesiva/tn-class-02` (`main` SHA `196f8e32ccdbbbcf50a89b83d1da8a509fe42e20`)
4. Files: **1,176 files** (1,044 single-page PDFs + 114 questions.md + 18 `pages.json`) mapped into `legacy-2018-2022/`.
5. Method: Direct Git Tree manipulation via GitHub REST API (Zero local download/clone).

### Phase 2 — Active 2026 Promotion:
1. Target Repo: `Eaglesiva/tn-class-02`
2. Migration Branch: `migration/class-02-edition-upgrade` (created from `main` SHA `196f8e32ccdbbbcf50a89b83d1da8a509fe42e20`)
3. Source: `scert/class-02/audit-2026-27` (Commit `d2e168f2b2f646d4f29ff428caefbb599dd8ed28`)
4. Files: **854 files** (824 single-page PDFs + 30 JSON manifests) promoted to `books/2026-27/`.
5. Remove all legacy subject directories (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`).

### Phase 3 — Post-Migration Audit (Step 7):
1. Verify 100% Git Blob SHA match on all 1,176 archive files.
2. Verify 100% Git Blob SHA match on all 824 2026 page PDFs.
3. Publish `CLASS_02_FINAL_MIGRATION_AUDIT_REPORT.md` on archive migration branch.

### Phase 4 — Main Merge Gate (Step 8):
- **Await explicit user approval** before merging either branch into its respective `main` branch.
