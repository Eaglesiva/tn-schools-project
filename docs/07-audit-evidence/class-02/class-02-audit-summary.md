# SCERT Class 2 (2026–27) Comprehensive Class-Wide Audit & Ingestion Report

**Execution Timestamp:** 2026-11-04T19:03:29.408676+00:00 UTC  
**Target Repository:** Eaglesiva/tn-class-02  
**Target Branch:** scert/class-02/audit-2026-27  
**Live Official API URL:** `https://emis3.tnschools.gov.in/api/get_scert_books`  
**Raw API Snapshot SHA-256:** `404f283443b1f7a6a0fae814092aae556d0419ad2b4b2c0b0a0f7ebd756cc3e4`  

---

## 1. Class-Wide Metric Reconciliation Table (34 Records Complete)

| No. | Audit Verification Metric | Count | Reconciliation & Evidence Details |
|---|---|:---:|---|
| 1 | **Total Class 2 Official API Records** | **34** | Complete live API inventory across all sections: 31 academic, 1 valuation module, 2 physical education resource books. |
| 2 | **In-Scope Records (State Board Tamil & English)** | **9** | Core State Board academic books: 3 Term-I, 3 Term-II, 3 Term-III. |
| 3 | **Out-of-Scope Records** | **25** | • 1 CBSE Tamil volume (`TAMIL(CBSE)`)<br>• 21 Minority language readers & mediums (Telugu, Kannada, Malayalam, Urdu, Hindi)<br>• 1 Value education supplementary module (`2nd_Std_Value_Education_Module.pdf`)<br>• 2 Physical education teacher's resource books (Tamil & English) |
| 4 | **Official URLs Successfully Downloaded & Audited** | **6** | All 6 currently released Term-I and Term-II State Board books sequentially downloaded to runner `/tmp/`, verified, and removed. |
| 5 | **Official URLs Returning HTTP 403 on GET** | **3** | Exactly 3 Term-III State Board books returned HTTP 403 Forbidden on both HEAD and GET (`GET_HTTP_403_FORBIDDEN_AS_OF_2026-11-04`). Confirms official Textbook Corporation distribution schedule (Term-III 2026–27 PDFs not yet released). |
| 6 | **Books Matching Existing Local Baseline** | **0** | Zero. All repository baseline folders contain legacy 2019/2022 separate book splits. |
| 7 | **Books with Confirmed New/Different Edition (2026)** | **6** | All 6 downloaded books confirmed as 2026 combined curriculum volumes with higher page counts and differing text. |
| 8 | **Books Successfully Split & Validated into 1-Page PDFs** | **6** | All 6 confirmed new edition books split into individual pages (**824 total pages**) with 100% passing structural validation (magic bytes, 1-page, renderable, size, continuity). |
| 9 | **Books Ingested into Audit Branch Editions** | **6** | Ingested under immutable paths in `official_editions/2026-27/`: <br>• `term1/vol1_tamil_english/` (160p)<br>• `term1/vol2_maths_evs_tm/` (144p)<br>• `term1/vol2_maths_evs_em/` (144p)<br>• `term2/vol1_tamil_english/` (136p)<br>• `term2/vol2_maths_evs_tm/` (120p)<br>• `term2/vol2_maths_evs_em/` (120p) |
| 10 | **Books Requiring Manual Review (TOC boundaries)** | **6** | All 6 combined volumes require unit-level manual review to map internal subject boundaries before production viewer routing. |
| 11 | **Books Awaiting Official Release (Term-III)** | **3** | All 3 Term-III State Board books. |
| 12 | **Books Not Checked** | **0** | Every single one of the 34 records was evaluated and cataloged. |

---

## 2. In-Scope Book Details & All-Pages Comparison

| Term | Subject & Volume | Medium | Official Pages | Baseline Local Pages | All-Pages Comparison Metric | Split Pages Validated | Final Status |
|---|---|---|:---:|:---:|---|:---:|---|
| **Term-I** | **VOL-I (TAMIL& ENGLISH)** | Combined (`16,19`) | **160** | 160 (82p Tam + 78p Eng) | Official is single combined volume; Local is split into 2 folders | **160 / 160** | **SPLIT_VALIDATED** |
| **Term-I** | **VOL-II (MATHS & EVS)** | Tamil (`16`) | **144** | 130 (76p Mat + 54p Sci) | Compared 130p: text differs; +14 extra official pages | **144 / 144** | **SPLIT_VALIDATED** |
| **Term-I** | **VOL-II (MATHS & EVS)** | English (`19`) | **144** | 130 (76p Mat + 54p Sci) | Compared 130p: text differs; +14 extra official pages | **144 / 144** | **SPLIT_VALIDATED** |
| **Term-II** | **VOL-I (TAMIL& ENGLISH)** | Combined (`16,19`) | **136** | 97 (50p Tam + 47p Eng) | Compared 97p: text differs; +39 extra official pages | **136 / 136** | **SPLIT_VALIDATED** |
| **Term-II** | **VOL-II (MATHS & EVS)** | Tamil (`16`) | **120** | 90 (50p Mat + 40p Sci) | Compared 90p: text differs; +30 extra official pages | **120 / 120** | **SPLIT_VALIDATED** |
| **Term-II** | **VOL-II (MATHS & EVS)** | English (`19`) | **120** | 86 (50p Mat + 36p Sci) | Compared 86p: text differs; +34 extra official pages | **120 / 120** | **SPLIT_VALIDATED** |
| **Term-III** | **VOL-I (TAMIL& ENGLISH)** | Combined (`16,19`) | — | 119 (56p Tam + 63p Eng) | GET returned HTTP 403 AccessDenied | — | **GET_HTTP_403_FORBIDDEN_AS_OF_2026-11-04** |
| **Term-III** | **VOL-II (MATHS & EVS)** | Tamil (`16`) | — | 114 (63p Mat + 51p Sci) | GET returned HTTP 403 AccessDenied | — | **GET_HTTP_403_FORBIDDEN_AS_OF_2026-11-04** |
| **Term-III** | **VOL-II (MATHS & EVS)** | English (`19`) | — | 114 (63p Mat + 51p Sci) | GET returned HTTP 403 AccessDenied | — | **GET_HTTP_403_FORBIDDEN_AS_OF_2026-11-04** |

---

## 3. Git Safety & Production Protection
- **Main Branch:** Completely protected. Zero changes to existing production folders (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`, `index.html`, `viewer.html`).
- **Audit Branch:** All files stored strictly under `official_editions/2026-27/` and root audit manifests on `scert/class-02/audit-2026-27`.
- **Master PDFs:** Zero master PDFs committed to Git. Downloaded strictly to runner temporary `/tmp/` and removed immediately after splitting.
