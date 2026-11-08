# Class 04 — Master Edition Verification Register & Pre-Migration Baseline Inventory (Draft: Step 0 & Step 1 Only)

**Document Role:** Central Edition Register & Pre-Migration Baseline Inventory  
**Target Class:** Class 04 (Standard 4 / நான்காம் வகுப்பு)  
**Curriculum Authority:** State Council of Educational Research and Training (SCERT), Tamil Nadu  
**Publishing Authority:** Tamil Nadu Textbook and Educational Services Corporation  
**Central Repository:** `Eaglesiva/tn-schools-project`  
**Active Textbook Repository:** `Eaglesiva/tn-class-04`  
**Permanent Archive Repository:** `Eaglesiva/tn-class-04-archive`  
**Workflow Blueprint:** [`docs/02-workflow/scert-edition-migration/SCERT_EDITION_MIGRATION_WORKFLOW_TA.md`](https://github.com/Eaglesiva/tn-schools-project/blob/main/docs/02-workflow/scert-edition-migration/SCERT_EDITION_MIGRATION_WORKFLOW_TA.md)  
**Verification Date:** 2026-11-08  
**Verification Status:** **STEP 0 & STEP 1 COMPLETED (100% READ-ONLY BASELINE AUDIT — ZERO FILES MOVED / NO COMMITS ON MAIN / NO BRANCH MERGES)**  
**Branch Location:** `draft/class-04-edition-register` (Dedicated docs-only review branch; `main` branch remains untouched)

---

## 1. Pre-Migration Repositories Baseline State (Step 0)

All Git Commit SHAs, branch heads, and blob inventories verified live directly via GitHub REST / Git Database API:

| Repository | Branch | Git Commit SHA | Total Blobs | Content Classification & Tree Composition |
|:---|:---|:---|:---:|:---|
| **`Eaglesiva/tn-class-04`** | `main` | [`426c58bdd809fcb808519c346ea33ab1b2dd0b4d`](https://github.com/Eaglesiva/tn-class-04/commit/426c58bdd809fcb808519c346ea33ab1b2dd0b4d) | **1,466** | **Full Main Inventory (1,455 Legacy Payload + 11 Infrastructure Assets):**<br>• **1,300** Single-page PDFs across 8 subjects (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`, `social_science_tm/`, `social_science_em/`)<br>• **131** Legacy `questions.md` files (46 in T1, 39 in T2, 38 in T3, 8 in root)<br>• **24** Legacy `pages.json` manifests (8 in T1, 8 in T2, 8 in T3)<br>• **6** Repository Documentation files (`README.md`, `docs/`)<br>• **1** Audit manifest CSV (`docs/edition-audit/2026-27/class_04_2026_27_audit_manifest.csv`)<br>• **2** Web UI HTML assets (`index.html`, `viewer.html`)<br>• **2** JavaScript assets (`vendor/pdfjs/pdf.min.js`, `vendor/pdfjs/pdf.worker.min.js`) |
| **`Eaglesiva/tn-class-04`** | `scert/class-04/audit-2026-27` | [`86ce7d415766a3639553c7d59a1ccdf32008036b`](https://github.com/Eaglesiva/tn-class-04/commit/86ce7d415766a3639553c7d59a1ccdf32008036b) | **1,952** | **Existing 2026 Pre-Audited Staging Branch Composition:**<br>• **1,460** blobs sharing identical paths with `main`<br>• **487** new Official 2026–27 Academic Distribution blobs under `official_editions/2026-27/` (**472** single-page PDFs + **15** JSON manifests across 3 Term-I combined volumes)<br>• **5** audit-only blobs (`.github/workflows/scert-audit-class4.yml`, `.github/scripts/audit_class4_comprehensive.py`, `class_04_audit_summary.md`, `class_04_official_api_snapshot.json`, `class_04_2026_27_audit_manifest.csv`) |
| **`Eaglesiva/tn-class-04-archive`** | `main` | [`a3d511cbac741c15c8c238d2284e8733b05f6174`](https://github.com/Eaglesiva/tn-class-04-archive/commit/a3d511cbac741c15c8c238d2284e8733b05f6174) | **1** | **Initial Clean Archive Repository:** Holds initial `README.md` only (blob `0b5f394b`); ready to ingest legacy textbook files into `legacy-2018-2022/`. |

### Main Branch Documentation Integrity Protection
The following **11 infrastructure files** on `tn-class-04/main` are active repository governance assets. They must be strictly preserved during active edition promotion and must NEVER be archived or deleted:
1. `README.md`
2. `docs/BOOK_EDITION_VERIFICATION_RULES_TA.md`
3. `docs/PROJECT_BLUEPRINT_COMMON_TA.md`
4. `docs/README.md`
5. `docs/edition-audit/2026-27/README.md`
6. `docs/edition-audit/2026-27/class_04_audit_summary.md`
7. `docs/edition-audit/2026-27/class_04_2026_27_audit_manifest.csv`
8. `index.html` (Class Portal Web Entry)
9. `viewer.html` (Document Viewer Engine)
10. `vendor/pdfjs/pdf.min.js` (Offline PDF.js Library)
11. `vendor/pdfjs/pdf.worker.min.js` (Offline PDF.js Worker)

---

## 2. Live SCERT Official API Retrieval Evidence (2026-11-08)

The upstream government education portal API (`https://emis3.tnschools.gov.in/api/get_scert_books`) was queried live:

* **Retrieval UTC Timestamp:** `2026-11-08T10:21:56.699564+00:00`
* **HTTP Status:** `200 OK`
* **Response Headers:**
  - `Date: Sun, 08 Nov 2026 10:21:57 GMT`
  - `Server: Apache / PHP`
  - `Content-Type: application/json; charset=utf-8`
  - `Cache-Control: no-store, no-cache, must-revalidate`
  - `Expires: Thu, 19 Nov 1981 08:52:00 GMT`
* **Raw Response Size:** `208,374 bytes`
* **Raw Response Bytes SHA-256:** `404f283443b1f7a6a0fae814092aae556d0419ad2b4b2c0b0a0f7ebd756cc3e4` (Calculated directly from received binary byte stream; confirms upstream API payload data has remained constant since 2026-11-04).
* **Canonical JSON UTF-8 SHA-256:** `78b2de28dd0367727657c5f74079e7dc325f47cf3ddc5d1f4679d28008d06030` (Calculated after canonical key-sorted serialization).
* **Total Class 4 Records in Catalog:** **30 Records** (27 Academic under `4. Class-IV`, 1 Value Education Module, 2 Physical Education Resource Books).
* **Core In-Scope State Board Books (Tamil & English Medium):** **9 Records**
* **Out-of-Scope Records:** **21 Records** (1 CBSE Tamil, 17 Minority Languages, 1 Value Education, 2 Physical Education).

---

## 3. Physical Distribution vs CloudFront CDN Access Status (Textbook Corporation Verification)

According to official Tamil Nadu Textbook and Educational Services Corporation ([textbookcorp.in](https://www.textbookcorp.in/schools)) distribution orders:
- **Class 4–7 Term-I Textbook Sales:** Officially commenced on **14 May 2026**.
- **Class 1–7 Term-II Textbook Sales:** Officially commenced on **22 September 2026**.
- The physical print circulation for both Term-I and Term-II is actively distributed in Tamil Nadu schools.

### CloudFront CDN Probe Details (Live Probe on 2026-11-08)

All 6 Term-II and Term-III official CloudFront URLs were tested live:

| Book Title | Official CDN URL | HTTP Status | Response Server | UTC Timestamp Checked | Official Access Status |
|:---|:---|:---:|:---:|:---:|:---|
| **Term-II VOL-I (Tamil & English)** | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_4_II_VOL-I.pdf` | **403 Forbidden** | `AmazonS3` | `2026-11-08T10:21:19Z` | `CDN_ACCESS_BLOCKED` |
| **Term-II VOL-II (Maths, Sci & Soc TM)** | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_4_II_VOL-II_TM.pdf` | **403 Forbidden** | `AmazonS3` | `2026-11-08T10:21:19Z` | `CDN_ACCESS_BLOCKED` |
| **Term-II VOL-II (Maths, Sci & Soc EM)** | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_4_II_VOL-II_EM.pdf` | **403 Forbidden** | `AmazonS3` | `2026-11-08T10:21:20Z` | `CDN_ACCESS_BLOCKED` |
| **Term-III VOL-I (Tamil & English)** | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/TAMIL%20%26%20ENGLISH_4_III_VOL-I.pdf` | **403 Forbidden** | `AmazonS3` | `2026-11-08T10:21:20Z` | `CDN_ACCESS_BLOCKED` |
| **Term-III VOL-II (Maths, Sci & Soc TM)** | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_4_III_VOL-II_TM.pdf` | **403 Forbidden** | `AmazonS3` | `2026-11-08T10:21:20Z` | `CDN_ACCESS_BLOCKED` |
| **Term-III VOL-II (Maths, Sci & Soc EM)** | `https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/MATHS%2C%20SCIENCE%20%26%20SOCIAL_4_III_VOL-II_EM.pdf` | **403 Forbidden** | `AmazonS3` | `2026-11-08T10:21:20Z` | `CDN_ACCESS_BLOCKED` |

> **Critical Classification Directive:** Because Term-II books are physically in school circulation as per government announcements, the CDN 403 status is classified strictly as **`CDN_ACCESS_BLOCKED`** (upstream cloud permission issue), not `NOT_RELEASED`. Legacy Term-II and Term-III files in `main` must remain fully preserved and accessible in portal routing until official CDN files become downloadable.

---

## 4. Main Repository Legacy Page-2 Evidence Table (All 24 Books Accounted For)

Every single one of the 24 legacy subject books on `tn-class-04/main` has been audited individually via GitHub API:

| No. | Subject & Term | Main Repository File Path | Git Blob SHA | Exact Extracted Text / Content on Page 2 | Page 2 Classification & Role |
|:---:|:---|:---|:---:|:---|:---|
| 1 | **Tamil Term 1** | `tamil/term1/00_prelims/page_02.pdf` | `02fb6e311bddd0b97a6cecab4248869f10157cad` | `II \| தமிழ்நாடு அரசு \| முதல்பதிப்பு - 2019 \| திருத்திய பதிப்பு - 2020, 2022 \| மறுபதிப்பு - 2021, 2023, 2024` | Formal SCERT Imprint Page |
| 2 | **Tamil Term 2** | `tamil/term2/00_prelims/page_02.pdf` | `cb82b2a2c511fde62b019ea5c0696abfc348456d` | `முகவுரை \| கல்வி, அறிவுத் தேடலுக்கான பயணம் மட்டுமல்ல; எதிர்கால வாழ்விற்கு அடித்தளம் அமைத்திடும்...` | Preface Page (Split lacks standalone copyright page; p1=Title, p2=Preface) |
| 3 | **Tamil Term 3** | `tamil/term3/00_prelims/page_02.pdf` | `7c310861ac54d6ad86f27f39b3fcbfdb04eff979` | `முகவுரை \| கல்வி, அறிவுத் தேடலுக்கான பயணம் மட்டுமல்ல; எதிர்கால வாழ்விற்கு அடித்தளம் அமைத்திடும்...` | Preface Page (Split lacks standalone copyright page) |
| 4 | **English Term 1** | `english/term1/00_prelims/page_02.pdf` | `c7d16e33df04ceb91e038028d5e9fe2da7f40af3` | `• Children learn new skills every day and have many likes that can be developed...` | Pedagogical Skills Overview (p1=How to use textbook, p2=Skills overview) |
| 5 | **English Term 2** | `english/term2/00_prelims/page_02.pdf` | `6900f10fa58651f42b6c9b36e58e679a5ef8e622` | `How to use the textbook? \| • The second term II English Book for Standard IV has...` | Textbook Instructions Page |
| 6 | **English Term 3** | `english/term3/00_prelims/page_02.pdf` | `9bbbb9d985cdf216c4c8853503c6e787c78744c5` | `How to use the textbook \| • The third term English Book for Standard 4 has three units...` | Textbook Instructions Page |
| 7 | **Maths TM Term 1** | `maths_tm/term1/00_prelims/page_02.pdf` | `4b77145e4e8afda3395cd579f21239ae130b7b10` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| திருத்திய பதிப்பு - 2020, 2022` | Formal SCERT Imprint Page |
| 8 | **Maths TM Term 2** | `maths_tm/term2/00_prelims/page_02.pdf` | `cd04d1ebeed4247cfb14a78bb58995e7e7d8c68a` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)` | Formal SCERT Imprint Page |
| 9 | **Maths TM Term 3** | `maths_tm/term3/00_prelims/page_02.pdf` | `01a81d846fa2a412c60cc0fbaec5fa578325422d` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)` | Formal SCERT Imprint Page |
| 10 | **Maths EM Term 1** | `maths_em/term1/00_prelims/page_02.pdf` | `c558a4978786f9cf9a6e3afd677c30e4a70c6b5d` | `Government of Tamil Nadu \| First Edition - 2019 \| Revised Edition - 2020, 2022` | Formal SCERT Imprint Page |
| 11 | **Maths EM Term 2** | `maths_em/term2/00_prelims/page_02.pdf` | `99bc5f5ec29a609d9506e309ad940093d9b42d9d` | `Government of Tamil Nadu \| First Edition - 2019 \| (Published under New Syllabus in Trimester Pattern)` | Formal SCERT Imprint Page |
| 12 | **Maths EM Term 3** | `maths_em/term3/00_prelims/page_02.pdf` | `db01a5d49e5378c39cda265aba57ab529cdc17e9` | `Government of Tamil Nadu \| First Edition - 2019 \| (Published under New Syllabus in Trimester Pattern)` | Formal SCERT Imprint Page |
| 13 | **Science TM Term 1** | `science_tm/term1/00_prelims/page_02.pdf` | `ceb267762ce97c3e5d5cfa992a1c8cfb4b889a0f` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| திருத்திய பதிப்பு - 2020, 2022` | Formal SCERT Imprint Page |
| 14 | **Science TM Term 2** | `science_tm/term2/00_prelims/page_02.pdf` | `1d399bf8482c9cc316516ab2f67ba47f480aecd7` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)` | Formal SCERT Imprint Page |
| 15 | **Science TM Term 3** | `science_tm/term3/00_prelims/page_02.pdf` | `25b0779c6a231ae6603c7effad37ff4aa49a66f7` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)` | Formal SCERT Imprint Page |
| 16 | **Science EM Term 1** | `science_em/term1/00_prelims/page_02.pdf` | `d76c0b1ff33de0ff4204a1ad7568538050d5accd` | `Government of Tamil Nadu \| First Edition - 2019 \| Revised Edition - 2020, 2022` | Formal SCERT Imprint Page |
| 17 | **Science EM Term 2** | `science_em/term2/00_prelims/page_02.pdf` | `63261c954ab59e53436069d4639d2ff51a390a85` | `Government of Tamil Nadu \| First Edition - 2019 \| (Published under New Syllabus in Trimester Pattern)` | Formal SCERT Imprint Page |
| 18 | **Science EM Term 3** | `science_em/term3/00_prelims/page_02.pdf` | `c706d772486e3dabe512ac3b175d6a585a91702a` | `Government of Tamil Nadu \| First Edition - 2019 \| (Published under New Syllabus in Trimester Pattern)` | Formal SCERT Imprint Page |
| 19 | **Social Science TM Term 1** | `social_science_tm/term1/00_prelims/page_02.pdf` | `b112ed30ae9273726b8b3b5875c402b34ff4be0c` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| திருத்திய பதிப்பு - 2020, 2022` | Formal SCERT Imprint Page |
| 20 | **Social Science TM Term 2** | `social_science_tm/term2/00_prelims/page_02.pdf` | `598374341a1a8f03c1558a2e87c033bb74ead864` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)` | Formal SCERT Imprint Page |
| 21 | **Social Science TM Term 3** | `social_science_tm/term3/00_prelims/page_02.pdf` | `bff92716d1ff9924943b2ea560de530f91e34038` | `II \| தமிழ்நாடு அரசு \| முதல் பதிப்பு - 2019 \| (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)` | Formal SCERT Imprint Page |
| 22 | **Social Science EM Term 1** | `social_science_em/term1/00_prelims/page_02.pdf` | `a348813d06f297b45702d2e7bccc09d0dc403bf7` | `Government of Tamil Nadu \| First Edition - 2019 \| Revised Edition - 2020, 2022` | Formal SCERT Imprint Page |
| 23 | **Social Science EM Term 2** | `social_science_em/term2/00_prelims/page_02.pdf` | `521b06eba7d4ca275662ad9d3dcf1c0ce1acfa99` | `Government of Tamil Nadu \| First Edition - 2019 \| (Published under New Syllabus in Trimester Pattern)` | Formal SCERT Imprint Page |
| 24 | **Social Science EM Term 3** | `social_science_em/term3/00_prelims/page_02.pdf` | `cf5e19916cc6c0f3583b5a5baa4f57db22953519` | `Government of Tamil Nadu \| First Edition - 2019 \| (Published under New Syllabus in Trimester Pattern)` | Formal SCERT Imprint Page |

---

## 5. In-Depth Content Comparison Report (3 New Term-I Combined Volumes)

Comparison of official 2026 combined textbooks against the separate subject baseline folders on `main`:

| Book Identity | Official Page Count | Baseline Combined Page Count | Printed Imprint (Official vs Local) | Page 2 Imprint Match Status | Text Comparison Findings | Visual Comparison Status | Verified Edition Conclusion |
|:---|:---:|:---:|:---|:---:|:---|:---|:---|
| **Term-I VOL-I (Tamil & English)** | **152** | **152**<br>(Tamil 81p + Eng 71p) | **Official:** `முதல்பதிப்பு 2019`<br>**Local:** `முதல்பதிப்பு 2019` | `MATCH_PAGE2_DIFFERENT_REMAINDER` | **133 pages identical text; 19 pages differing text.** | Automated OCR/pdfplumber text diff only; individual page visual screenshot review not performed. | **DIFFERING COMPILATION** (New combined edition formatting and text updates). |
| **Term-I VOL-II (Maths, Science & Social TM)** | **160** | **164**<br>(Maths 83p + Sci 45p + Soc 36p) | **Official:** `முதல் பதிப்பு 2019`<br>**Local:** `2019; Revised 2020, 2022` | `DIFFERENT` | **All 160 pages differ in text comparison.** Pagination shifted by -4 pages due to combined volume layout. | Automated text diff only; visual screenshot review not performed. | **NEW COMBINED EDITION** (Different layout, page count, and contents). |
| **Term-I VOL-II (Maths, Science & Social EM)** | **160** | **164**<br>(Maths 83p + Sci 45p + Soc 36p) | **Official:** `2019; Rev 2020, 2022, 2023`<br>**Local:** `2019; Rev 2020, 2022` | `DIFFERENT` | **All 160 pages differ in text comparison.** Pagination shifted by -4 pages due to combined volume layout. | Automated text diff only; visual screenshot review not performed. | **NEW COMBINED EDITION** (Different layout, page count, and contents). |

---

## 6. Complete Support File Mapping (131 Questions Files Accounted For)

Every single one of the 131 `questions.md` files on `main` is strictly mapped to its legacy book and chapter:

| Subject & Term | Total `questions.md` Files | Mapped Lessons / Chapters | `UNMAPPED_SUPPORT_FILE` Count |
|:---|:---:|:---|:---:|
| **Tamil Root** | 1 | `tamil/book_back_questions/questions.md` (Subject-level summary) | 0 |
| **Tamil Term 1** | 10 | Lessons 01–09 (`01_annai_thamizhe` to `09_karikalan_kattiya_kallanai`) + Term summary | 0 |
| **Tamil Term 2** | 10 | Lessons 01–09 (`01_kaavalkaaran` to `09_naam_kaakkum_iyarhai`) + Term summary | 0 |
| **Tamil Term 3** | 10 | Lessons 01–09 (`01_ulaa_varum_seyarkaikol` to `09_neethi_neri_vilakkam`) + Term summary | 0 |
| **English Root** | 1 | `english/book_back_questions/questions.md` (Subject-level summary) | 0 |
| **English Term 1** | 4 | Units 01–03 (`01_a_world_with_robots`, `02_my_hobbies`, `03_time_for_a_journey`) + Term summary | 0 |
| **English Term 2** | 3 | Units 01–02 (`01_affection`, `02_saving`) + Term summary | 0 |
| **English Term 3** | 4 | Units 01–03 (`01_the_best_policy`, `02_creativity_around_me`, `03_secret_of_success`) + Term summary | 0 |
| **Maths TM Root** | 1 | `maths_tm/book_back_questions/questions.md` | 0 |
| **Maths TM Term 1** | 7 | Units 01–07 (`01_geometry` to `07_information_processing`) | 0 |
| **Maths TM Term 2** | 5 | Units 01–05 (`01_geometry` to `05_information_processing`) | 0 |
| **Maths TM Term 3** | 4 | Units 01, 02, 06 + Term summary | 0 |
| **Maths EM Root** | 1 | `maths_em/book_back_questions/questions.md` | 0 |
| **Maths EM Term 1** | 7 | Units 01–07 (`01_geometry` to `07_information_processing`) | 0 |
| **Maths EM Term 2** | 5 | Units 01–05 (`01_geometry` to `05_information_processing`) | 0 |
| **Maths EM Term 3** | 4 | Units 01, 02, 06 + Term summary | 0 |
| **Science TM Root** | 1 | `science_tm/book_back_questions/questions.md` | 0 |
| **Science TM Term 1** | 5 | Units 01–04 (`01_my_body` to `04_science_in_everyday_life`) + Term summary | 0 |
| **Science TM Term 2** | 4 | Units 01–03 (`01_food`, `02_water`, `03_plants`) + Term summary | 0 |
| **Science TM Term 3** | 4 | Units 01–03 (`01_green_environment`, `02_animals_life`, `03_air_we_breathe`) + Term summary | 0 |
| **Science EM Root** | 1 | `science_em/book_back_questions/questions.md` | 0 |
| **Science EM Term 1** | 5 | Units 01–04 (`01_my_body` to `04_science_in_everyday_life`) + Term summary | 0 |
| **Science EM Term 2** | 4 | Units 01–03 (`01_food`, `02_water`, `03_plants`) + Term summary | 0 |
| **Science EM Term 3** | 4 | Units 01–03 (`01_green_environment`, `02_animals_life`, `03_air_we_breathe`) + Term summary | 0 |
| **Social Science TM Root** | 1 | `social_science_tm/book_back_questions/questions.md` | 0 |
| **Social Science TM Term 1** | 4 | Units 01–03 (`01_kingdoms_of_rivers`, `02_five_landforms`, `03_municipality_and_corporation`) + Term summary | 0 |
| **Social Science TM Term 2** | 4 | Units 01–03 (`01_philanthropists_of_sangam_age`, `02_physical_features_of_tn`, `03_transport`) + Term summary | 0 |
| **Social Science TM Term 3** | 4 | Units 01–03 (`01_tamils_around_the_world`, `02_history_of_madras_presidency`, `03_rights_and_duties_of_children`) + Term summary | 0 |
| **Social Science EM Root** | 1 | `social_science_em/book_back_questions/questions.md` | 0 |
| **Social Science EM Term 1** | 4 | Units 01–03 (`01_kingdoms_of_rivers`, `02_five_landforms`, `03_municipality_and_corporation`) + Term summary | 0 |
| **Social Science EM Term 2** | 4 | Units 01–03 (`01_philanthropists_of_sangam_age`, `02_physical_features_of_tn`, `03_transport`) + Term summary | 0 |
| **Social Science EM Term 3** | 4 | Units 01–03 (`01_tamils_around_the_world`, `02_history_of_madras_presidency`, `03_rights_and_duties_of_children`) + Term summary | 0 |
| **Totals** | **131** | **All 131 files mapped 100% to legacy curriculum** | **0** |

---

## 7. Migration Mapping & Destination Architecture (Pre-Migration Plan)

| Content Package | File Count Breakdown | Planned Active Destination | Planned Archive Destination | Migration Pre-Condition |
|:---|:---:|:---|:---|:---|
| **Term 1 Legacy Package** (8 Books) | 480 PDFs + 8 manifests + 46 questions = **534 files** | Will be superseded by Term 1 2026 combined books | `legacy-2018-2022/{subject}/term1/` | Transferred in resumable batches of 200–300 files per book package. |
| **Term 2 Legacy Package** (8 Books) | 382 PDFs + 8 manifests + 39 questions = **429 files** | **RETAINED ACCESSIBLE IN PORTAL** | Future archive upon official CDN access | Because official CDN returned HTTP 403 (`CDN_ACCESS_BLOCKED`), these remain active/linked. |
| **Term 3 Legacy Package** (8 Books) | 438 PDFs + 8 manifests + 38 questions = **484 files** | **RETAINED ACCESSIBLE IN PORTAL** | Future archive upon official CDN access | Because official CDN returned HTTP 403 (`CDN_ACCESS_BLOCKED`), these remain active/linked. |
| **Subject Root Questions** | 8 files (`book_back_questions/questions.md`) | — | `legacy-2018-2022/{subject}/book_back_questions/` | Transferred with respective subject package. |
| **2026 Term 1 Combined Books** (3 Books) | 472 PDFs + 15 manifests = **487 files** | `books/2026-27/term1/` | — | Promoted from `scert/class-04/audit-2026-27`. |
| **Repository Infrastructure** | **11 files** (HTML, JS, docs, README) | Strictly preserved in `main` root | Never archived | Protected from deletion or archiving. |

---

## 8. Governance Directives & Protocol Safeguards

1. **Strict Read-Only Guarantee:** ZERO files moved, ZERO files deleted, ZERO uploads to `main`, ZERO branch merges.
2. **Book-First Execution Discipline:** Once approved, migration will proceed strictly one book at a time in self-contained batches of 200–300 files.
3. **Resumable Checkpoints:** If any rate limit (403/429) occurs, execution will back off and resume from checkpoint, skipping matching SHAs.
4. **Action Gate:** All migration operations remain completely on HOLD awaiting user review and explicit approval of this Draft Register.
