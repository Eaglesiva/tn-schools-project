# Page-2 and Full-Edition Verification Gate

## Non-negotiable sequence

1. Identify Class + Subject + Medium + Term/Annual + Volume.
2. Open the official SCERT/School Education listing and confirm the exact official download URL.
3. Open the official master PDF. Record the PDF page count and the exact Page-2 First Edition / Revised Edition / Reprint imprint.
4. Record the corresponding Page-2 PDF from the GitHub candidate branch/main using an immutable commit link.
5. Compare the printed imprint and page count.
6. Compare all pages or compare the master PDF hash against the local master hash. Where neither is possible, remain PENDING.
7. Compare table of contents, section boundaries, Book-back question locations and lesson order.
8. Check `pages.json` and every referenced page file; confirm no page gaps, duplicates or broken links.
9. Test the viewer using the proposed active edition.
10. Only then set CURRENT or ARCHIVE and update production main.

## Critical distinctions

- Academic year (e.g. 2026–27) is the school distribution cycle.
- Printed imprint year (e.g. First Edition 2019 / Reprint 2024) is the publication statement printed inside the book.
- Same Page-2 imprint does not prove same book contents.
- Same total page count does not prove same book contents.
- Successfully split PDFs do not prove the pages match the previous edition.
- A 403 on an official PDF is a blocked/unavailable source at the time checked; it does not authorize using an older book as if it were the new edition.

## Two-copy decision rule (mandatory)

- Page 2-ஐ ஒவ்வொரு candidate PDF-க்கும் திறந்து exact imprint / printed year-ஐப் பதிவு செய்யவும். Page 2 வேறுபாடு old/new candidate-ஐ அடையாளம் காட்ட உதவும்.
- இரண்டும் ஒரே edition/year என்று Page 2 காட்டினால், Archive முடிவுக்கு முன் முழு content identity-ஐ 100% சரிபார்க்கவும்: master SHA-256 அல்லது எல்லா page Blob SHA-கள், page count/order, manifest, TOC மற்றும் book-back பகுதிகள்.
- 100% identical என்றால் ஒரு canonical copy மட்டும் Active-ல் இருக்கும்; duplicate Archive-க்கு செல்லாது (`IDENTICAL_DUPLICATE_NO_ARCHIVE`).
- Same imprint இருந்தும் content வேறுபட்டால் `SAME_EDITION_CONTENT_MISMATCH_REVIEW`; automatic old/new split அல்லது deletion தடை.
- ஒரே புத்தகம் மட்டும் இருந்தால் அதன் official current status-ஐ உறுதி செய்து `SINGLE_CURRENT_EDITION`, `LEGACY_ONLY_RELEASE_PENDING` அல்லது `EDITION_UNVERIFIED` என்று தெளிவாகப் பதிவு செய்யவும்.

## Page-2 link format

For audit branches, prefer commit links:
`https://github.com/Eaglesiva/<repo>/blob/<audit-commit-sha>/<exact-page-2-path>`

The link must point to the actual `page_002.pdf`, `page-002.pdf`, or corresponding Page-2 split file, not to the folder or a guessed filename.


## Official Page-2 links and partial-preview rule (added 2026-11-09)

Keep these links separate in every book record:

1. **Official listing page:** `https://tnschools.gov.in/scert-textbook`
2. **Official full-PDF download:** the exact SCERT/CDN URL returned by the official listing/API. Do not construct or guess a filename.
3. **Official PDF opened at Page 2:** append `#page=2` to that exact PDF URL. This asks a PDF viewer to open at page 2; it is a navigation fragment, **not** a separate Page-2-only download endpoint and does not by itself prove that the whole PDF will not be transferred.
4. **GitHub Page-2 proof:** link directly to the stored one-page `page-002.pdf` / `page_002.pdf` on an immutable commit SHA.
5. **Page map:** link to that same commit's `pages.json`.

### When may a link be called a Page-2-only / range preview?

Only after a real request to the official PDF has been tested with a `Range: bytes=start-end` request and all of the following are recorded:

- HTTP response is `206 Partial Content`, not `200 OK`.
- `Content-Range` identifies the returned byte interval and total object length.
- Returned byte count matches the requested interval and is less than the complete PDF length.
- A browser or PDF.js test can render Page 2 from those range responses without first downloading the entire master PDF.

`Accept-Ranges: bytes` alone is not sufficient. A `#page=2` link alone is not proof of partial transfer. If the checks above have not been run, label the range preview `NOT_VERIFIED` and retain the official full-PDF link plus the GitHub one-page Page-2 link. Do not invent a separate official Page-2 URL.

**Known limitation:** the earlier Class 10 preview workflow checked the `Accept-Ranges` header but then used a normal full `GET`; that run did not demonstrate a range-only preview. Re-test the actual official PDF URL before marking any source `RANGE_PREVIEW_VERIFIED`.
