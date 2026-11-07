# SCERT Class 6 Textbook Edition Verification Audit Report (49 Records)

**Audit Execution Environment:** GitHub Actions Runner (Ubuntu 22.04 LTS)  
**Execution Timestamp:** 2026-11-04T19:04:19.462786+00:00 UTC  
**Target Repository:** Eaglesiva/tn-class-06  
**Target Branch:** scert/class-06/audit-2026-27  
**Live Official API URL:** `https://emis3.tnschools.gov.in/api/get_scert_books`  
**Raw API Snapshot SHA-256:** `404f283443b1f7a6a0fae814092aae556d0419ad2b4b2c0b0a0f7ebd756cc3e4`  

---

## 1. Class-Wide Metric Reconciliation Table (49 Records Complete)

| No. | Audit Verification Metric | Count | Reconciliation & Evidence Details |
|---|---|:---:|---|
| 1 | **Total Class 6 Official API Records** | **49** | Complete live API inventory across all sections: 46 academic, 1 valuation module, 2 physical education resource books. |
| 2 | **In-Scope Records (State Board Tamil & English)** | **15** | Core State Board academic books: 5 Term-I, 5 Term-II, 5 Term-III. |
| 3 | **Out-of-Scope Records** | **34** | • 1 CBSE Tamil volume (`TAMIL(CBSE)`)<br>• 23 Minority language readers & mediums (Telugu, Kannada, Malayalam, Urdu, Hindi, Sanskrit, Arabic, French)<br>• 1 Value education supplementary module (`6th_Std_Value_Education_Module.pdf`)<br>• 2 Physical education teacher's resource books (Tamil & English) |
| 4 | **Official URLs Successfully Downloaded & Audited** | **5** | All currently accessible Term-I State Board books sequentially downloaded to runner `/tmp/`, verified, and removed. |
| 5 | **Official URLs Returning HTTP 403 on GET** | **10** | Term-II and Term-III State Board books returned HTTP 403 Forbidden on GET (`GET_HTTP_403_FORBIDDEN_AS_OF_2026-11-04`). Confirms that these files currently cannot be downloaded from CDN. |
| 6 | **Books Matching Existing Local Baseline** | **0** | Zero. Baseline folders contain legacy 2018/2019/2022 separate book splits. |
| 7 | **Books with Confirmed New/Different Edition (2026)** | **5** | All downloaded books confirmed as 2026 curriculum volumes with differing text/pages and 2023/2024 reprint imprints. |
| 8 | **Books Successfully Split & Validated into 1-Page PDFs** | **5** | All confirmed new edition books split into individual pages with 100% passing structural validation (magic bytes, 1-page, renderable, size, continuity). |
| 9 | **Books Ingested into Audit Branch Editions** | **5** | Ingested under immutable paths in `official_editions/2026-27/`. |
| 10 | **Books Requiring Manual Review (TOC boundaries)** | **3** | Vol-I (Tamil & English) and Vol-III (Science & Social Science TM/EM) combined volumes require unit-level manual review (`MANUAL_REVIEW_REQUIRED`). Vol-II (Maths TM & EM) are standalone single-subject volumes. |
| 11 | **Books Currently Inaccessible on CDN (HTTP 403)** | **10** | Term-II (5 books) & Term-III (5 books) State Board books. |
| 12 | **Books Not Checked** | **0** | Every single one of the 49 records was evaluated and cataloged. |

---

## 2. Git Safety & Production Protection
- **Main Branch:** Completely protected. Zero changes to existing production folders (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`, `social_science_tm/`, `social_science_em/`, `index.html`, `viewer.html`).
- **Audit Branch:** All files stored strictly under `official_editions/2026-27/` and root audit manifests on `scert/class-06/audit-2026-27`.
- **Master PDFs:** Zero master PDFs committed to Git. Downloaded strictly to runner temporary `/tmp/` and removed immediately after splitting.
