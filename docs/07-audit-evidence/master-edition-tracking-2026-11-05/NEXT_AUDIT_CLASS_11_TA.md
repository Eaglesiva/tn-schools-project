# [COMPLETED / ARCHIVED] SCERT Class 11 Textbook Edition Reconciliation

> [!NOTE]
> **Status:** COMPLETED & ARCHIVED (2026-11-05)  
> All 32 State Board Class 11 textbooks have been reconciled and verified under the 4-tier verification protocol.  
> - **Audit Manifest:** [class_11_2026_27_audit_manifest.csv](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/audit-2026-27/docs/class_11_2026_27_audit_manifest.csv)  
> - **Audit Summary:** [class_11_audit_summary.md](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/audit-2026-27/docs/class_11_audit_summary.md)  
> - **Live API Snapshot:** [class_11_official_api_snapshot.json](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/audit-2026-27/docs/class_11_official_api_snapshot.json)  
> - **Update Branch (7,832 pages):** [scert/class-11/official-version-updates](https://github.com/Eaglesiva/tn-class-11/tree/scert/class-11/official-version-updates)  
> - **Master Index:** Recorded in [SCERT_MASTER_EDITION_INDEX.csv](https://github.com/Eaglesiva/tn-class-10/blob/scert/master-edition-tracking/docs/SCERT_MASTER_EDITION_INDEX.csv)  

---

# அடுத்த பணி — Class 11 Official Catalog vs GitHub Edition Reconciliation

**பணி நிலை:** Class 9 comparison evidence மற்றும் Class 10 ஏழு pending comparisons closeout ஆன பிறகு தொடங்க வேண்டிய audit  
**முக்கிய கட்டுப்பாடு:** ஏற்கெனவே Download / Split / Commit செய்யப்பட்டுள்ள 2026–27 editions-ஐ மீண்டும் உருவாக்க வேண்டாம். முதலில் remote audit evidence-ஐ முழுமைப்படுத்து.

## 1. ஏற்கெனவே உள்ள ஆதாரங்கள்

Repository: [Eaglesiva/tn-class-11](https://github.com/Eaglesiva/tn-class-11)

Edition branch: [`scert/class-11/official-version-updates`](https://github.com/Eaglesiva/tn-class-11/tree/scert/class-11/official-version-updates)

இந்த branch-ல் ஏற்கெனவே உள்ள report கோப்புகள். இவற்றை மீண்டும் உருவாக்க வேண்டாம்:

- [முழு Class 11 verification report](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/official-version-updates/docs/class11_verification_report.md)
- [Batch 1 report](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/official-version-updates/docs/class_11_batch_1_report.md)
- [Batch 2 report](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/official-version-updates/docs/class_11_batch_2_report.md)
- [Batch 3 report](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/official-version-updates/docs/class_11_batch_3_report.md)
- [Batch 4 report](https://github.com/Eaglesiva/tn-class-11/blob/scert/class-11/official-version-updates/docs/class_11_batch_4_report.md)

முந்தைய verification report Class 11-ல் 32 core books/items என்று வகைப்படுத்துகிறது:

- **4 `GITHUB_IS_NEWER`**: Tamil Full; Maths TM Vol-1/Vol-2; Maths EM Vol-1. பழைய report பரிந்துரை: `KEEP_EXISTING`.
- **4 `SAME_VERSION`**: Maths EM Vol-2; History TM; Geography TM; Political Science TM. பழைய report பரிந்துரை: `KEEP_EXISTING`.
- **24 `VERSION_DIFFERENT`**: Physics TM/EM Vol-1/Vol-2, Chemistry TM/EM Vol-1/Vol-2, Botany TM/EM, Zoology TM/EM, Computer Science TM/EM, Commerce TM/EM, Accountancy TM/EM, Economics TM/EM, English, History EM, Geography EM, Political Science EM.

இவை முந்தைய audit முடிவுகள் மட்டுமே; புதிய live API பதிவு மற்றும் முழு page-level proof உடன் ஒவ்வொரு முடிவையும் மீண்டும் இணைக்க வேண்டும்.

## 2. GitHub-ல் ஏற்கெனவே உள்ள 2026–27 edition inventory

Remote Git tree-ல் `scert/class-11/official-version-updates` branch-இல் 24 page-set groups உள்ளன; மொத்தம் **7,832 single-page PDFs**:

| பாடம் / Medium | Volumes | PDF pages |
|---|---:|---:|
| Accountancy EM | Full | 352 |
| Accountancy TM | Full | 368 |
| Botany EM | Full | 376 |
| Botany TM | Full | 384 |
| Chemistry EM | Vol-1 304 + Vol-2 320 | 624 |
| Chemistry TM | Vol-1 328 + Vol-2 344 | 672 |
| Commerce EM | Full | 336 |
| Commerce TM | Full | 336 |
| Computer Science EM | Full | 328 |
| Computer Science TM | Full | 328 |
| Economics EM | Full | 288 |
| Economics TM | Full | 336 |
| English | Full | 216 |
| Geography EM | Full | 296 |
| History EM | Full | 320 |
| Physics EM | Vol-1 320 + Vol-2 328 | 648 |
| Physics TM | Vol-1 320 + Vol-2 336 | 656 |
| Political Science EM | Full | 320 |
| Zoology EM | Full | 304 |
| Zoology TM | Full | 344 |
| **மொத்தம்** | **24 page sets** | **7,832** |

அதாவது Batch 1–4 ingestion ஏற்கெனவே remote-ல் உள்ளது. இந்த 7,832 page files-ஐ மீண்டும் split அல்லது upload செய்ய வேண்டாம்.

## 3. Audit செய்ய வேண்டிய பணி

### Step A — Official catalog snapshot

1. Live endpoint `https://emis3.tnschools.gov.in/api/get_scert_books`-ஐ இப்போது மீண்டும் fetch செய்.
2. Class 11-க்கு சேர்ந்த அனைத்து API பதிவுகளையும் exact JSON fields உடன் சேமி. Raw snapshot-ஐ மாற்றாமல் வைத்துக் கொண்டு retrieval timestamp UTC, snapshot SHA-256 சேர்க்கவும்.
3. State Board core books, medium, volume, annual/term, minority language, CBSE/other supplementary items ஆகியவற்றை தனித்தனியாக வகைப்படுத்தவும்.
4. Class 11-ன் முந்தைய 32-item verification report-ல் இல்லாத/புதிய API records ஏதும் உள்ளதா எனக் கண்டறி.

### Step B — Existing GitHub content inventory

1. Class 11 `main` branch-ன் exact commit SHA-ஐ பதிவு செய்.
2. `scert/class-11/official-version-updates` branch-ன் exact commit SHA-ஐ பதிவு செய்.
3. ஒவ்வொரு subject/medium/volume-க்கும்:
   - main `pages.json` count + order + actual page files
   - update branch `edition.json`, `manifest.json`, `pages.json`
   - edition path-இல் உள்ள actual page PDFs
   - per-page SHA-256 (manifest-ல் இருந்தால்)
   - source URL, downloaded date, raw page-2 imprint
   ஆகியவற்றை பதிவு செய்.
4. Vol-1 / Vol-2 தனித்தனி master files-ஐ ஒன்றாகத் தவறாக எண்ணாதே. Subject/medium/volume identity தெளிவாக இருக்க வேண்டும்.

### Step C — Current official edition verification

1. ஒவ்வொரு API record-ஐ exact filename + URL + class + subject + medium + volume உடன் map செய்.
2. HTTP status, final URL, content type, content length, ETag/Last-Modified ஆகியவற்றைப் பதிவு செய். HTTP 403 வந்தால் அது retrieval block மட்டுமே; வெளியிடப்படவில்லை என்று தானாக முடிவு செய்யக்கூடாது.
3. ஏற்கெனவே உள்ள edition metadata-ல் official master SHA-256 இல்லை என்றால் அதை `NOT_CAPTURED` என்று குறி. GitHub page SHA-256-ஐ official master SHA-256 எனப் பயன்படுத்தாதே.
4. Page-2 imprint text extraction image-only என்றால் page-2 image-ஐ artifact-ஆக வைத்துப் பார்வை மூலம் சரிபார். Academic year 2026–27 மற்றும் printed edition/reprint year தனித்தனி fields.
5. ஒரு old edition-ம் official current master-மும் வேறுபட்டால், முதலில் exact difference list தயாரி. Existing official update branch edition ஏற்கெனவே இருக்கும்போது அதை மறுபடியும் download/split செய்யாதே; முதலில் ஏற்கெனவே stored official split-ஐ ஆய்வு செய்.

### Step D — Page-level comparison

1. Class 11 main page set-ஐ அதே order-ல் reconstruct செய்து official/stored edition-உடன் compare செய்.
2. Update branch 24 page sets-க்கு:
   - `manifest.json` entries vs `pages.json` count
   - Git tree actual page file count
   - page number continuity
   - each page PDF opens, exactly one page, renderable, non-zero size
   ஆகியவற்றைச் சோதித்து `split_validation.json` உருவாக்கு.
3. Official update edition vs main existing copy ஒவ்வொரு பக்கத்தையும் normalized text மற்றும் rendered image comparison மூலம் ஒப்பிடு. Page count match மட்டும் போதாது.
4. வேறுபட்ட பக்க எண்கள், missing/extra/reordered pages அனைத்தையும் report-ல் சேர்க்கவும்.
5. 4 `GITHUB_IS_NEWER` மற்றும் 4 `SAME_VERSION` பழைய report முடிவுகளை முதலில் cross-check செய்து, அதிகாரப்பூர்வ API மற்றும் page evidence இல்லாமல் அவற்றை இறுதி முடிவாக ஏற்காதே.

### Step E — Output files / commits

இந்த audit branch-ஐ உருவாக்கு அல்லது ஏற்கெனவே உள்ளதா என்று சரிபார்:

`scert/class-11/audit-2026-27`

அதில் மட்டும் கீழ்கண்ட கோப்புகளை commit செய்:

- `docs/class_11_official_api_snapshot.json` — raw live API snapshot (or exact filtered raw records plus separate whole snapshot)
- `docs/class_11_2026_27_audit_manifest.csv` — one row per official book/volume/medium
- `docs/class_11_audit_summary.md` — three-bucket summary and known limitations
- `docs/class_11_local_vs_official_comparison.json` — every page comparison summary/differing pages
- `docs/class_11_existing_edition_inventory.json` — exact GitHub branches, commits, paths, page counts and checksums
- per-volume `split_validation.json` only if you actually run the structural checks

Master PDFs stay in runner temporary storage only. Do not upload masters to Git.

### Step F — Update the central tracker

After committing the class evidence:

- Append verified Class 11 records to [Master Edition Index CSV](./SCERT_MASTER_EDITION_INDEX.csv) on `scert/master-edition-tracking`.
- Update [Master Edition Tracker](./SCERT_MASTER_EDITION_TRACKER.md).
- Keep both `github_audit_branch` and `github_edition_branch` separate.
- Distinguish official API listed, sale announced, CDN 200/403, printed imprint, GitHub edition existence, and final page-equivalence result.
- Do not claim a book is missing until main + update branch + volume mapping have all been checked.

## 4. Three final buckets

1. **Official listed + GitHub current/matching** — only evidence-backed matches.
2. **Official listed + GitHub older/different/missing/mapping unresolved** — explicitly say what is older or what is not mapped.
3. **Official record/release unresolved / retrieval blocked** — API absent, HTTP 403, invalid PDF, ambiguous volume/medium, etc.

## 5. Safety rules

- No production `main` edits.
- No viewer/index routing changes.
- No overwriting or deleting legacy pages.
- No duplicate download/split of the 7,832 existing update-branch page files without a specific failed validation or comparison reason.
- Do not merge/deploy any update branch.
- This is a catalog and equivalence audit first. Share the final report before deciding whether a new download source or edition replacement is required.
