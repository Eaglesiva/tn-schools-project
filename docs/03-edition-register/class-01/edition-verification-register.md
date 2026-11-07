# Class 01 — Master Edition Verification & Migration Register (Finalized)

**Document Status:** Production Verified & Merged  
**Target Class:** Class 01 (Tamil Nadu State Board)  
**Central Repository:** `Eaglesiva/tn-schools-project`  
**Active Production Repository:** `Eaglesiva/tn-class-01` (Branch: `main`)  
**Legacy Archive Repository:** `Eaglesiva/tn-class-01-archive` (Branch: `main`)  
**Audit Verification:** 100% Blob SHA Match on all 1,189 Legacy files & 848 2026 Edition Page PDFs.  
**Execution Date:** 2026-11-07  

---

## 1. Executive Summary & Verification Architecture

Class 01 migration has been completed following the Zero-Data-Loss and Zero-Local-Footprint protocol:
1. **Active Repository (`tn-class-01`):**
   - `main` branch now contains **848 single-page PDFs** across 6 official 2026 First Edition textbooks under `books/2026-27/`.
   - Contains 6 verified 2026 textbook primer question sets (`questions.md`).
   - All legacy subject folders (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`) have been completely removed.
2. **Archive Repository (`tn-class-01-archive`):**
   - `main` branch securely archives **all 1,189 legacy files** (1,062 single-page PDFs, 109 legacy question markdown files, 18 `pages.json` manifests) under `legacy-2018-2022/`.
   - Every file maintains 100% Git Blob SHA equality with the pre-migration source tree.
3. **Central Register (`tn-schools-project`):**
   - Serves as the single source of truth connecting official SCERT CDN master PDFs, live 2026 active links, and legacy archive links.

---

## 2. Master Verification Table (Class 01 — 9 Records)

| ID | Book Identity | Official SCERT Source & Page 2 Direct Link | Active 2026 Edition (Main Branch) | Legacy Archive (Main Branch) | Verification Status | Migration Status |
|:---|:---|:---|:---|:---|:---|:---|
| **C1-T1-V1** | **Class 1 / Term-I**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 176 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Tamil%20&%20English%20Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Tamil%20&%20English%20Term%201_Text.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol1_tamil_english/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol1_tamil_english/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>[View Archive Tamil Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/tamil/term1/00_prelims/page_02.pdf)<br>[View Archive Questions](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/tamil/term1/01_paadi_aadi_vilaiyaadalaam/book_back_questions/questions.md) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T1-V2-TM** | **Class 1 / Term-I**<br>VOL-II (Maths & EVS)<br>Medium: Tamil<br>Pages: 144 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_TM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_TM_Term%201_Text.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_tm/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_tm/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>[View Archive Maths Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/maths_tm/term1/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T1-V2-EM** | **Class 1 / Term-I**<br>VOL-II (Maths & EVS)<br>Medium: English<br>Pages: 144 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_EM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_EM_Term%201_Text.pdf#page=2) | **Imprint:** First Edition 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_em/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_em/questions.md) | **Imprint:** First Edition 2018, Revised 2022<br>[View Archive Maths Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/maths_em/term1/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T2-V1** | **Class 1 / Term-II**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 144 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_II_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_II_VOL-I.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol1_tamil_english/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol1_tamil_english/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>[View Archive Tamil Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/tamil/term2/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T2-V2-TM** | **Class 1 / Term-II**<br>VOL-II (Maths & EVS)<br>Medium: Tamil<br>Pages: 120 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_TM.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_tm/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_tm/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>[View Archive Maths Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/maths_tm/term2/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T2-V2-EM** | **Class 1 / Term-II**<br>VOL-II (Maths & EVS)<br>Medium: English<br>Pages: 120 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_EM.pdf#page=2) | **Imprint:** First Edition 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_em/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_em/questions.md) | **Imprint:** First Edition 2018, Revised 2022<br>[View Archive Maths Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/maths_em/term2/00_prelims/page_02.pdf) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T3-V1** | **Class 1 / Term-III**<br>VOL-I (Tamil & English)<br>Medium: Bilingual | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_III_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_III_VOL-I.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>[View Archive Tamil Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/tamil/term3/00_prelims/page_02.pdf) | `ARCHIVED_PENDING_2026` | **PRESERVED IN ARCHIVE** |
| **C1-T3-V2-TM** | **Class 1 / Term-III**<br>VOL-II (Maths & EVS)<br>Medium: Tamil | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_TM.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>[View Archive Maths Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/maths_tm/term3/00_prelims/page_02.pdf) | `ARCHIVED_PENDING_2026` | **PRESERVED IN ARCHIVE** |
| **C1-T3-V2-EM** | **Class 1 / Term-III**<br>VOL-II (Maths & EVS)<br>Medium: English | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_EM.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>[View Archive Maths Page 2](https://github.com/Eaglesiva/tn-class-01-archive/blob/main/legacy-2018-2022/maths_em/term3/00_prelims/page_02.pdf) | `ARCHIVED_PENDING_2026` | **PRESERVED IN ARCHIVE** |

---

## 3. Structural Summary of Live Repositories

### Active Repo: `Eaglesiva/tn-class-01` (Branch: `main`)
- **Directory:** `books/2026-27/`
- **Term 1:**
  - `vol1_tamil_english/`: 176 single-page PDFs + `questions.md`
  - `vol2_maths_evs_tm/`: 144 single-page PDFs + `questions.md`
  - `vol2_maths_evs_em/`: 144 single-page PDFs + `questions.md`
- **Term 2:**
  - `vol1_tamil_english/`: 144 single-page PDFs + `questions.md`
  - `vol2_maths_evs_tm/`: 120 single-page PDFs + `questions.md`
  - `vol2_maths_evs_em/`: 120 single-page PDFs + `questions.md`
- **Total 2026 Content Files:** 848 single-page PDFs + 6 questions markdown files = 854 content files.
- **Legacy Files on Active Main:** 0 (Completely clean).

### Archive Repo: `Eaglesiva/tn-class-01-archive` (Branch: `main`)
- **Directory:** `legacy-2018-2022/`
- **Tamil:** Term 1 (81 PDFs, 41 questions), Term 2 (69 PDFs, 21 questions), Term 3 (75 PDFs, 26 questions)
- **English:** Term 1 (65 PDFs), Term 2 (65 PDFs), Term 3 (59 PDFs)
- **Maths TM:** Term 1 (66 PDFs, 5 questions), Term 2 (52 PDFs, 5 questions), Term 3 (68 PDFs, 5 questions)
- **Maths EM:** Term 1 (66 PDFs), Term 2 (52 PDFs), Term 3 (67 PDFs)
- **Science TM:** Term 1 (64 PDFs, 2 questions), Term 2 (38 PDFs, 2 questions), Term 3 (2 questions)
- **Science EM:** Term 1 (64 PDFs), Term 2 (36 PDFs), Term 3 (49 PDFs)
- **Structural Manifests:** 18 `pages.json`
- **Total Archived Legacy Files:** 1,189 files.