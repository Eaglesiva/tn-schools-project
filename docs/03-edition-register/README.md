# Edition Register — Classes 1–12

**One-click master document:** [MASTER CROSS-VERIFICATION INDEX](MASTER_CROSS_VERIFICATION_INDEX.md) — all 12 class registers and their direct Page-2 / official-source links in one file.

Each class has its own register file. The register is the single place to answer:

- Which exact book is under review?
- Which official SCERT distribution entry and academic year does it belong to?
- What does Page 2 say (printed first/revised/reprint imprint)?
- What is the direct one-click GitHub Page-2 PDF link?
- Where are the complete page set and `pages.json` located?
- What are the official and local page counts?
- What did the full-book comparison show?
- Which commit/branch holds the evidence?
- Is it CURRENT, ARCHIVE, PENDING, or BLOCKED?

## Mandatory fields for every book record

| Field | Meaning |
|---|---|
| Book ID | Stable ID such as `C01-T1-V1-TAM-ENG` |
| Class / Subject / Medium | Exact book identity |
| Term / Volume | Exact published structure |
| Academic year | Distribution / school-use year, e.g. 2026–27 |
| Printed imprint | Exact Page-2 First Edition / Revised / Reprint wording |
| Official source | Official SCERT / Textbook Corporation URL |
| Official PDF pages | Official master page count |
| GitHub source | Repository + immutable commit SHA + exact file path |
| Page-2 proof | Direct link to the split Page-2 PDF |
| Page map | Direct link to `pages.json` |
| Main baseline | Existing main branch page count and imprint |
| Comparison | SHA / page-level / text / visual comparison status |
| TOC / Book-back check | Whether combined-volume boundaries and questions map correctly |
| Decision | CURRENT / ARCHIVE / PENDING / BLOCKED |
| Reason | Plain-language reason and unresolved work |

## Link rule

Use immutable commit-SHA GitHub links where possible, for example:

`https://github.com/Eaglesiva/tn-class-01/blob/<commit-sha>/<exact-page-2-path>`

Do not use a moving branch URL as the only evidence link. Keep a separate link to the official source PDF and, where stored, the local full-book page map.

## Status meanings

- `CURRENT`: approved for production after all required comparisons and viewer checks.
- `ARCHIVE`: superseded by an approved current edition; preserve historical questions and evidence.
- `PENDING`: there is a candidate but one or more checks remain.
- `BLOCKED`: an official book is not currently available or source mapping is unresolved.
- `SAME_IMPRINT_CONTENT_DIFFERENT`: Page-2 imprint matches, but the rest of the book differs. This is not an exact edition match.

## Registers

- [Class 1](class-01/edition-register.md)
- [Class 2](class-02/edition-register.md)
- [Class 3](class-03/edition-register.md)
- [Class 4](class-04/edition-register.md)
- [Class 5](class-05/edition-register.md)
- [Class 6](class-06/edition-register.md)
- [Class 7](class-07/edition-register.md)
- [Class 8](class-08/edition-register.md)
- [Class 9](class-09/edition-register.md)
- [Class 10](class-10/edition-register.md)
- [Class 11](class-11/edition-register.md)
- [Class 12](class-12/edition-register.md)
