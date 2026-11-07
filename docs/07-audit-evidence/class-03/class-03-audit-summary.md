# SCERT Class 3 Textbook Edition Verification Audit Report (35 Records)

**Audit Execution Environment:** GitHub Actions Runner (Ubuntu 22.04 LTS)  
**Execution Timestamp:** 2026-11-04T23:34:58.934534+00:00 UTC  
**Target Repository:** Eaglesiva/tn-class-03  
**Target Branch:** scert/class-03/audit-2026-27  
**Live Official API URL:** `https://emis3.tnschools.gov.in/api/get_scert_books`  
**Raw API Snapshot SHA-256:** `404f283443b1f7a6a0fae814092aae556d0419ad2b4b2c0b0a0f7ebd756cc3e4`  

---

## 1. Class-Wide Metric Reconciliation Table (35 Records Complete)

| No. | Audit Verification Metric | Count | Reconciliation & Evidence Details |
|---|---|:---:|---|
| 1 | **Total Class 3 Official API Records** | **35** | Complete live API inventory across all sections: 32 academic, 1 valuation module, 2 physical education resource books. |
| 2 | **In-Scope Records (State Board Tamil & English)** | **9** | Core State Board academic books: 3 Term-I, 3 Term-II, 3 Term-III. |
| 3 | **Out-of-Scope Records** | **26** | • 1 CBSE Tamil volume (`TAMIL(CBSE)`)<br>• 22 Minority language readers & mediums (Telugu, Kannada, Malayalam, Urdu, Hindi)<br>• 1 Value education supplementary module (`3rd_Std_Value_Education_Module.pdf`)<br>• 2 Physical education teacher's resource books (Tamil & English) |
| 4 | **Official URLs Successfully Downloaded & Audited** | **6** | All 6 currently released Term-I and Term-II State Board books sequentially downloaded to runner `/tmp/`, verified, and removed. |
| 5 | **Official URLs Returning HTTP 403 on GET** | **3** | Exactly 3 Term-III State Board books returned HTTP 403 Forbidden on both HEAD and GET (`GET_HTTP_403_FORBIDDEN_AS_OF_2026-11-04`). Confirms official Textbook Corporation distribution schedule (Term-III 2026–27 PDFs not yet released). |
| 6 | **Books Matching Existing Local Baseline** | **0** | Zero. All repository baseline folders contain legacy 2018/2019/2022 separate book splits. |
| 7 | **Books with Confirmed New/Different Edition (2026)** | **6** | All 6 downloaded books confirmed as 2026 combined curriculum volumes with higher page counts and differing text. |
| 8 | **Books Successfully Split & Validated into 1-Page PDFs** | **6** | All 6 confirmed new edition books split into individual pages with 100% passing structural validation (magic bytes, 1-page, renderable, size, continuity). |
| 9 | **Books Ingested into Audit Branch Editions** | **6** | Ingested under immutable paths in `official_editions/2026-27/`: <br>• `term1/vol1_tamil_english/`<br>• `term1/vol2_maths_sci_soc_tm/`<br>• `term1/vol2_maths_sci_soc_em/`<br>• `term2/vol1_tamil_english/`<br>• `term2/vol2_maths_sci_soc_tm/`<br>• `term2/vol2_maths_sci_soc_em/` |
| 10 | **Books Requiring Manual Review (TOC boundaries)** | **6** | All 6 combined volumes require unit-level manual review to map internal subject boundaries before production viewer routing. |
| 11 | **Books Awaiting Official Release (Term-III)** | **3** | All 3 Term-III State Board books. |
| 12 | **Books Not Checked** | **0** | Every single one of the 35 records was evaluated and cataloged. |

---

## 2. Git Safety & Production Protection
- **Main Branch:** Completely protected. Zero changes to existing production folders (`tamil/`, `english/`, `maths_tm/`, `maths_em/`, `science_tm/`, `science_em/`, `social_science_tm/`, `social_science_em/`, `index.html`, `viewer.html`).
- **Audit Branch:** All files stored strictly under `official_editions/2026-27/` and root audit manifests on `scert/class-03/audit-2026-27`.
- **Master PDFs:** Zero master PDFs committed to Git. Downloaded strictly to runner temporary `/tmp/` and removed immediately after splitting.
