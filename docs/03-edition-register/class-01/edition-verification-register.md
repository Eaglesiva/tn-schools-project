# Class 01 — Master Edition Verification & Migration Register (Finalized)

**Current scope note (2026-11-09):** This register now tracks the active 2026–27 books only. Legacy book and Archive information retained below is historical evidence from the earlier audit; the user has removed the old books and Archive. Do not restore, recreate or link to an Archive as part of current maintenance.

**Document Status:** Production Verified & Merged (100% Finalized)  
**Target Class:** Class 01 (Tamil Nadu State Board)  
**Central Repository:** `Eaglesiva/tn-schools-project`  
**Active Production Repository:** `Eaglesiva/tn-class-01` (Branch: `main`, Merge SHA: `b20b8d38a2decd66db25e8053318027d23a04c1e`)  
**Archive Status:** Old books and Archive are removed from the current active project scope (owner instruction, 2026-11-09). Any legacy details below are historical audit records only; do not assume the Archive repository or links are available.
**Audit Verification:** 100% Blob SHA Match on all 1,189 Legacy files & 848 2026 Edition Page PDFs.  
**Execution Date:** 2026-11-07 / 2026-11-08  

---

## 1. Executive Summary & Verification Architecture

Class 01 migration has been executed and completed following the Zero-Data-Loss and Zero-Local-Footprint protocol:
1. **Active Repository (`tn-class-01`):**
   - `main` branch contains **884 files** across 6 official 2026 First Edition textbooks under `books/2026-27/`.
   - All legacy subject folders (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`) have been completely removed from `main`.
2. **Legacy archive status (historical only):**
   - The previous archive counts and SHA reports are historical audit evidence. The owner has removed old books and Archive from the active project; no archive restoration or migration is part of the current work.
3. **Central Register (`tn-schools-project`):**
   - Serves as the current source of truth for active 2026 book links, official SCERT sources and Page-2 evidence. Legacy archive references are historical only.

---

## 2. Active Repository File Composition Breakdown (884 Files)

| File Category | Count | Description / Role |
|:---|:---:|:---|
| **Single-Page PDFs** | **848** | Complete isolated single-page PDFs for all 6 official 2026 textbooks (176 + 144 + 144 + 144 + 120 + 120). |
| **Questions Markdown** | **6** | Verified 2026 book-back primer question sets located at `book_back_questions/questions.md` for each book. |
| **JSON Manifests** | **30** | Exactly 5 structural JSON manifests per volume (6 volumes × 5 = 30):<br>• `edition.json` (Edition imprint metadata)<br>• `pages.json` (Page indexing & sequence map)<br>• `source_record.json` (Upstream SCERT CDN master record)<br>• `split_validation.json` (Page-count and integrity verification)<br>• `toc.json` (Table of Contents mapping) |
| **Total Blobs in `books/2026-27/`** | **884** | **100% accounted for and verified.** |

---

## 3. Master Verification Table (Class 01 — 9 Records)

| ID | Book Identity | Official SCERT Source & Page 2 Direct Link | Active 2026 Edition (Main Branch) | Legacy imprint history (Archive removed) | Verification Status | Migration Status |
|:---|:---|:---|:---|:---|:---|:---|
| **C1-T1-V1** | **Class 1 / Term-I**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 176 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Tamil%20&%20English%20Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Tamil%20&%20English%20Term%201_Text.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol1_tamil_english/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol1_tamil_english/book_back_questions/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>View Archive Tamil Page 2 (historical reference; Archive removed)<br>View Archive Questions (historical reference; Archive removed) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T1-V2-TM** | **Class 1 / Term-I**<br>VOL-II (Maths & EVS)<br>Medium: Tamil<br>Pages: 144 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_TM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_TM_Term%201_Text.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_tm/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_tm/book_back_questions/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>View Archive Maths Page 2 (historical reference; Archive removed) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T1-V2-EM** | **Class 1 / Term-I**<br>VOL-II (Maths & EVS)<br>Medium: English<br>Pages: 144 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_EM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/1st_Maths%20&%20EVS_EM_Term%201_Text.pdf#page=2) | **Imprint:** First Edition 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_em/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term1/vol2_maths_evs_em/book_back_questions/questions.md) | **Imprint:** First Edition 2018, Revised 2022<br>View Archive Maths Page 2 (historical reference; Archive removed) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T2-V1** | **Class 1 / Term-II**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 144 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_II_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_II_VOL-I.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol1_tamil_english/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol1_tamil_english/book_back_questions/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>View Archive Tamil Page 2 (historical reference; Archive removed)<br>View Archive Questions (historical reference; Archive removed) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T2-V2-TM** | **Class 1 / Term-II**<br>VOL-II (Maths & EVS)<br>Medium: Tamil<br>Pages: 120 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_TM.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_tm/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_tm/book_back_questions/questions.md) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>View Archive Maths Page 2 (historical reference; Archive removed) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T2-V2-EM** | **Class 1 / Term-II**<br>VOL-II (Maths & EVS)<br>Medium: English<br>Pages: 120 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_II_VOL-II_EM.pdf#page=2) | **Imprint:** First Edition 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_em/pages/page-002.pdf)<br>[View 2026 Questions](https://github.com/Eaglesiva/tn-class-01/blob/main/books/2026-27/term2/vol2_maths_evs_em/book_back_questions/questions.md) | **Imprint:** First Edition 2018, Revised 2022<br>View Archive Maths Page 2 (historical reference; Archive removed) | `PAGE2_VERIFIED`<br>`SHA_MATCH_100%` | **MERGED TO MAIN** |
| **C1-T3-V1** | **Class 1 / Term-III**<br>VOL-I (Tamil & English)<br>Medium: Bilingual | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_III_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20&%20ENGLISH_1_III_VOL-I.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>View Archive Tamil Page 2 (historical reference; Archive removed) | `TERM_III_STATUS_RECHECK_REQUIRED` | **NOT_IN_CURRENT_SCOPE** |
| **C1-T3-V2-TM** | **Class 1 / Term-III**<br>VOL-II (Maths & EVS)<br>Medium: Tamil | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_TM.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>View Archive Maths Page 2 (historical reference; Archive removed) | `TERM_III_STATUS_RECHECK_REQUIRED` | **NOT_IN_CURRENT_SCOPE** |
| **C1-T3-V2-EM** | **Class 1 / Term-III**<br>VOL-II (Maths & EVS)<br>Medium: English | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%20&%20EVS_1_III_VOL-II_EM.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>View Archive Maths Page 2 (historical reference; Archive removed) | `TERM_III_STATUS_RECHECK_REQUIRED` | **NOT_IN_CURRENT_SCOPE** |

---

## 4. Structural Summary of Live Repositories

### Active Repo: `Eaglesiva/tn-class-01` (Branch: `main`)
- **Directory:** `books/2026-27/`
- **Term 1:**
  - `vol1_tamil_english/`: 176 single-page PDFs + 1 `book_back_questions/questions.md` + 5 JSON manifests
  - `vol2_maths_evs_tm/`: 144 single-page PDFs + 1 `book_back_questions/questions.md` + 5 JSON manifests
  - `vol2_maths_evs_em/`: 144 single-page PDFs + 1 `book_back_questions/questions.md` + 5 JSON manifests
- **Term 2:**
  - `vol1_tamil_english/`: 144 single-page PDFs + 1 `book_back_questions/questions.md` + 5 JSON manifests
  - `vol2_maths_evs_tm/`: 120 single-page PDFs + 1 `book_back_questions/questions.md` + 5 JSON manifests
  - `vol2_maths_evs_em/`: 120 single-page PDFs + 1 `book_back_questions/questions.md` + 5 JSON manifests
- **Total Blobs:** 848 PDFs + 6 Questions Markdown + 30 JSON manifests = 884 files.
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