# Class 02 — Master Edition Verification & Migration Register (Draft)

**Document Type:** Pilot Master Register (Rough Draft for Review)  
**Target Class:** Class 02 (Tamil Nadu State Board)  
**Central Repository:** `Eaglesiva/tn-schools-project`  
**Active Repository:** `Eaglesiva/tn-class-02` (Main Commit: `196f8e32ccdbbbcf50a89b83d1da8a509fe42e20`)  
**Archive Repository:** `Eaglesiva/tn-class-02-archive` (Main Commit: `7f3cb55440bb58d6210e8396901c725f87c52c42`)  
**Audit Source Branch:** `scert/class-02/audit-2026-27` (Commit: `d2e168f2b2f646d4f29ff428caefbb599dd8ed28`)  
**Current Gate:** **STEP 0 (PRE-WORK GATE) & STEP 1 (BOOK INVENTORY) ONLY — ZERO FILES MOVED / NO COMMITS TO ACTIVE BRANCHES**

---

## 1. Step 0: Pre-Work Gate Summary

1. **Repository Mapping:**
   - Active Repo: `Eaglesiva/tn-class-02` (Default branch: `main`)
   - Archive Repo: `Eaglesiva/tn-class-02-archive` (Default branch: `main`)
   - Central Register: `Eaglesiva/tn-schools-project` (`docs/03-edition-register/class-02/`)
2. **Existing Branches & Assets:**
   - `tn-class-02` contains verified audit branch: `scert/class-02/audit-2026-27` (Commit `d2e168f2b2f646d4f29ff428caefbb599dd8ed28`).
   - Audit branch already contains **824 single-page PDFs** across all 6 released 2026 books under `official_editions/2026-27/` + 30 JSON manifests.
   - `tn-class-02/main` contains **1,176 legacy files** (1,044 single-page PDFs + 114 legacy questions markdown + 18 `pages.json`).
3. **Safety Constraints:**
   - Strict NO-CLONE, NO-DOWNLOAD, GITHUB-API-ONLY policy maintained.
   - Zero files moved, renamed, deleted, or merged.

---

## 2. Step 1: Complete Book Inventory (Class 02 — 9 In-Scope Records)

| ID | Book Identity | Term & Volume | Medium | Official SCERT Master CDN URL & Page 2 Direct Link | Official Pages | 2026 Edition Source Location (Audit Branch) | Current Legacy Baseline Location (`main` branch) | Legacy Baseline Pages | Edition & Evidence Status | Migration Readiness |
|:---|:---|:---:|:---:|:---|:---:|:---|:---|:---:|:---:|:---:|
| **C2-T1-V1** | **Class 2 / Term-I**<br>VOL-I (Tamil & English) | Term 1<br>Vol 1 | Bilingual | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Tamil%20&%20English%20Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Tamil%20&%20English%20Term%201_Text.pdf#page=2) | **160** | `official_editions/2026-27/term1/vol1_tamil_english/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term1/vol1_tamil_english/pages/page-002.pdf) | `tamil/term1/`<br>`english/term1/`<br>[Legacy Tamil Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/tamil/term1/00_prelims/page_02.pdf) | 160<br>(82 Tam + 78 Eng) | `PAGE2_VERIFIED`<br>2026 Imprint vs 2019/2022 Legacy | Ready for Draft Review |
| **C2-T1-V2-TM** | **Class 2 / Term-I**<br>VOL-II (Maths & EVS TM) | Term 1<br>Vol 2 | Tamil | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd_Maths%20&%20EVS_TM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd_Maths%20&%20EVS_TM_Term%201_Text.pdf#page=2) | **144** | `official_editions/2026-27/term1/vol2_maths_evs_tm/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term1/vol2_maths_evs_tm/pages/page-002.pdf) | `maths_tm/term1/`<br>`science_tm/term1/`<br>[Legacy Maths Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_tm/term1/00_prelims/page_02.pdf) | 130<br>(76 Mat + 54 Sci) | `PAGE2_VERIFIED`<br>2026 Imprint vs 2018/2022 Legacy | Ready for Draft Review |
| **C2-T1-V2-EM** | **Class 2 / Term-I**<br>VOL-II (Maths & EVS EM) | Term 1<br>Vol 2 | English | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Maths%20&%20Environmental%20Science_Term-1_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/2nd%20Maths%20&%20Environmental%20Science_Term-1_Text.pdf#page=2) | **144** | `official_editions/2026-27/term1/vol2_maths_evs_em/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term1/vol2_maths_evs_em/pages/page-002.pdf) | `maths_em/term1/`<br>`science_em/term1/`<br>[Legacy Maths EM Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_em/term1/00_prelims/page_02.pdf) | 130<br>(76 Mat + 54 Sci) | `PAGE2_VERIFIED`<br>2026 Imprint vs 2019/2022 Legacy | Ready for Draft Review |
| **C2-T2-V1** | **Class 2 / Term-II**<br>VOL-I (Tamil & English) | Term 2<br>Vol 1 | Bilingual | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_II_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_II_VOL-I.pdf#page=2) | **136** | `official_editions/2026-27/term2/vol1_tamil_english/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term2/vol1_tamil_english/pages/page-002.pdf) | `tamil/term2/`<br>`english/term2/`<br>[Legacy Tamil Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/tamil/term2/00_prelims/page_02.pdf) | 97<br>(50 Tam + 47 Eng) | `PAGE2_VERIFIED`<br>2026 Imprint vs 2019/2022 Legacy | Ready for Draft Review |
| **C2-T2-V2-TM** | **Class 2 / Term-II**<br>VOL-II (Maths & EVS TM) | Term 2<br>Vol 2 | Tamil | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_TM.pdf#page=2) | **120** | `official_editions/2026-27/term2/vol2_maths_evs_tm/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term2/vol2_maths_evs_tm/pages/page-002.pdf) | `maths_tm/term2/`<br>`science_tm/term2/`<br>[Legacy Maths TM Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_tm/term2/00_prelims/page_02.pdf) | 90<br>(50 Mat + 40 Sci) | `PAGE2_VERIFIED`<br>2026 Imprint vs 2018/2022 Legacy | Ready for Draft Review |
| **C2-T2-V2-EM** | **Class 2 / Term-II**<br>VOL-II (Maths & EVS EM) | Term 2<br>Vol 2 | English | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_II_VOL-II_EM.pdf#page=2) | **120** | `official_editions/2026-27/term2/vol2_maths_evs_em/`<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-02/blob/d2e168f2b2f646d4f29ff428caefbb599dd8ed28/official_editions/2026-27/term2/vol2_maths_evs_em/pages/page-002.pdf) | `maths_em/term2/`<br>`science_em/term2/`<br>[Legacy Maths EM Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_em/term2/00_prelims/page_02.pdf) | 86<br>(50 Mat + 36 Sci) | `PAGE2_VERIFIED`<br>2026 Imprint vs 2019/2022 Legacy | Ready for Draft Review |
| **C2-T3-V1** | **Class 2 / Term-III**<br>VOL-I (Tamil & English) | Term 3<br>Vol 1 | Bilingual | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_III_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_2_III_VOL-I.pdf#page=2) | — | Official 2026 Term-3 not yet released by government (CDN HTTP 403) | `tamil/term3/`<br>`english/term3/`<br>[Legacy Tamil Term 3 Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/tamil/term3/00_prelims/page_02.pdf) | 119<br>(56 Tam + 63 Eng) | `GET_HTTP_403_PENDING_RELEASE`<br>(Keep legacy in archive/active until official release) | **HOLD** (Pending Government Release) |
| **C2-T3-V2-TM** | **Class 2 / Term-III**<br>VOL-II (Maths & EVS TM) | Term 3<br>Vol 2 | Tamil | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_TM.pdf#page=2) | — | Official 2026 Term-3 not yet released by government (CDN HTTP 403) | `maths_tm/term3/`<br>`science_tm/term3/`<br>[Legacy Maths TM Term 3 Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_tm/term3/00_prelims/page_02.pdf) | 105<br>(63 Mat + 42 Sci) | `GET_HTTP_403_PENDING_RELEASE`<br>(Keep legacy in archive/active until official release) | **HOLD** (Pending Government Release) |
| **C2-T3-V2-EM** | **Class 2 / Term-III**<br>VOL-II (Maths & EVS EM) | Term 3<br>Vol 2 | English | • [Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_2_III_VOL-II_EM.pdf#page=2) | — | Official 2026 Term-3 not yet released by government (CDN HTTP 403) | `maths_em/term3/`<br>`science_em/term3/`<br>[Legacy Maths EM Term 3 Page 2](https://github.com/Eaglesiva/tn-class-02/blob/196f8e32ccdbbbcf50a89b83d1da8a509fe42e20/maths_em/term3/00_prelims/page_02.pdf) | 105<br>(63 Mat + 42 Sci) | `GET_HTTP_403_PENDING_RELEASE`<br>(Keep legacy in archive/active until official release) | **HOLD** (Pending Government Release) |

---

## 3. Inventory Reconciliation Summary

- **Total State Board Academic Books in Scope:** 9
- **2026 Books Already Audited & Split on Branch `scert/class-02/audit-2026-27`:** 6 books (**824 single-page PDFs**)
- **2026 Books Awaiting SCERT Term-III Release:** 3 books (Official CDN returns HTTP 403 Forbidden)
- **Legacy Files Cataloged on `tn-class-02/main` for Future Archiving:** **1,176 files**
  - 1,044 single-page PDFs (Tamil: 188, English: 188, Maths TM: 189, Maths EM: 189, Science TM: 145, Science EM: 145)
  - 114 questions markdown files (`book_back_questions/questions.md`)
  - 18 structural `pages.json` manifests
- **Current Action:** Draft Review. Zero files moved or modified.
