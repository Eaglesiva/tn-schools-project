# SCERT Audit Artifacts — Local vs GitHub Inventory

**Checked & Updated:** 2026-11-05 (Asia/Kolkata)  
**Scope:** Authoritative register of all GitHub repositories, production branches, update branches, and local evidence artifacts generated during the 2026–27 SCERT State Board textbook audit and 38-book refresh across Classes 1 to 12.

---

## 1. Direct Official Master Refreshed Books (Production Main) — 38 Books / 11,760 Pages

All 38 pending textbooks were refreshed directly from current 2026–27 SCERT CloudFront master PDFs exclusively via GitHub Actions ephemeral hosted runners. Single-page PDFs were sliced and committed in-place on production `main` branches, preserving exact directory hierarchy and viewer URLs. Zero master PDF bytes were persisted locally.

| Class | Refreshed Books | Refreshed Pages | Production `main` Tip Commit | Machine-Readable Evidence Artifacts |
| :---: | :---: | :---: | :--- | :--- |
| **9** | **5** | **1,664** | [`d6fc546d`](https://github.com/Eaglesiva/tn-class-09/commit/d6fc546d58aab5f520c5cfbebddb2a829ce86bae) | [`class_09_all_refreshed_evidence.json`](./refresh_evidence/class_09_all_refreshed_evidence.json)<br>Individual JSONs: `maths_em`, `science_tm`, `science_em`, `social_science_tm`, `social_science_em` |
| **10** | **1** | **224** | [`22f176e2`](https://github.com/Eaglesiva/tn-class-10/commit/22f176e29b3e92be4ff6a110ac8285a1ce371765) | [`class_10_english_refresh_evidence.json`](./refresh_evidence/class_10_english_refresh_evidence.json) |
| **12** | **32** | **9,872** | [`c15e34ad`](https://github.com/Eaglesiva/tn-class-12/commit/c15e34ad9ca2f53ccd020b2625995d2c20aaf952) | [`class_12_all_refreshed_evidence.json`](./refresh_evidence/class_12_all_refreshed_evidence.json) |
| **Total** | **38** | **11,760** | — | **Full Contiguity Evidence**: [`scert_38_toc_contiguity_audit.json`](./refresh_evidence/scert_38_toc_contiguity_audit.json) (592 directories across 38 books: Class 9: 125, Class 10: 22, Class 12: 445) |

### Detailed 38-Book Production Refreshed Register

| # | Class | Subject & Volume | Medium | Pages | Official Master SHA-256 (First 16 hex) | Runner In-Place Status | Contiguity Across Subdirs |
| :---: | :---: | :--- | :---: | :---: | :---: | :---: | :---: |
| 1 | 9 | Mathematics | English | 328 | `09a3c7ce5f55fa72` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–328) |
| 2 | 9 | Science | Tamil | 336 | `926439263715ecb9` | REFRESH_COMMITTED | 26/26 Dirs Contiguous (p.1–336) |
| 3 | 9 | Science | English | 328 | `e142c38d321fd6fa` | REFRESH_COMMITTED | 26/26 Dirs Contiguous (p.1–328) |
| 4 | 9 | Social Science | Tamil | 344 | `76ed2a8ff4a3779e` | REFRESH_COMMITTED | 31/31 Dirs Contiguous (p.1–344) |
| 5 | 9 | Social Science | English | 328 | `ee52e826762c4ea5` | REFRESH_COMMITTED | 31/31 Dirs Contiguous (p.1–328) |
| 6 | 10 | English | English | 224 | `4d09e77f39d2c206` | REFRESH_COMMITTED | 22/22 Dirs Contiguous (p.1–224) |
| 7 | 12 | General Tamil | Tamil | 240 | `6813313ab87140f6` | REFRESH_COMMITTED | 9/9 Dirs Contiguous (p.1–240) |
| 8 | 12 | General English | English | 248 | `e1872f57497d3419` | REFRESH_COMMITTED | 23/23 Dirs Contiguous (p.1–248) |
| 9 | 12 | Mathematics (Vol I) | Tamil | 336 | `310b339a96ea855d` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–336) |
| 10 | 12 | Mathematics (Vol II) | Tamil | 288 | `92b0c3ac3c0b1f13` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–288) |
| 11 | 12 | Mathematics (Vol I) | English | 304 | `040df951b752fe9d` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–304) |
| 12 | 12 | Mathematics (Vol II) | English | 272 | `272488124c6efcf0` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–272) |
| 13 | 12 | Physics (Vol I) | Tamil | 352 | `1abae0855e9ea29e` | REFRESH_COMMITTED | 9/9 Dirs Contiguous (p.1–352) |
| 14 | 12 | Physics (Vol II) | Tamil | 312 | `a33236ee34f9a560` | REFRESH_COMMITTED | 8/8 Dirs Contiguous (p.1–312) |
| 15 | 12 | Physics (Vol II) | English | 296 | `f63346abb31fe4ff` | REFRESH_COMMITTED | 8/8 Dirs Contiguous (p.1–296) |
| 16 | 12 | Chemistry (Vol I) | Tamil | 328 | `2db9c871a53b53f6` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–328) |
| 17 | 12 | Chemistry (Vol II) | Tamil | 344 | `b4c28ca6b0521633` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–344) |
| 18 | 12 | Chemistry (Vol II) | English | 328 | `bbf1b2fda27546ef` | REFRESH_COMMITTED | 11/11 Dirs Contiguous (p.1–328) |
| 19 | 12 | Botany | Tamil | 336 | `242756cc9a1f5a9c` | REFRESH_COMMITTED | 12/12 Dirs Contiguous (p.1–336) |
| 20 | 12 | Botany | English | 312 | `eac2781e71239c59` | REFRESH_COMMITTED | 12/12 Dirs Contiguous (p.1–312) |
| 21 | 12 | Zoology | Tamil | 336 | `f1c813fd561ba7a8` | REFRESH_COMMITTED | 18/18 Dirs Contiguous (p.1–336) |
| 22 | 12 | Zoology | English | 280 | `4e03246374070a72` | REFRESH_COMMITTED | 18/18 Dirs Contiguous (p.1–280) |
| 23 | 12 | Bio-Zoology | Tamil | 312 | `585ab94f4e72322a` | REFRESH_COMMITTED | 17/17 Dirs Contiguous (p.1–312) |
| 24 | 12 | Bio-Zoology | English | 264 | `db8d8fa4429bfb60` | REFRESH_COMMITTED | 17/17 Dirs Contiguous (p.1–264) |
| 25 | 12 | Computer Science | Tamil | 360 | `4bbca6fe774b711e` | REFRESH_COMMITTED | 21/21 Dirs Contiguous (p.1–360) |
| 26 | 12 | Computer Science | English | 360 | `fb6f35757f4fb263` | REFRESH_COMMITTED | 21/21 Dirs Contiguous (p.1–360) |
| 27 | 12 | Commerce | Tamil | 288 | `b86806fcc0e2b4cb` | REFRESH_COMMITTED | 13/13 Dirs Contiguous (p.1–288) |
| 28 | 12 | Commerce | English | 288 | `aefd49700cd14d6d` | REFRESH_COMMITTED | 13/13 Dirs Contiguous (p.1–288) |
| 29 | 12 | Accountancy | Tamil | 368 | `814d37be7dd5c52c` | REFRESH_COMMITTED | 12/12 Dirs Contiguous (p.1–368) |
| 30 | 12 | Accountancy | English | 368 | `6cbb7b89775f0f35` | REFRESH_COMMITTED | 12/12 Dirs Contiguous (p.1–368) |
| 31 | 12 | Economics | Tamil | 336 | `481e90f589980d9e` | REFRESH_COMMITTED | 14/14 Dirs Contiguous (p.1–336) |
| 32 | 12 | Economics | English | 296 | `c2c964a93883a9e7` | REFRESH_COMMITTED | 15/15 Dirs Contiguous (p.1–296) |
| 33 | 12 | History | Tamil | 312 | `c5fb6a88a91dae6c` | REFRESH_COMMITTED | 18/18 Dirs Contiguous (p.1–312) |
| 34 | 12 | History | English | 272 | `cc4b963081e7d4d8` | REFRESH_COMMITTED | 18/18 Dirs Contiguous (p.1–272) |
| 35 | 12 | Geography | Tamil | 232 | `8f3b5256209581c3` | REFRESH_COMMITTED | 17/17 Dirs Contiguous (p.1–232) |
| 36 | 12 | Geography | English | 216 | `9e9f895c4046dbe6` | REFRESH_COMMITTED | 15/15 Dirs Contiguous (p.1–216) |
| 37 | 12 | Political Science | Tamil | 360 | `3966068066bb7316` | REFRESH_COMMITTED | 14/14 Dirs Contiguous (p.1–360) |
| 38 | 12 | Political Science | English | 328 | `a5ba26c7657d42cf` | REFRESH_COMMITTED | 14/14 Dirs Contiguous (p.1–328) |

---

## 2. Central Shared Tracker Files (`Eaglesiva/tn-class-10: scert/master-edition-tracking`)

| File Name | Purpose | Records / Scope | Last Reconciled Commit |
| :--- | :--- | :---: | :--- |
| [`SCERT_MASTER_EDITION_INDEX.csv`](./SCERT_MASTER_EDITION_INDEX.csv) | Authoritative cross-class master catalog index | 165 books (Classes 1–12) | All 38 refreshed records matched with runner JSONs |
| [`FINAL_MASTER_AUDIT_STATUS.md`](./FINAL_MASTER_AUDIT_STATUS.md) | Mutually exclusive primary status accounting & TOC audit | 165 books (33,696 known official pages) | Exact -104 page reconciliation documented; 41 books unmeasured |
| [`SCERT_MASTER_EDITION_TRACKER.md`](./SCERT_MASTER_EDITION_TRACKER.md) | Comprehensive cross-class navigation tracker | Classes 1–12 summary | 42 GET-200 / 41 GET-403 harmonized |
| [`LOCAL_VS_GITHUB_ARTIFACT_INVENTORY.md`](./LOCAL_VS_GITHUB_ARTIFACT_INVENTORY.md) | Complete artifact & branch inventory register | Classes 1–12 cross-repo | Synchronized with 38-book refresh commits |
| [`scert_38_toc_contiguity_audit.json`](./refresh_evidence/scert_38_toc_contiguity_audit.json) | Granular TOC directory-by-directory contiguity proof | 38 books / 592 directories | 38/38 strictly contiguous (p.1 to end; Class 9: 125, Class 10: 22, Class 12: 445) |
| [`scert_38_refresh_targets.json`](./scert_38_refresh_targets.json) | Machine input targets for runner refresh | 38 books specification | Verified against SCERT API URLs |
| [`class_10_maths_visual_review_results.json`](./audit_evidence/class_10_maths_visual_review_results.json) | 36-page visual pixel diff & CMap decomposition results | 36 flagged pages (Class 10 Maths) | 36/36 visually & curriculum equivalent; 0 content diffs |

---

## 3. Remote Class Audit Branches & Artifacts (Classes 1–12)

| Class | GitHub Repository & Audit Branch | Core Evidence Artifacts Stored | Status Summary |
| :---: | :--- | :--- | :--- |
| **1** | [`tn-class-01: scert/class-01/audit-2026-27-term1-vol1`](https://github.com/Eaglesiva/tn-class-01/tree/scert/class-01/audit-2026-27-term1-vol1) | `class_01_audit_summary.md`<br>`class_01_2026_27_audit_manifest.csv`<br>`class_01_official_api_snapshot.json` | 6 GET-200 (848p) / 3 Term-III 403 (Release unconfirmed) |
| **2** | [`tn-class-02: scert/class-02/audit-2026-27`](https://github.com/Eaglesiva/tn-class-02/tree/scert/class-02/audit-2026-27) | `class_02_audit_summary.md`<br>`class_02_2026_27_audit_manifest.csv`<br>`class_02_official_api_snapshot.json` | 6 GET-200 (824p) / 3 Term-III 403 (Release unconfirmed) |
| **3** | [`tn-class-03: scert/class-03/audit-2026-27`](https://github.com/Eaglesiva/tn-class-03/tree/scert/class-03/audit-2026-27) | `class_03_audit_summary.md`<br>`class_03_2026_27_audit_manifest.csv`<br>`class_03_official_api_snapshot.json` | 6 GET-200 (1,016p) / 3 Term-III 403 (Release unconfirmed) |
| **4** | [`tn-class-04: scert/class-04/audit-2026-27`](https://github.com/Eaglesiva/tn-class-04/tree/scert/class-04/audit-2026-27) | `class_04_audit_summary.md`<br>`class_04_2026_27_audit_manifest.csv`<br>`class_04_official_api_snapshot.json` | 3 GET-200 (472p) / 3 Term-II 403 (Sale started) / 3 Term-III 403 |
| **5** | [`tn-class-05: scert/class-05/audit-2026-27`](https://github.com/Eaglesiva/tn-class-05/tree/scert/class-05/audit-2026-27) | `class_05_audit_summary.md`<br>`class_05_2026_27_audit_manifest.csv`<br>`class_05_official_api_snapshot.json` | 3 GET-200 (544p) / 3 Term-II 403 (Sale started) / 3 Term-III 403 |
| **6** | [`tn-class-06: scert/class-06/audit-2026-27`](https://github.com/Eaglesiva/tn-class-06/tree/scert/class-06/audit-2026-27) | `class_06_audit_summary.md`<br>`class_06_2026_27_audit_manifest.csv`<br>`class_06_official_api_snapshot.json` | 5 GET-200 (864p) / 5 Term-II 403 (Sale started) / 5 Term-III 403 |
| **7** | [`tn-class-07: scert/class-07/audit-2026-27`](https://github.com/Eaglesiva/tn-class-07/tree/scert/class-07/audit-2026-27) | `class_07_audit_summary.md`<br>`class_07_2026_27_audit_manifest.csv`<br>`class_07_official_api_snapshot.json` | 5 GET-200 (880p) / 5 Term-II 403 (Sale started) / 5 Term-III 403 |
| **8** | [`tn-class-08: scert/class-08/audit-2026-27`](https://github.com/Eaglesiva/tn-class-08/tree/scert/class-08/audit-2026-27) | `class_08_audit_summary.md`<br>`class_08_2026_27_audit_manifest.csv`<br>`class_08_official_api_snapshot.json` | 8 GET-200 (2,208p) / 0 GET-403 (Complete) |
| **9** | [`tn-class-09: main`](https://github.com/Eaglesiva/tn-class-09/tree/main) & [`scert/class-09/audit-2026-27`](https://github.com/Eaglesiva/tn-class-09/tree/scert/class-09/audit-2026-27) | 5 refresh JSONs on main (`d6fc546d`);<br>3 Layer 4 pilot diff reports on audit branch | 5 Refreshed on Main (1,664p) + 3 Pilot Verified (840p) = 8 books / 2,504p complete |
| **10** | [`tn-class-10: main`](https://github.com/Eaglesiva/tn-class-10/tree/main) & [`scert/class-10/audit-2026-27`](https://github.com/Eaglesiva/tn-class-10/tree/scert/class-10/audit-2026-27) | English refresh JSON on main (`22f176e2`);<br>Maths TM & EM verification JSONs, visual review results & review summary on audit branch;<br>8-record audit manifest & API snapshot on audit branch | 1 Refreshed (224p) + 1 Match (248p) + 2 Confirmed Newer (720p) + 4 Updates (1,432p) |
| **11** | [`tn-class-11: scert/class-11/audit-2026-27`](https://github.com/Eaglesiva/tn-class-11/tree/scert/class-11/audit-2026-27) & [`official-version-updates`](https://github.com/Eaglesiva/tn-class-11/tree/scert/class-11/official-version-updates) | 32-record manifest, API snapshot (`404f2834...`);<br>24 edition folders with 4 manifests each | 4 Newer (1,152p) + 4 Same (1,304p) + 23 Updates (7,528p) + 1 Unresolved (304p) = 32 books |
| **12** | [`tn-class-12: main`](https://github.com/Eaglesiva/tn-class-12/tree/main) & [`scert/class-12/audit-2026-27`](https://github.com/Eaglesiva/tn-class-12/tree/scert/class-12/audit-2026-27) | 33 refresh JSONs on main (`c15e34ad`);<br>2 edition folders on update branch | 32 Refreshed on Main (9,872p) + 2 Updates (648p) = 34 books / 10,520p complete |

---

## 4. Stored Edition Page-File Inventory (Branches & Main)

| Location | Branch / Purpose | Books / Groups | Page PDFs | Structural Status |
| :--- | :--- | :---: | :---: | :--- |
| **Class 9 Production Main** | `main` (Live delivery) | 5 refreshed + 3 legacy | 2,504 | 100% Contiguous; PyMuPDF validated |
| **Class 10 Production Main** | `main` (Live delivery) | 1 refreshed + 3 legacy | 1,192 | 100% Contiguous; PyMuPDF validated |
| **Class 12 Production Main** | `main` (Live delivery) | 32 refreshed | 9,872 | 100% Contiguous; PyMuPDF validated |
| **Class 10 Update Branch** | `scert/class-10/official-version-updates` | 4 edition groups | 1,432 | Stored in unit directories |
| **Class 11 Update Branch** | `scert/class-11/official-version-updates` | 24 edition groups | 7,832 | Canonical 1-page PDFs with 4 manifests each |
| **Class 12 Update Branch** | `scert/class-12/official-version-updates` | 2 edition groups | 648 | Canonical 1-page PDFs with 4 manifests each |
| **Total Tracked Single-Page PDFs** | — | — | **23,480** | **Strictly verifiable across GitHub trees** |

---

## 5. Local Antigravity Workspace Hygiene & Zero Download Policy

- **Master PDF Persistence**: **0 bytes**. No full master textbook PDFs are stored on local disks. All master downloads and page slicing occurred strictly inside ephemeral GitHub Actions runners (`ubuntu-latest`) with runner `/tmp` purged after job completion.
- **Local Artifacts Kept**: Only compact machine-readable index files, metadata JSONs, and markdown tracking registers are preserved locally in `docs/` and tracked on branch `scert/master-edition-tracking`.
- **Viewer Continuity**: Zero changes to production folder names, TOC structures, or viewer routes were made.
