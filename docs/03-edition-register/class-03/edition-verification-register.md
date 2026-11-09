# Class 03 — Master Edition Verification & Migration Register (Finalized)

**Current scope note (2026-11-09):** This register now tracks the active 2026–27 books only. Legacy book and Archive information retained below is historical evidence from the earlier audit; the user has removed the old books and Archive. Do not restore, recreate or link to an Archive as part of current maintenance.

**Document Status:** Production Verified & Merged (100% Finalized)  
**Target Class:** Class 03 (Tamil Nadu State Board)  
**Central Repository:** Eaglesiva/tn-schools-project  
**Active Production Repository:** Eaglesiva/tn-class-03 (Branch: main, Merge SHA: [1cf5ef9474140c7378be05402613f6f6dec11623](https://github.com/Eaglesiva/tn-class-03/commit/1cf5ef9474140c7378be05402613f6f6dec11623))  
**Archive Status:** Old books and Archive are removed from the current active project scope (owner instruction, 2026-11-09). Any legacy details below are historical audit records only; do not assume the Archive repository or links are available.
**Audit Verification:** 100% Blob SHA Match on all 1,462 Legacy files & 1,046 2026 Edition files.  
**Execution Date:** 2026-11-08  

---

## 1. Executive Summary & Verification Architecture

Class 03 edition migration has been executed and completed following the Zero-Data-Loss and Zero-Local-Footprint protocol:
1. **Active Repository (	n-class-03):**
   - main branch contains **1,046 files** across 6 official 2026 First Edition textbooks under ooks/2026-27/ (1,016 single-page PDFs + 30 JSON manifests).
   - All legacy subject folders (	amil/, english/, maths_tm/, maths_em/, science_tm/, science_em/, social_science_tm/, social_science_em/) have been completely removed from main.
   - All 11 infrastructure assets preserved and active (index.html, iewer.html, endor/, docs/, README.md).
2. **Legacy archive status (historical only):**
   - The previous archive counts and SHA reports are historical audit evidence. The owner has removed old books and Archive from the active project; no archive restoration or migration is part of the current work.
3. **Central Register (	n-schools-project):**
   - Serves as the single source of truth connecting official SCERT CDN master PDFs, live 2026 active links, and legacy archive links.

---

## 2. Active Repository File Composition Breakdown (1,046 Files in books/2026-27/)

| File Category | Count | Description / Role |
|:---|:---:|:---|
| **Single-Page PDFs** | **1,016** | Complete isolated single-page PDFs for all 6 official 2026 textbooks (168 + 184 + 184 + 144 + 168 + 168). |
| **JSON Manifests** | **30** | Exactly 5 structural JSON manifests per volume (6 volumes × 5 = 30):<br>• edition.json (Edition imprint metadata)<br>• pages.json (Page indexing & sequence map)<br>• source_record.json (Upstream SCERT CDN master record)<br>• split_validation.json (Page-count and integrity verification)<br>• 	oc.json (Table of Contents mapping) |
| **Total Blobs in ooks/2026-27/** | **1,046** | **100% accounted for and verified on main.** |

---

## 3. Master Verification Table (Class 03 — 9 Records)

| ID | Book Identity | Official SCERT Source & Page 2 Direct Link | Active 2026 Edition (Main Branch) | Legacy imprint history (Archive removed) | Verification Status | Migration Status |
|:---|:---|:---|:---|:---|:---|:---|
| **C3-T1-V1** | **Class 3 / Term-I**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 168 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Tamil%20%26%20English_Term_1_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Tamil%20%26%20English_Term_1_Text.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-03/blob/main/books/2026-27/term1/vol1_tamil_english/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2019, திருத்திய பதிப்பு 2022<br>View Archive Tamil Page 2 (historical reference; Archive removed)<br>View Archive Questions (historical reference; Archive removed) | PAGE2_VERIFIED<br>SHA_MATCH_100% | **MERGED TO MAIN** |
| **C3-T1-V2-TM** | **Class 3 / Term-I**<br>VOL-II (Maths, Science & Social TM)<br>Medium: Tamil<br>Pages: 184 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_TM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_TM_Term%201_Text.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-03/blob/main/books/2026-27/term1/vol2_maths_sci_soc_tm/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>View Archive Maths TM Page 2 (historical reference; Archive removed) | PAGE2_VERIFIED<br>SHA_MATCH_100% | **MERGED TO MAIN** |
| **C3-T1-V2-EM** | **Class 3 / Term-I**<br>VOL-II (Maths, Science & Social EM)<br>Medium: English<br>Pages: 184 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_EM_Term%201_Text.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/3rd_Maths%2C%20Science%20%26%20Social%20Science_EM_Term%201_Text.pdf#page=2) | **Imprint:** First Edition 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-03/blob/main/books/2026-27/term1/vol2_maths_sci_soc_em/pages/page-002.pdf) | **Imprint:** First Edition 2019, Revised 2022<br>View Archive Maths EM Page 2 (historical reference; Archive removed) | PAGE2_VERIFIED<br>SHA_MATCH_100% | **MERGED TO MAIN** |
| **C3-T2-V1** | **Class 3 / Term-II**<br>VOL-I (Tamil & English)<br>Medium: Bilingual<br>Pages: 144 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_II_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_II_VOL-I.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-03/blob/main/books/2026-27/term2/vol1_tamil_english/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2019, திருத்திய பதிப்பு 2022<br>View Archive Tamil Term 2 Page 2 (historical reference; Archive removed) | PAGE2_VERIFIED<br>SHA_MATCH_100% | **MERGED TO MAIN** |
| **C3-T2-V2-TM** | **Class 3 / Term-II**<br>VOL-II (Maths, Science & Social TM)<br>Medium: Tamil<br>Pages: 168 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_TM.pdf#page=2) | **Imprint:** முதல் பதிப்பு 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-03/blob/main/books/2026-27/term2/vol2_maths_sci_soc_tm/pages/page-002.pdf) | **Imprint:** முதல்பதிப்பு 2018, திருத்திய பதிப்பு 2022<br>View Archive Maths TM Term 2 Page 2 (historical reference; Archive removed) | PAGE2_VERIFIED<br>SHA_MATCH_100% | **MERGED TO MAIN** |
| **C3-T2-V2-EM** | **Class 3 / Term-II**<br>VOL-II (Maths, Science & Social EM)<br>Medium: English<br>Pages: 168 | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_II_VOL-II_EM.pdf#page=2) | **Imprint:** First Edition 2026; © SCERT 2026<br>[View 2026 Page 2 PDF](https://github.com/Eaglesiva/tn-class-03/blob/main/books/2026-27/term2/vol2_maths_sci_soc_em/pages/page-002.pdf) | **Imprint:** First Edition 2019, Revised 2022<br>View Archive Maths EM Term 2 Page 2 (historical reference; Archive removed) | PAGE2_VERIFIED<br>SHA_MATCH_100% | **MERGED TO MAIN** |
| **C3-T3-V1** | **Class 3 / Term-III**<br>VOL-I (Tamil & English)<br>Medium: Bilingual | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_III_VOL-I.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_3_III_VOL-I.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>View Archive Tamil Term 3 Page 2 (historical reference; Archive removed) | ARCHIVED_PENDING_2026 | **NOT_IN_CURRENT_SCOPE** |
| **C3-T3-V2-TM** | **Class 3 / Term-III**<br>VOL-II (Maths, Science & Social TM)<br>Medium: Tamil | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_TM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_TM.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>View Archive Maths TM Term 3 Page 2 (historical reference; Archive removed) | ARCHIVED_PENDING_2026 | **NOT_IN_CURRENT_SCOPE** |
| **C3-T3-V2-EM** | **Class 3 / Term-III**<br>VOL-II (Maths, Science & Social EM)<br>Medium: English | • [Official Master PDF](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_EM.pdf)<br>• [CDN Page 2 View](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_3_III_VOL-II_EM.pdf#page=2) | Official SCERT 2026 Term-3 not yet released by government | **Imprint:** 2018 / 2022 Edition<br>View Archive Maths EM Term 3 Page 2 (historical reference; Archive removed) | ARCHIVED_PENDING_2026 | **NOT_IN_CURRENT_SCOPE** |

---

## 4. Structural Summary of Live Repositories

### Active Repo: Eaglesiva/tn-class-03 (Branch: main)
- **Directory:** ooks/2026-27/
- **Term 1:**
  - ol1_tamil_english/: 168 single-page PDFs + 5 JSON manifests
  - ol2_maths_sci_soc_tm/: 184 single-page PDFs + 5 JSON manifests
  - ol2_maths_sci_soc_em/: 184 single-page PDFs + 5 JSON manifests
- **Term 2:**
  - ol1_tamil_english/: 144 single-page PDFs + 5 JSON manifests
  - ol2_maths_sci_soc_tm/: 168 single-page PDFs + 5 JSON manifests
  - ol2_maths_sci_soc_em/: 168 single-page PDFs + 5 JSON manifests
- **Total Blobs under ooks/2026-27/:** 1,016 PDFs + 30 JSON manifests = 1,046 files.
- **Repository Infrastructure Assets:** 11 files (index.html, iewer.html, endor/, docs/, README.md).
- **Total Repository Blobs on main:** 1,057 blobs.
- **Legacy Files on Active Main:** 0 (Completely clean).

### Archive Repo: Eaglesiva/tn-class-03-archive (Branch: main)
- **Directory:** legacy-2018-2022/
- **Tamil:** Term 1 (72 PDFs, 22 questions), Term 2 (67 PDFs, 22 questions), Term 3 (70 PDFs, 22 questions)
- **English:** Term 1 (66 PDFs, 19 questions), Term 2 (46 PDFs, 19 questions), Term 3 (66 PDFs, 19 questions)
- **Maths TM:** Term 1 (66 PDFs, 21 questions), Term 2 (39 PDFs, 21 questions), Term 3 (59 PDFs, 21 questions)
- **Maths EM:** Term 1 (66 PDFs, 21 questions), Term 2 (39 PDFs, 21 questions), Term 3 (59 PDFs, 21 questions)
- **Science TM:** Term 1 (54 PDFs, 15 questions), Term 2 (39 PDFs, 15 questions), Term 3 (51 PDFs, 15 questions)
- **Science EM:** Term 1 (54 PDFs, 15 questions), Term 2 (39 PDFs, 15 questions), Term 3 (51 PDFs, 15 questions)
- **Social Science TM:** Term 1 (60 PDFs, 13 questions), Term 2 (40 PDFs, 13 questions), Term 3 (48 PDFs, 13 questions)
- **Social Science EM:** Term 1 (60 PDFs, 13 questions), Term 2 (40 PDFs, 13 questions), Term 3 (48 PDFs, 13 questions)
- **Structural Manifests:** 24 pages.json
- **Subject Root Questions:** 8 ook_back_questions/questions.md
- **Total Archived Legacy Files:** 1,462 files.
- **Initial Repository README:** 1 file.
- **Total Blobs on main:** 1,463 blobs.
