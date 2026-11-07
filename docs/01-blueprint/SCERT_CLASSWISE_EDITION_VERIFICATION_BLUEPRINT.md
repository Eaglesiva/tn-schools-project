# SCERT Class-wise Edition Verification Blueprint
**Version:** 1.0  
**Last updated:** 2026-11-04  
**Canonical home:** `Eaglesiva/tn-class-10/docs/SCERT_CLASSWISE_EDITION_VERIFICATION_BLUEPRINT.md`

> This document is the operating contract for ChatGPT, Antigravity and any future operator. Follow it before auditing, downloading, splitting, committing or changing a textbook. This process is class-by-class and one official book/volume at a time.

## 1. Non-negotiable rules

1. **Truth over completion claims.** Say `VERIFIED` only when the evidence listed in this document exists. If a source could not be opened, a page could not be compared, or a tool did not run, say `NOT VERIFIED` and state the blocker.
2. Never invent an official URL, publication year, edition, page count, TOC, subject mapping, local path, checksum or successful workflow run.
3. A filename match, equal file size, equal page count, matching ETag, or a single matching page is not proof that two whole books are equivalent.
4. Never map two distinct official subjects to the same local PDF merely because their page counts or sizes are similar. A combined official volume may map to multiple local folders only after the exact page sequence and subject boundaries have been demonstrated.
5. Never overwrite, delete, rename, replace, move or re-encode existing book files in `main`. Do not regenerate existing page splits just to test the pipeline.
6. If the current local edition is verified as the same content as the official current copy, **STOP**: do not download a second copy into Git, split again, make duplicate files, or redeploy.
7. If a newer/different official book is confirmed, store it as a **new immutable edition** on a new branch. Keep the existing production edition intact. Do not switch `active_edition`, change `index.html`/viewer routing, merge or deploy without an explicitly reviewed follow-up.
8. Never commit the official master PDF. Download it to the GitHub Actions runner's temporary directory (for example `/tmp`), process it there, and let the runner discard it when the job ends.
9. Do not use `git add .`, `git push --force`, `git checkout -B` against an existing branch, destructive shell commands, or an unreviewed mass commit. Stage only explicit new report/manifest and edition paths.
10. Work in order: Class 1, then 2, 3, 4, 5, and continue upwards. Finish and report one class before starting the next. Within a class, process one official book/volume/medium/term per run.

## 2. Verified source of truth

Use these sources in this order:

- Official SCERT textbook listing: https://tnschools.gov.in/scert-textbook
- Official listing API: https://emis3.tnschools.gov.in/api/get_scert_books
- Official Government textbook CDN base: https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/
- Government textbook distribution notices: https://www.textbookcorp.in/schools
- Official primary-class title/price structure: https://textbookcorp.in/textbook/schools/books

Third-party textbook sites, FlipHTML5 mirrors, blogs, Google Drive copies, and cached search snippets may help find leads, but they are not proof of the official current edition.

### Current release facts verified on 2026-11-04

The Tamil Nadu Textbook and Educational Services Corporation's official notices state:
- 2026–27 Term-I textbooks for Classes 1–3 were released for sale from 25-05-2026.
- 2026–27 Term-II textbooks for Classes 1–7 were released for sale from 22-09-2026.
- Term-I books for Classes 1–3 printed during 2025–26 are explicitly described as obsolete and offered separately at a discount.

Source: https://www.textbookcorp.in/schools

Therefore, do not treat an old Class 1–3 Term-I PDF as current merely because it is already in the repository. Also, do not assume that Term-III 2026–27 has been officially released; verify it from the live official listing and an official notice at the time of that run.

The official price list identifies separate combined volumes for primary classes, such as:
- Classes 1–2: Term-wise Vol-I (Tamil & English) and Vol-II (Maths & EVS).
- Classes 3–5: Term-wise Vol-I (Tamil & English) and Vol-II (Maths, Science & Social Science).

Source: https://textbookcorp.in/textbook/schools/books

This means an official combined volume must not be naively mapped to one single-subject local folder.

## 3. Where code and tools currently live (verified GitHub state)

### Class repositories
The repositories are separate:
- `Eaglesiva/tn-class-01`
- `Eaglesiva/tn-class-02`
- `Eaglesiva/tn-class-03`
- `Eaglesiva/tn-class-04`
- `Eaglesiva/tn-class-05`
- and corresponding class repositories through Class 12.

Each class repository has its own `main` branch and Cloudflare Pages project. A workflow or a book from one class must not be assumed to exist in another class repository.

### Class 1 repo
At the time of this document:
- `Eaglesiva/tn-class-01` has the existing subject/term page-split structure and `pages.json` manifests.
- For example, `tamil/term1/pages.json` enumerates the existing one-page PDFs from `tamil/term1/00_prelims/page_01.pdf` onward. `english/term1/pages.json`, `maths_tm/term1/pages.json` and `science_tm/term1/pages.json` also exist.
- The root contains `index.html`, `viewer.html`, and existing book content.
- The GitHub root/tree inspected on 2026-11-04 did not show a `.github/workflows` directory in this repository. This is a statement about the checked GitHub branch, **not** proof that Antigravity's local workspace has no uncommitted or untracked scripts.

### Class 10 audit and pilot workflows
`Eaglesiva/tn-class-10` currently contains:
- `.github/workflows/scert-preview-page2.yml`
- `.github/workflows/scert-edition-sync.yml`
- `docs/official_api_local_match_manifest.csv`
- `docs/local_master_pdf_reverse_audit.csv`
- `docs/MASTER_EDITION_AUDIT_REPORT.md`
- `docs/OFFICIAL_API_VS_LOCAL_PDF_AUDIT.md`
- `docs/OFFICIAL_GOVERNMENT_CDN_VERIFICATION_PROOF.md`
- `docs/PROJECT_BLUEPRINT_TA.md`

Important limitations found by directly reading the workflows on 2026-11-04:
- The preview workflow checks the `Accept-Ranges` response header, but then makes a normal full `GET` without a `Range: bytes=...` request. Therefore it does **not** prove an HTTP 206 range-only preview. Its earlier success downloads the full master PDF to runner scratch.
- The sync workflow is not a safe generic Class 1–12 workflow yet. It contains Class 10 Tamil-specific hard-coded MD5/page-count checks and hard-coded imprint/TOC metadata (including a 2024 imprint). Its fallback TOC for other books is only a whole-book placeholder, not a verified extracted TOC.
- Do not reuse either workflow as a generic cross-class tool without removing and testing all Class 10 assumptions. The previous Class 10 pilot proves a temporary-runner download/split/push mechanism; it does not prove that every other class or subject has a correct mapping or edition.

Antigravity's local-only environment is not visible to a GitHub reader. The agent must inventory its actual local scripts, project root, installed tools and uncommitted files before claiming they exist. Record exact paths and relevant evidence. Do not guess.

## 4. Required per-book workflow (one item per run)

### Step A — Refresh the official record
1. Fetch the live official API/listing at run time. Save the exact API row/JSON snapshot in the run artifact.
2. Identify the record by **class + official subject/title + medium + term + volume**. Preserve the exact official filename and URL from the API.
3. Verify that the URL uses the expected official Government CDN host and that the HTTP response is successful.
4. Capture the retrieval timestamp in UTC, HTTP status, final URL after redirects, Content-Length, ETag/Last-Modified (if present), and response content type.
5. If an API record is ambiguous, duplicated, incorrectly named, or cannot confidently be mapped to a requested subject, stop that item as `API_MAPPING_UNRESOLVED`. Do not repair ambiguity by guessing.

### Step B — Discover the existing local/hosted copy
1. Read the class repository's recursive Git tree at the exact `main` commit SHA and capture that SHA.
2. Locate the correct subject/medium/term folder and its `pages.json` (or other documented page manifest). Read the manifest; do not infer page order by alphabetically sorting directories.
3. Check that every listed local page path exists in the same repository and that the sequence is complete, unique and in its declared order.
4. For a combined official volume, define and prove how its page sequence maps to the local subject folders. Use official contents/TOC and page content, not the filename alone.
5. If multiple plausible local candidates exist, record all candidates and stop as `LOCAL_MAPPING_UNRESOLVED`. Never choose the closest-looking subject name automatically.

### Step C — Download and inspect the official master
1. Download only the single selected PDF to a temporary runner path such as `/tmp/scert/<class>/<item>/official-master.pdf`.
2. For reliable processing, a normal complete download is acceptable for this first implementation. Do not claim range-only transfer unless a real request with a `Range` header returned HTTP 206 and a valid `Content-Range`, and the transferred-byte count confirms only the requested range.
3. Verify HTTP 200 (unless using a proven range workflow), PDF content type where available, `%PDF-` magic bytes, non-zero length, complete transfer length, and that PyMuPDF can open it.
4. Calculate SHA-256 and MD5 from the actual downloaded bytes. Treat ETag as an HTTP metadata field, not automatically as MD5; only compare it to MD5 with the relevant single-part/object caveat stated.
5. Record actual PDF page count, PDF metadata, page dimensions/rotation where useful, and extract selectable text from PDF page 2 (zero-based index 1).
6. Render official page 2 as a PNG (e.g. 150–200 DPI) and upload it as a workflow artifact. Preserve the exact page-2 extracted text and a JSON report alongside it.
7. Record the **printed edition/reprint/imprint** exactly as shown. If page 2 has no readable imprint, record `IMPRINT_NOT_READABLE`; do not invent a year or use the current academic year as the printed edition.

### Step D — Reconstruct and compare the existing repository edition
1. Using the ordered page list from the local `pages.json`, open each listed one-page PDF and append it to a temporary local composite PDF in exactly that order. Do not write to the checked-out book folders.
2. Verify each source page PDF opens, contains exactly one page, and is not empty. Verify sequence continuity and final assembled page count.
3. Extract local page-2 text and render local page 2 using the same PyMuPDF version/DPI as the official page. Upload the local page-2 image as an artifact too.
4. Compare the official and local page-2 imprint text and rendered page. Record exact text, normalized text comparison, image dimensions and an explicit visual difference/similarity metric.
5. A page-2 match alone is not proof of whole-book equivalence. Compare all pages when the local copy can be reconstructed: page count, normalized extracted text per page, page dimensions/rotation, and same-engine rendered page fingerprints/difference metrics. Record every differing page number. Never silently ignore missing, reordered or extra pages.
6. If the PDF is image-only and text extraction is empty, mark text as unavailable. Provide the rendered images for manual review. OCR may be used only as a clearly labelled fallback and never as the only proof.
7. Record local file paths, GitHub blob SHAs, file sizes and the exact `main` commit SHA used. A Git blob SHA is not a PDF's SHA-256.

### Step E — Decide the outcome

Use only one of these evidence-based result labels:
- `EXACT_MASTER_SHA256_MATCH` — full official master and the actual local master bytes are available and SHA-256 matches.
- `ALL_PAGES_CONTENT_MATCH` — local book was reconstructed and every page has passed the declared text + visual comparison gates, but the original master-byte hash is not the same/available.
- `PARTIAL_PAGE_MATCH` — some pages match and one or more pages differ or cannot be checked.
- `OFFICIAL_NEWER_OR_DIFFERENT` — official book differs materially from the current local edition; attach evidence of the differences and confirm printed imprint/current official distribution separately.
- `LOCAL_COPY_MISSING` — no credible local page set was found.
- `OFFICIAL_RECORD_MISSING` — no matching item is present in the live official listing/API.
- `API_MAPPING_UNRESOLVED` — official API entry cannot be mapped confidently.
- `LOCAL_MAPPING_UNRESOLVED` — local page set/subject mapping cannot be established.
- `MANUAL_REVIEW_REQUIRED` — evidence is incomplete, unreadable or contradictory.
- `DOWNLOAD_FAILED_RETRY_REQUIRED` — the official download failed validation or did not complete.

Do not use `VERIFIED_CONTENT_EQUIVALENT` based only on page count, file size, file name, or an inferred alias. Do not label an imprint year as “current” solely because the same URL is currently listed. Keep these separate:
- academic/distribution year (e.g. 2026–27),
- printed first/revised/reprint edition and imprint date,
- date checked,
- current government distribution confirmation.

### Step F — Only if a new edition is proven necessary
1. Create a new branch from the exact current class `main` SHA. Use a unique branch name, e.g. `scert/class-01/2026-27-term1-vol1-tamil-english`. If the branch already exists, stop and inspect it; never reset it with `checkout -B`.
2. Keep the official master under `/tmp` only.
3. Split with PyMuPDF into one PDF per source page, preserving original page order. Use a new immutable directory such as `<subject>/editions/<edition-id>/pages/page-001.pdf` and a generated page manifest. For a combined volume, use a properly named volume directory and maintain an explicit subject/page-range map.
4. Validate every generated page file: PDF magic bytes, non-zero size, opens successfully, exactly one page, renderable, and within the current Cloudflare Pages per-asset size limit. Record any limit check and date; do not assume limits without checking the official provider documentation.
5. Extract or manually verify TOC/unit boundaries from the official book. Never generate a fabricated “full book” TOC and present it as extracted.
6. Generate edition metadata from actual extracted values: official URL, API record identity, academic/distribution year, printed imprint, download date, hashes, page count, and TOC verification status. Unknown values remain `null` / `UNKNOWN`.
7. Check whether each new page is byte-identical or content-identical to an existing page before committing. Do not re-add an identical split set just because the official master PDF differs in compression/metadata.
8. Stage only the new immutable edition files and the specific metadata/report files. Explicitly confirm the master PDF is not staged. Never stage `index.html`, viewer files, existing `pages.json`, legacy book files, quizzes, answers or unrelated changes in this ingestion commit.
9. Run validation on the new branch, provide artifact links and commit SHA. Do not merge or deploy automatically.

## 5. Evidence package required for every run

Every run must produce:
- `official_api_record.json` — raw exact matching API record + retrieval timestamp.
- `official_download_report.json` — final URL, HTTP metadata, byte count, SHA-256, MD5, PDF page count, imprint extract.
- `official_page_2.png` — rendered official page 2.
- `local_page_2.png` — rendered page 2 reconstructed from existing local pages.
- `comparison_report.json` — local Git commit SHA, page manifest, page count, page 2 comparison, every-page comparison summary and differing pages.
- `decision.md` — final status, facts, unknowns, evidence references, and whether any commit was made.
- If a new edition is required: `split_validation.json`, verified `pages.json`, `toc.json` (only if actually extracted/verified), and `edition.md`.

The artifact/report must distinguish:
- checked and succeeded,
- checked and failed,
- not checked,
- unavailable due to tool/network limitation.

Never replace `not checked` with `passed`.

## 6. Batch order and first Class 1 pilot

### Class-by-class order
Class 1 → Class 2 → Class 3 → Class 4 → Class 5. Do not run Classes 1–5 together.

### First selected item
Start with the current official Class 1 **2026–27 Term-I Vol-I (Tamil & English)** entry from the live official API, if it is still listed and downloadable. Do not use the separate `TAMIL - For CBSE Schools` entry as a substitute for the State Board combined volume.

Existing candidate local page manifests to inspect:
- `tamil/term1/pages.json`
- `english/term1/pages.json`

Do not assume that simply concatenating these two page sets is correct. Confirm the exact official combined-book order and boundaries using its TOC and page content. If the mapping cannot be proved, set `LOCAL_MAPPING_UNRESOLVED` and report what is missing.

After Term-I Vol-I is decided, proceed in separate runs to the other current official Class 1 items (for example Term-I Vol-II Tamil/English medium and Term-II volumes), after refreshing the live API. Never assume the term list or filenames from the old CSV are still current.

The Class 1 legacy manifest previously stored in this audit repository contains a separate `TAMIL(CBSE)` record as well as combined `TAMIL & ENGLISH` volumes. Those entries are not interchangeable. Treat the old CSV as a discovery snapshot only; refresh the live official API before each decision.

## 7. Required Antigravity truthful-report format

At the end of each item, report exactly:

| Field | Required value |
|---|---|
| Class / subject / medium / term / volume | Exact official label |
| Official API | URL + record ID/identity + retrieval timestamp |
| Official master | Downloaded / failed / not attempted |
| Official size / SHA-256 / page count | Actual measured values or UNKNOWN |
| Page 2 imprint | Exact extract or NOT READABLE |
| Local repository | Repo + main commit SHA |
| Local page manifest | Exact path + listed page count |
| Local page 2 | Exact Git path + displayed/compared status |
| All-pages comparison | MATCH / PARTIAL / DIFFERENT / NOT DONE |
| Final decision | One allowed label from Section 4E |
| Git changes | NONE / report-only / new-edition branch + commit SHA |
| Unchecked items | Explicit list |

A final sentence must say either:
- `No existing main-branch book files were changed.`
- or list exactly which new files were committed and to which branch.

Do not use “100%”, “latest”, “current”, “officially verified”, “download successful”, “split successful”, or “committed” unless the corresponding measurements, logs, artifacts or Git commit are present.

## 8. New-chat handoff rule

For every fresh chat or new Antigravity session:
1. Read this blueprint first.
2. Read the latest audit report and manifest, but treat them as historical snapshots until the official API is refreshed.
3. Inspect the exact target class repository and current `main` commit.
4. State the last completed class/item and its evidence artifacts.
5. Continue with the next unfinished item; do not repeat a completed comparison unless its source changed or the prior evidence is missing/invalid.

**This blueprint is the policy.** Workflows, local scripts and AI summaries are implementation aids; they do not override these rules.

## 9. Class-batch orchestration (updated 2026-11-04)

The user-facing unit of work is **one whole class at a time**. The processing unit inside that class is **one official book/volume at a time, sequentially**. Do not force the user to create a separate prompt or manually trigger a separate workflow for every book.

For a class batch:

1. Fetch the complete live official API response once at the start. Save the raw response (not just the chosen record) as class_<N>_official_api_snapshot.json, plus retrieval UTC time and response SHA-256.
2. Enumerate every record for the requested class, including all available terms, volumes, language/medium combinations and special categories. Keep the exact API identity (class, subject/title, term, medium IDs/names, file name, URL, type). Do not silently omit non-Tamil/English records; classify scope explicitly.
3. Create an ordered queue from those live records. Separately check each official URL's HEAD/GET response, HTTP status, content type, content length, last-modified and ETag. A price-list title is not proof that a current PDF is live. A filename or old manifest row is not proof either.
4. Process the queue sequentially with max concurrency = 1. One item downloads to a unique temporary /tmp location, is validated, inspected, compared, and then the master is deleted before the next item's download begins. Do not download the entire class's master PDFs at once.
5. Store per-item result artifacts and one master class manifest with statuses such as QUEUED, IN_PROGRESS, MATCHED_NO_UPDATE_NEEDED, NEW_EDITION_CONFIRMED, MAPPING_UNRESOLVED, NOT_LISTED, URL_NOT_AVAILABLE, DOWNLOAD_FAILED, MANUAL_REVIEW_REQUIRED, SPLIT_VALIDATED, and COMMITTED_TO_AUDIT_BRANCH.
6. A failed or ambiguous item must not terminate the other items. Record its exact error and continue with the next item. Retry only failed items, not already completed items. Use a checkpoint so a rerun resumes at the first unfinished item.
7. Existing books that are verified as already matching the current official edition get MATCHED_NO_UPDATE_NEEDED; do not create duplicate split files or upload them again.
8. For every item labelled NEW_EDITION_CONFIRMED, prepare that new edition only after the comparison evidence is complete. Split only that item. Keep all old production files intact. Commit new files only to a new class audit/edition branch, with explicit paths; never merge or deploy automatically.
9. Finish the whole class queue and publish one class-level summary: official API records found, in-scope entries, URLs available, URLs unavailable, exact/whole-content matches, new/different books, unresolved mappings, failed downloads, books split, commits, and books not yet checked. Counts must reconcile to the raw API snapshot.
10. Stop after that one class. Do not start the next class until the user has received the completed class summary.

### Term III release handling

A title appearing in the Corporation's textbook price list does not establish that the 2026–27 PDF has been released or is downloadable. For example, the official primary textbook price list displays Term-I, Term-II and Term-III titles for Classes 1–5, while the current public sale notice found on 2026-11-04 announces the 2026–27 Term-II sale for Classes 1–7 from 22-09-2026. The notice does not give a Term-III sale/release date.

Sources:
- https://textbookcorp.in/textbook/schools/books
- https://www.textbookcorp.in/

Therefore:
- Check the live API and official URL for each Term-III book at the time of the class audit.
- If the live API entry is absent, report NOT_LISTED_AS_OF_<UTC_DATE>.
- If an API entry exists but its URL is unavailable or returns an error, report URL_NOT_AVAILABLE or DOWNLOAD_FAILED.
- Do not predict a release month or infer a release date from the academic calendar.
- Do not classify an unavailable future term as obsolete, missing content, or a failed local book.
- A future check can be run later using a fresh API snapshot.

### Correction note — Class 1 Term-I Vol-I pilot (run 41742395830)

The pilot successfully downloaded the official Class 1 Term-I Vol-I PDF to runner temporary storage, rendered the official page 2 and local Tamil page 2, captured the official metadata, and uploaded an evidence artifact. Its branch commit added only:
- .github/scripts/audit_class1.py
- .github/workflows/scert-audit-class1.yml

GitHub compare confirmed the branch was one commit ahead of the exact Class 1 main commit, with no existing book/page files changed.

The artifact shows:
- Official PDF: 227,062,369 bytes; 176 PDF pages; SHA-256 a1f3ed937c267805294d7d2dcf545e65b7746c8f0a0d413bcd8d427907f8bf2d.
- Official page 2: முதல் பதிப்பு - 2026.
- Local Tamil page 2: முதல் பதிப்பு - 2018, revised in 2019, 2020 and 2022.

This is direct evidence of a printed-edition mismatch. However, the pilot script did not reconstruct the local Tamil+English composite PDF and did not compare every page. It only summed the manifest counts (81 Tamil + 65 English = 146), inspected the Tamil page 2, and compared that sum with the official 176-page count. Thus the correct reporting is:
- PAGE2_IMPRINT_MISMATCH_CONFIRMED
- DECLARED_LOCAL_PAGE_COUNT_SUM=146
- OFFICIAL_PDF_PAGE_COUNT=176
- ALL_PAGES_COMPARISON=NOT_DONE
- COMBINED_VOLUME_PAGE_MAPPING=NOT_PROVEN

The pilot's broad OFFICIAL_NEWER_OR_DIFFERENT label may be retained as a preliminary edition finding based on the page-2 imprint, but it must not be described as a completed all-pages content comparison. Do not rerun the same official Vol-I download just to repeat the pilot. Reuse its evidence; complete the missing local page reconstruction/TOC mapping only if needed before preparing the new edition.

### Class 1 continuation after the pilot

- First perform a complete live API inventory of all Class 1 records for the current year and every term/volume/medium. Do not limit the API query to Term-I Vol-I.
- Mark the already audited Term-I Vol-I as PILOT_EVIDENCE_AVAILABLE; reuse its downloaded-report and page-2 image artifacts. Do not redownload it unless its live API record, URL, ETag/Last-Modified or expected current edition has changed.
- Continue with all other currently listed and downloadable Class 1 records in deterministic sequence: Term-I Vol-II, Term-II Vol-I, Term-II Vol-II, and any other records actually returned by the live API. This is a discovery order, not an assumption that every title is published.
- Term-III must be discovered from the live API and URL checks. Do not assume it is present or absent based only on the price list.
- At class completion, reconcile the manifest record count to the raw API snapshot. Every API row must have a visible status; do not silently skip any row.
