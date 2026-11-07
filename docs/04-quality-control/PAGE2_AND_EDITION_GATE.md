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

## Page-2 link format

For audit branches, prefer commit links:
`https://github.com/Eaglesiva/<repo>/blob/<audit-commit-sha>/<exact-page-2-path>`

The link must point to the actual `page_002.pdf`, `page-002.pdf`, or corresponding Page-2 split file, not to the folder or a guessed filename.
