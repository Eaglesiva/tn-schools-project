# Class 01 — Page 2 and TOC Extraction (2026-11-07)

**Source repository:** Eaglesiva/tn-class-01  
**Source branch:** scert/class-01/audit-2026-27-term1-vol1  
**Immutable source commit:** 838d5c2f335810ed95753327fe0a0b94ad298a63  
**Scope:** Six 2026–27 Term-I / Term-II official volume splits. No merge, no production update, no archive move.

## Method and integrity

- Read each book's existing pages.json and edition.json.
- Confirmed all six Page-2 files exist and are one-page PDFs.
- Extracted selectable text with PyMuPDF where available.
- For image-only Term-II Page-2 files, rendered the split PDF page at 120 DPI and inspected the image directly.
- Scanned the complete split page sets for text-based TOC headings where selectable text was available; for image-only books, inspected the rendered opening pages.
- All six page manifests previously passed continuity and presence checks: 848 listed pages total, 0 missing files, 0 invalid split files in the source branch integrity check.

**Important:** TOC entries below are transcribed from extracted text or direct page-image inspection. A subject's complete page boundary is not approved until every relevant TOC / section start and end has been confirmed.

## Six book records

| Book | Total PDF pages | Page-2 imprint | TOC evidence | Status |
|---|---:|---|---|---|
| Term-I VOL-I (Tamil & English) | 176 | Government of Tamil Nadu — First Edition 2026; © SCERT 2026 | Tamil TOC: PDF page 10. English Contents: PDF page 98. | Page 2 verified; both language TOCs located |
| Term-I VOL-II (Maths & EVS) — Tamil | 144 | Tamil Nadu Government — First Edition 2026; SCERT 2026 | Tamil contents: PDF page 7. | Page 2 verified; second-subject TOC / boundary pending |
| Term-I VOL-II (Maths & EVS) — English | 144 | Government of Tamil Nadu — First Edition 2026; SCERT 2026 | Mathematics Contents: PDF page 7. EVS Contents: PDF page 86. | Page 2 verified; TOC candidates for both sections |
| Term-II VOL-I (Tamil & English) | 144 | Tamil Nadu Government — First Edition 2026; SCERT 2026 | Tamil பொருளடக்கம்: PDF page 10. English TOC not yet located in the inspected opening pages. | Page 2 verified; English TOC pending |
| Term-II VOL-II (Maths & EVS) — Tamil | 120 | Tamil Nadu Government — First Edition 2026; SCERT 2026 | Mathematics பொருளடக்கம்: PDF page 6. EVS TOC pending. | Page 2 verified; second-subject TOC pending |
| Term-II VOL-II (Maths & EVS) — English | 120 | Government of Tamil Nadu — First Edition 2026; SCERT 2026 | Mathematics Contents: PDF page 6. EVS TOC pending. | Page 2 verified; second-subject TOC pending |

## Page-2 source links and exact imprint transcription

### 1. Term-I VOL-I (Tamil & English) — 176 pages

[Open Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol1_tamil_english/pages/page-002.pdf)

Extracted imprint:

- மாநிலக் கல்வியியல் ஆராய்ச்சி மற்றும் பயிற்சி நிறுவனம்
- © SCERT 2026
- தமிழ்நாடு அரசு
- முதல் பதிப்பு - 2026
- (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)

### 2. Term-I VOL-II (Maths & EVS) — Tamil — 144 pages

[Open Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_tm/pages/page-002.pdf)

Extracted imprint:

- தமிழ்நாடு அரசு
- முதல் பதிப்பு - 2026
- (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)
- மாநிலக் கல்வியியல் ஆராய்ச்சி மற்றும் பயிற்சி நிறுவனம்
- SCERT 2026

### 3. Term-I VOL-II (Maths & EVS) — English — 144 pages

[Open Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_em/pages/page-002.pdf)

Extracted imprint:

- Government of Tamil Nadu
- First Edition - 2026
- (Published under New Syllabus in Trimester Pattern)
- SCERT 2026

### 4. Term-II VOL-I (Tamil & English) — 144 pages

[Open Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol1_tamil_english/pages/page-002.pdf)

Direct image inspection confirms:

- தமிழ்நாடு அரசு
- முதல் பதிப்பு - 2026
- (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)
- © SCERT 2026

The PDF page has no selectable text; the above was read from the rendered page image.

### 5. Term-II VOL-II (Maths & EVS) — Tamil — 120 pages

[Open Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_tm/pages/page-002.pdf)

Direct image inspection confirms:

- தமிழ்நாடு அரசு
- முதல் பதிப்பு - 2026
- (புதிய பாடத்திட்டத்தின்கீழ் வெளியிடப்பட்ட முப்பருவ நூல்)
- © SCERT 2026

The PDF page has no selectable text; the above was read from the rendered page image.

### 6. Term-II VOL-II (Maths & EVS) — English — 120 pages

[Open Page 2 PDF](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_em/pages/page-002.pdf)

Direct image inspection confirms:

- Government of Tamil Nadu
- First Edition - 2026
- (Published under New Syllabus in Trimester Pattern)
- © SCERT 2026

The PDF page has no selectable text; the above was read from the rendered page image.

## TOC text extracted

### 1. Term-I VOL-I — Tamil TOC, PDF page 10

- 1. மகிழ்வோடு விளையாடு — printed page 1
- 2. கண்டுபிடி... கண்டுபிடி... — printed page 17
- 3. பாப்பாவோடு பாடலாம்! — printed page 54
- 4. வந்த பாதை — printed page 82

English Contents is at PDF page 98. Extracted entries include:

- Unit 1 — About Me!
  - Hi! Hello!
  - Simba and Chinnu
  - Shake and Jump!
  - Look at me!
- Unit 2 — My Family
  - Anu's Red Ribbon
  - My Finger Family
  - The Big Big Beetroot

The extracted text includes printed page references 88, 89, 100, 109, 120, 135, 143 and 154. Check the original TOC page image before assigning any final subject start/end boundary.

### 2. Term-I VOL-II — Tamil TOC, PDF page 7

Extracted lesson list:

- 1. பந்து எங்கே? — 1
- 2. எனக்குப் பிடித்த பொருள்கள் — 8
- 3. பொம்மைகள் எத்தனை? — 16
- 4. விடுபட்டவை எவை? — 36
- 5. யாரிடம் அதிகம்? — 45
- 6. மொத்த பலூன்கள் — 47
- 7. என்னைச் சுற்றியுள்ள பொருள்கள் — 58
- 8. மீதி பலூன்கள் — 65

The printed title/heading text is imperfectly extracted; the original PDF page is the controlling source. An additional EVS section TOC has not yet been separately identified in the Tamil volume.

### 3. Term-I VOL-II — English Contents, PDF page 7

Mathematics section:

- Unit 1
  - 1. Where is the Ball? — 1
  - 2. Things I Like — 8
  - 3. How Many Toys? — 16
  - 4. What are Missing? — 36
- Unit 2
  - 5. Who has More? — 45
  - 6. Total Balloons — 47
  - 7. Things Around Me — 58
  - 8. Remaining Balloons — 65

### 4. Term-I VOL-II — English Contents, PDF page 86

EVS section entries extracted:

- Unit 1 — About Me
  - My World — 80
  - My Health — 88
  - Nature's Gifts — 102
  - Animals Around Me — 116
- Unit 2 — Around Me

The page-number order in the extracted text is not the same as the visual reading order; check the original page before building the page map. The printed contents page indicates an EVS section around printed pages 80–116, after the Mathematics TOC's listed lesson pages through 65.

### 5. Term-II VOL-I — Tamil TOC, PDF page 10

Direct image inspection confirms the heading தமிழ்ப் பொருளடக்கம் and the following list:

- அலகு 1
  - 1. ஐ... மகிழ்ச்சி! — 1
  - 2. கண்ணாமூச்சி — 7
- அலகு 2
  - 3. கிளிங்... கிளிங்... — 28
  - 4. எதனால்? எதனால்? — 45

The English TOC was not located in the inspected first 20 PDF pages. Do not infer its page number or contents.

### 6. Term-II VOL-II — Tamil Mathematics TOC, PDF page 6

Direct image inspection confirms:

- அலகு I
  - 1. தாகமுள்ள பறவைகள் — 1
  - 2. நிழல் விளையாட்டு — 25
  - 3. எங்களின் புதிய வளையல்கள் — 30
- அலகு II
  - 4. பள்ளி செல்லும் வழியில் — 42
  - 5. என்னால் முடியும். உன்னால் முடியுமா? — 47
  - 6. பெட்டியில் உள்ள வளையல்கள் — 53

### 7. Term-II VOL-II — English Mathematics Contents, PDF page 6

- Unit I
  - 1. Thirsty Birds — 1
  - 2. Shadow Game — 25
  - 3. Our New Bangles — 30
- Unit II
  - 4. On the Way to School — 42
  - 5. I Can. Can You? — 47
  - 6. Bangles in the Box — 53

The separate EVS TOC for both Term-II VOL-II medium editions has not yet been located.

## Pending checks — keep status PENDING

1. Locate and transcribe the English TOC in Term-II VOL-I.
2. Locate and transcribe the EVS TOC in Term-II VOL-II Tamil and English.
3. Locate any separate EVS TOC or confirm the subject structure for Term-I VOL-II Tamil.
4. Confirm all combined-volume section start/end pages from the printed TOC and intervening pages before making production viewer maps.
5. Do not change active_edition, production routing, main branch PDF files, questions, quizzes or archive contents from this text-extraction pass.

**Decision:** All six Page-2 imprints visually/textually confirm First Edition 2026. TOC identification is partial as detailed above. No production merge or archive move is approved by this report.


---

## Final TOC page verification — 2026-11-07 (supersedes the earlier partial-TOC note)

All six books' Page-2 pages and all identified subject TOC pages were rendered and inspected directly. This update closes the earlier *TOC-page-location* gaps. It does **not** claim that the complete subject end-page ranges or production viewer routes have already been tested.

### Page-2 evidence — all six books

| Book | Existing Page-2 split PDF | Page-2 imprint |
|---|---|---|
| Term-I VOL-I Tamil & English (176 pages) | [page-002.pdf](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol1_tamil_english/pages/page-002.pdf) | Government of Tamil Nadu / SCERT — First Edition 2026 |
| Term-I VOL-II Maths & EVS — Tamil (144 pages) | [page-002.pdf](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_tm/pages/page-002.pdf) | தமிழ்நாடு அரசு — முதல் பதிப்பு 2026 / SCERT 2026 |
| Term-I VOL-II Maths & EVS — English (144 pages) | [page-002.pdf](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_em/pages/page-002.pdf) | Government of Tamil Nadu — First Edition 2026 / SCERT 2026 |
| Term-II VOL-I Tamil & English (144 pages) | [page-002.pdf](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol1_tamil_english/pages/page-002.pdf) | தமிழ்நாடு அரசு — முதல் பதிப்பு 2026 / SCERT 2026 |
| Term-II VOL-II Maths & EVS — Tamil (120 pages) | [page-002.pdf](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_tm/pages/page-002.pdf) | தமிழ்நாடு அரசு — முதல் பதிப்பு 2026 / SCERT 2026 |
| Term-II VOL-II Maths & EVS — English (120 pages) | [page-002.pdf](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_em/pages/page-002.pdf) | Government of Tamil Nadu — First Edition 2026 / SCERT 2026 |

**Reprint history:** Each Page 2 states First Edition 2026. No separate later reprint/revised-edition line is shown on these six Page-2 pages. Academic year (2026–27) and printed edition (First Edition 2026) remain separate fields.

Each Page-2 PDF already existed in its book's `pages/` directory and was confirmed as a one-page PDF. No duplicate Page-2 PDF was created.

### TOC transcription and immutable evidence links

#### 1. Term-I VOL-I — Tamil & English

Tamil TOC — [PDF split page 10](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol1_tamil_english/pages/page-010.pdf)

- அலகு 1:
  - 1. மகிழ்வோடு விளையாடு — printed page 1
  - 2. கண்டுபிடி... கண்டுபிடி... — printed page 17
- அலகு 2:
  - 3. பாப்பாவோடு பாடலாம்! — printed page 54
  - 4. வந்த பாதை — printed page 82

English Contents — [PDF split page 98](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol1_tamil_english/pages/page-098.pdf)

- Unit 1 — About Me!
  - Hi! Hello! — 89
  - Simba and Chinnu — 100
  - Shake and Jump! — 109
  - Look at me! — 120
- Unit 2 — My Family
  - Anu’s Red Ribbon — 135
  - My Finger Family — 143
  - The Big Big Beetroot — 154

#### 2. Term-I VOL-II — Maths & EVS — Tamil

Mathematics TOC — [PDF split page 7](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_tm/pages/page-007.pdf)

- அலகு 1:
  - 1. பந்து எங்கே? — 1
  - 2. எனக்குப் பிடித்த பொருள்கள் — 8
  - 3. பொம்மைகள் எத்தனை? — 16
  - 4. விடுபட்டவை எவை? — 36
- அலகு 2:
  - 5. யாரிடம் அதிகம்? — 45
  - 6. மொத்த பலூன்கள் — 47
  - 7. என்னைச் சுற்றியுள்ள பொருள்கள் — 58
  - 8. மீதி பலூன்கள் — 65

Environmental Science TOC — [PDF split page 86](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_tm/pages/page-086.pdf) (printed page 79)

- அலகு 1 — என்னைப்பற்றி...
  - என் உலகம் — 80
  - என் நலம் — 88
- அலகு 2 — என்னைச் சுற்றி...
  - இயற்கையின் பரிசுகள் — 102
  - என்னைச் சுற்றியுள்ள விலங்குகள் — 116

#### 3. Term-I VOL-II — Maths & EVS — English

Mathematics Contents — [PDF split page 7](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_em/pages/page-007.pdf)

- Unit 1:
  - Where is the Ball? — 1
  - Things I Like — 8
  - How Many Toys? — 16
  - What are Missing? — 36
- Unit 2:
  - Who has More? — 45
  - Total Balloons — 47
  - Things Around Me — 58
  - Remaining Balloons — 65

Environmental Science Contents — [PDF split page 86](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term1/vol2_maths_evs_em/pages/page-086.pdf) (printed page 79)

- Unit 1 — About Me
  - My World — 80
  - My Health — 88
- Unit 2 — Around Me
  - Nature’s Gifts — 102
  - Animals Around Me — 116

#### 4. Term-II VOL-I — Tamil & English

Tamil பொருளடக்கம் — [PDF split page 10](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol1_tamil_english/pages/page-010.pdf)

- அலகு 1:
  - 1. ஐ... மகிழ்ச்சி! — 1
  - 2. கண்ணாமூச்சி — 7
- அலகு 2:
  - 3. கிளிங்... கிளிங்... — 28
  - 4. எதனால்? எதனால்? — 45

English Contents — [PDF split page 84](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol1_tamil_english/pages/page-084.pdf) (printed page 74)

- Unit 1 — My Classroom
  - My School Bag — 75
  - The Train Station — 80
  - Bits of Paper — 86
  - The Cat’s Hat — 99
- Unit 2 — Flowers and Insects
  - The Orange Flowers — 106
  - The Little Caterpillar — 112
  - A Pig in the Pit — 126

#### 5. Term-II VOL-II — Maths & EVS — Tamil

Mathematics பொருளடக்கம் — [PDF split page 6](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_tm/pages/page-006.pdf)

- அலகு I:
  - 1. தாகமுள்ள பறவைகள் — 1
  - 2. நிழல் விளையாட்டு — 25
  - 3. எங்களின் புதிய வளையல்கள் — 30
- அலகு II:
  - 4. பள்ளி செல்லும் வழியில் — 42
  - 5. என்னால் முடியும். உன்னால் முடியுமா? — 47
  - 6. பெட்டியில் உள்ள வளையல்கள் — 53

Environmental Science பொருளடக்கம் — [PDF split page 74](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_tm/pages/page-074.pdf) (printed page 68)

- அலகு 1 — நமது பசுமை நண்பர்கள் — 69
- அலகு 2 — ஜீனியின் தோட்டம் — 92

#### 6. Term-II VOL-II — Maths & EVS — English

Mathematics Contents — [PDF split page 6](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_em/pages/page-006.pdf)

- Unit I:
  - Thirsty Birds — 1
  - Shadow Game — 25
  - Our New Bangles — 30
- Unit II:
  - On the Way to School — 42
  - I Can. Can You? — 47
  - Bangles in the Box — 53

Environmental Science Contents — [PDF split page 74](https://github.com/Eaglesiva/tn-class-01/blob/838d5c2f335810ed95753327fe0a0b94ad298a63/official_editions/2026-27/term2/vol2_maths_evs_em/pages/page-074.pdf) (printed page 68)

- Unit 1 — Our Green Friends — 69
- Unit 2 — Genie’s Garden — 92

### Updated decision

- **Page-2 imprint:** confirmed as First Edition 2026 for all 6 books.
- **TOC pages:** identified and visually checked for the Tamil and English / Maths and EVS sections listed above.
- **Combined-volume subject map:** TOC start pages are now recorded; do not yet infer every subject's exact final page boundary or switch production viewer routes until the page sequence and section transitions are mapped and tested.
- **Git safety:** no main-branch textbook PDF/page assets, `pages.json`, viewer, quiz, or answer files were changed. No archive move, branch merge, or active-edition change was made.

This final extraction supersedes the earlier partial-TOC note in this report.


## Original official filenames and local split paths

| Book | Original official PDF filename | Existing split folder |
|---|---|---|
| Term-I VOL-I Tamil & English | `1st_Tamil & English Term 1_Text.pdf` | `official_editions/2026-27/term1/vol1_tamil_english/pages/` |
| Term-I VOL-II Maths & EVS — Tamil | `1st_Maths & EVS_TM_Term 1_Text.pdf` | `official_editions/2026-27/term1/vol2_maths_evs_tm/pages/` |
| Term-I VOL-II Maths & EVS — English | `1st_Maths & EVS_EM_Term 1_Text.pdf` | `official_editions/2026-27/term1/vol2_maths_evs_em/pages/` |
| Term-II VOL-I Tamil & English | `TAMIL & ENGLISH_1_II_VOL-I.pdf` | `official_editions/2026-27/term2/vol1_tamil_english/pages/` |
| Term-II VOL-II Maths & EVS — Tamil | `MATHS & EVS_1_II_VOL-II_TM.pdf` | `official_editions/2026-27/term2/vol2_maths_evs_tm/pages/` |
| Term-II VOL-II Maths & EVS — English | `MATHS & EVS_1_II_VOL-II_EM.pdf` | `official_editions/2026-27/term2/vol2_maths_evs_em/pages/` |

For all six folders, the existing one-page proof filename is `pages/page-002.pdf`. The complete split folders contain 176, 144, 144, 144, 120, and 120 pages respectively.
