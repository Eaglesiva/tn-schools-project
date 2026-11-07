# வகுப்பு 03: காட்சி ஆய்வு, பொருளடக்க எல்லைகள் & பயனர் இடைமுக முன்சரிபார்ப்பு அறிக்கை
*(Class 03 Visual Review, TOC Lesson Boundaries & UI Precheck Audit Report)*

**வெளியீட்டுத் தேதி:** 2026-11-08  
**திட்டம்:** தமிழ்நாடு அரசுப் பள்ளிக் கல்வித்துறை — SCERT 2026-27 பாடநூல்கள் பிரித்தெடுப்பு மற்றும் களஞ்சியப் புனரமைப்பு  
**மைய ஆவணப் பதிவேடு:** [`Eaglesiva/tn-schools-project`](https://github.com/Eaglesiva/tn-schools-project)  
**இலக்கு செயலில் உள்ள களஞ்சியம் (Active Repo):** [`Eaglesiva/tn-class-03`](https://github.com/Eaglesiva/tn-class-03)  
**இலக்குக் காப்பகக் களஞ்சியம் (Archive Repo):** [`Eaglesiva/tn-class-03-archive`](https://github.com/Eaglesiva/tn-class-03-archive)  

---

## 1. தணிக்கை மற்றும் களஞ்சியக் கிளைகளின் நிலை (Repository & Branch Status)

| களஞ்சியம் | கிளை (Branch) | தற்போதைய Commit SHA | நிலை | குறிப்பு |
|---|---|---|:---:|---|
| **tn-class-03** | `main` | [`a7206fe321a8c93463056a65fbc73f8a5cee907a`](https://github.com/Eaglesiva/tn-class-03/commit/a7206fe321a8c93463056a65fbc73f8a5cee907a) | **மாற்றமில்லை (LOCKED)** | பிரதான கிளை பாதுகாக்கப்பட்டுள்ளது. 1,473 பழைய கோப்புகள் உள்ளன. |
| **tn-class-03** | `precheck/class-03-viewer-and-index` | [`b1bf4ab6bd6fa763a806154c256018436f00b3d6`](https://github.com/Eaglesiva/tn-class-03/commit/b1bf4ab6bd6fa763a806154c256018436f00b3d6) | **புதுப்பிக்கப்பட்டது** | Main-ஐ விட 3 commits முன்னால், 0 பின்னால். `index.html` & `viewer.html` மட்டும் மாற்றப்பட்டுள்ளது. பருவம் 3 பழைய பாடநூல்கள் அணுகல் சேர்க்கப்பட்டுள்ளது. |
| **tn-class-03** | `scert/class-03/audit-2026-27` | [`c6b5dffadfc066e76aff58c7e18afaf019ee3995`](https://github.com/Eaglesiva/tn-class-03/commit/c6b5dffadfc066e76aff58c7e18afaf019ee3995) | **மூலத் தணிக்கைக் கிளை** | 1,046 புதிய 2026 கோப்புகள் (`official_editions/2026-27/`) உள்ளன. பருவம் 1-க்கான இயந்திரம் படிக்கக்கூடிய `toc.json` ஒத்திசைக்கப்பட்டது. |
| **tn-class-03-archive** | `main` | [`babaf6b590ab0918ed668f2904007e124ec4343b`](https://github.com/Eaglesiva/tn-class-03-archive/commit/babaf6b590ab0918ed668f2904007e124ec4343b) | **மாற்றமில்லை (LOCKED)** | ஆரம்ப நிலை (README மட்டும்). Step 6 பயனர் அனுமதி இன்றி தொடங்கப்படாது. |

---

## 2. வகுப்பு 03 — 6 அதிகாரப்பூர்வப் பாடநூல்கள் விவரப் பட்டியல் (Complete Book Inventory)

வகுப்பு 03 பாடநூல்கள் SCERT-ஆல் **ஒருங்கிணைந்த தொகுதிகளாக (Combined Volumes)** வெளியிடப்பட்டுள்ளன.

| # | பருவம் & தொகுதி | கோப்புறைப் பாதை | பக்கங்கள் | பயிற்றுமொழி | அதிகாரப்பூர்வ SHA-256 | அதிகாரப்பூர்வ MD5 |
|---|---|---|:---:|:---:|:---:|:---:|
| 1 | **பருவம் 1 — தொகுதி 1** | `term1/vol1_tamil_english` | 168 | தமிழ் / English | `187b179a18fac459d91fc9e4843bc7be68d8c7344d510b7a822ebc014ebb7101` | `a92ca41140bfce6c6ebad1580fb5e26d` |
| 2 | **பருவம் 1 — தொகுதி 2 (TM)** | `term1/vol2_maths_sci_soc_tm` | 184 | தமிழ் வழி (TM) | `5c04f3a6f609cbfedfc6ac9a97422d4c143533feada7e7f0db4df5215fed18f3` | `fa8e5e1879676e1ac7347111f36dcbfa` |
| 3 | **பருவம் 1 — தொகுதி 2 (EM)** | `term1/vol2_maths_sci_soc_em` | 184 | English Medium (EM) | `5efce3bc9b6c00d43f0fcfeee5218d867c29571f54cfc01d9f0fc88ec7b9e0f6` | `485ea49bf2f0ae27e7f09848529f518e` |
| 4 | **பருவம் 2 — தொகுதி 1** | `term2/vol1_tamil_english` | 144 | தமிழ் / English | `0d8b746816ec54a7c13da3ef14e1fa0a6045d6143c7b2a61362cb24fb3c8965a` | `fdb0c9e6ca3a0ecb791443d5c5f2120e` |
| 5 | **பருவம் 2 — தொகுதி 2 (TM)** | `term2/vol2_maths_sci_soc_tm` | 168 | தமிழ் வழி (TM) | `5d288d67a1491cf15fd6cb9c35472aa5c02b370607185fc5f2061266d13cb2d2` | `1c89fca6cb94ef202111bbdb77c667ce` |
| 6 | **பருவம் 2 — தொகுதி 2 (EM)** | `term2/vol2_maths_sci_soc_em` | 168 | English Medium (EM) | `39f7df8cf88fec933b9c02ff4b4458f237f3747ebff62cb9634e320d866a87c1` | `5c84dfc1d81cb21183141249b6b90fd7` |

---

## 3. அச்சு முத்திரை மற்றும் காட்சி ஆய்வுச் சான்றுகள் (Page 2 Imprint & Visual Review Evidence)

### பருவம் 1 (Term 1) — Text-Extracted Imprints
1. **Vol 1 (Tamil & English):**
   - **பக்கம் 2 அச்சு முத்திரை:** `மாநிலக் கல்வியியல் ஆராய்ச்சி மற்றும் பயிற்சி நிறுவனம் © SCERT 2026 உருவாக்கமும் தொகுப்பும்`
   - **பதிப்பு:** முதல் பதிப்பு 2026 (First Edition 2026).
   - **நிலைக் குறியீடு:** `DIFFERENT / DIFFERENT` (CONFIRMED).
2. **Vol 2 TM (Maths, Science, Social):**
   - **பக்கம் 2 அச்சு முத்திரை:** `தமிழ்நாடு அரசு முதல் பதிப்பு - 2026`
   - **நிலைக் குறியீடு:** `DIFFERENT / DIFFERENT` (CONFIRMED).
3. **Vol 2 EM (Maths, Science, Social):**
   - **பக்கம் 2 அச்சு முத்திரை:** `Tamil Nadu Textbook and Educational Services Corporation / SCERT First Edition 2026`
   - **நிலைக் குறியீடு:** `DIFFERENT / DIFFERENT` (CONFIRMED).

### பருவம் 2 (Term 2) — Raster Image Imprints
- பருவம் 2-ன் 3 தொகுதிகளும் (`vol1_tamil_english`, `vol2_maths_sci_soc_tm`, `vol2_maths_sci_soc_em`) பக்கம் 2-ல் ராஸ்டர் பட வடிவிலான அச்சு முத்திரையைக் கொண்டுள்ளன.
- இவை தன்னிச்சையாக அனுமானிக்கப்படாமல் `VISUAL_REVIEW_PENDING` என்ற பாதுகாப்பு நிலையிலேயே வைக்கப்பட்டுள்ளன.

---

## 4. பாடப் பிரிவுகள் மற்றும் பொருளடக்க எல்லைகள் (TOC & Lesson Boundaries)

தணிக்கைக் கிளையில் (`scert/class-03/audit-2026-27`) உள்ள `toc.json` கோப்புகள் துல்லியமாகப் புதுப்பிக்கப்பட்டுள்ளன:

### 4.1. பருவம் 1 — தொகுதி 1 (Tamil & English)
- **பொருளடக்கம் (TOC):** பக்கம் 4 (தமிழ்) & பக்கம் 74 (ஆங்கிலம்).
- **பிரிவு 1 (தமிழ்):** பக்கங்கள் 1 முதல் 72 வரை (பாடங்கள் 1 முதல் 6).
- **பிரிவு 2 (ஆங்கிலம்):** பக்கங்கள் 73 முதல் 168 வரை (Units 1, 2, 3).

### 4.2. பருவம் 1 — தொகுதி 2 TM & EM (Maths, Science, Social Science)
- **பிரிவு 1 (கணக்கு / Mathematics):** பக்கங்கள் 1 முதல் 62 வரை (அலகுகள் 1 முதல் 5).
- **பிரிவு 2 (அறிவியல் / Science):** பக்கங்கள் 63 முதல் 122 வரை (அலகுகள் 1 முதல் 4).
- **பிரிவு 3 (சமூக அறிவியல் / Social Science):** பக்கங்கள் 123 முதல் 184 வரை (அலகுகள் 1 முதல் 4).

### 4.3. பருவம் 2 (Term 2)
- பருவம் 2 தொகுதிகளுக்கான TOC ஆய்வு `MANUAL_REVIEW_REQUIRED` என்ற பாதுகாப்பு நிலையில் வைக்கப்பட்டு `toc.json`-ல் பதிவு செய்யப்பட்டுள்ளது.

---

## 5. பருவம் 3 பழைய பாடநூல்கள் தக்கவைப்பு & அணுகல் (Term 3 Legacy Book Retention)

- SCERT 2026 பருவம் 3 பாடநூல்கள் இன்னும் வெளியிடப்படவில்லை (Upstream CDN returns **HTTP 403 Forbidden**).
- எனவே, **நடப்பு `main`-ல் உள்ள 8 பருவம் 3 பழைய பாடநூல்கள் (மொத்தம் 503 கோப்புகள்: 452 Single-page PDFs, 8 `pages.json`, 43 `questions.md`) கண்டிப்பாக Active களஞ்சியத்தில் (`Eaglesiva/tn-class-03`) தக்கவைக்கப்பட வேண்டும்.**
- **Portal UI Integration:** `index.html`-ல் 8 பழைய பருவம் 3 பாடநூல்களுக்கும் தனிப்பட்ட அட்டைப் பிரிவுகள் (Book Cards) சேர்க்கப்பட்டுள்ளன.
  1. வகுப்பு 3 — தமிழ் (பருவம் 3) -> `./tamil/term3/00_prelims/page_02.pdf`
  2. Class 3 — English (Term 3) -> `./english/term3/00_prelims/page_02.pdf`
  3. வகுப்பு 3 — கணக்கு (பருவம் 3 - TM) -> `./maths_tm/term3/00_prelims/page_02.pdf`
  4. Class 3 — Mathematics (Term 3 - EM) -> `./maths_em/term3/00_prelims/page_02.pdf`
  5. வகுப்பு 3 — அறிவியல் (பருவம் 3 - TM) -> `./science_tm/term3/00_prelims/page_02.pdf`
  6. Class 3 — Science (Term 3 - EM) -> `./science_em/term3/00_prelims/page_02.pdf`
  7. வகுப்பு 3 — சமூக அறிவியல் (பருவம் 3 - TM) -> `./social_science_tm/term3/00_prelims/page_02.pdf`
  8. Class 3 — Social Science (Term 3 - EM) -> `./social_science_em/term3/00_prelims/page_02.pdf`
- **Viewer Engine Integration:** `viewer.html`-ல் `bookTitleMap`-ல் 8 பழைய பாடநூல்களுக்கும் தலைப்புகள் சேர்க்கப்பட்டுள்ளன; `./<subject>/term3/pages.json` தானாகக் கண்டறியப்பட்டு அடுத்தடுத்த பக்கங்கள் இயங்குகின்றன.
- **Footer Notice:** Footer வாசகம் திருத்தப்பட்டு, "பழைய 2018–2022 பாடநூல்களின் பருவம் 1 & 2 காப்பகப் பரிமாற்றத்திற்குத் திட்டமிடப்பட்டுள்ளன; புதிய 2026 பதிப்பு வெளியாகும் வரை பருவம் 3 பாடநூல்கள் இத்தளத்திலேயே தொடர்ந்து செயல்பாட்டில் இருக்கும்" என துல்லியமாக மாற்றப்பட்டுள்ளது.

---

## 6. தற்போதைய கோப்பு எண்ணிக்கை மற்றும் நல்லிணக்கம் (File Count Reconciliation)

`tn-class-03/main` (`a7206fe3...`) கிளையில் உள்ள மொத்த 1,473 கோப்புகளின் சரிபார்க்கப்பட்ட முழுமையான விவரம்:

| பிரிவு | Single-page PDFs | `pages.json` | `questions.md` | மொத்தக் கோப்புகள் | நிலை |
|---|:---:|:---:|:---:|:---:|---|
| **பருவம் 1 (Term 1)** | 498 | 8 | 48 | **554** | எதிர்கால காப்பகப் பரிமாற்றத்திற்குத் தகுதியானது |
| **பருவம் 2 (Term 2)** | 349 | 8 | 40 | **397** | எதிர்கால காப்பகப் பரிமாற்றத்திற்குத் தகுதியானது |
| **பருவம் 1 & 2 கூட்டுத்தொகை** | **847** | **16** | **88** | **951** | **திட்டமிடப்பட்ட எதிர்காலக் காப்பகப் பேலோடு** |
| **பருவம் 3 (Term 3)** | 452 | 8 | 43 | **503** | **Active-ல் தக்கவைக்கப்பட வேண்டியவை (தவிர்க்க முடியாதவை)** |
| **Subject Root Questions** | 0 | 0 | 8 | **8** | பாட வாரியான பொது கேள்விக் கோப்புகள் |
| **மொத்த பழைய பாடநூல் கோப்புகள்** | **1,299** | **24** | **139** | **1,462** | **முழுமையான பழைய பாடப்பிரிவு உள்ளடக்கம்** |
| **களஞ்சியக் கட்டமைப்பு (Infrastructure)** | — | — | — | **11** | `README`, `docs/`, `index.html`, `viewer.html`, `pdfjs` |
| **மொத்த Blobs (`main`)** | — | — | — | **1,473** | **100% துல்லியமாக உறுதிசெய்யப்பட்டது** |

*(குறிப்பு: முந்தைய வரைவு அட்டவணையின் கூட்டுத்தொகையில் இருந்த தட்டச்சுப் பிழை [456/330/412] சரிசெய்யப்பட்டு, துல்லியமான எண்ணிக்கையான [498/349/452] என சீர்செய்யப்பட்டுள்ளது).*

---

## 7. பயனர் இடைமுகப் பாதை தணிக்கை (UI Route Audit Analysis)

### 7.1. Planned Destination Mapping: PASS (42 / 42)
- `index.html`-ல் உள்ள 42 தனித்துவமான 2026 PDF இலக்குகளும் (`./books/2026-27/...`), தணிக்கைக் கிளையில் (`scert/class-03/audit-2026-27`) உள்ள `official_editions/2026-27/...` பாதைகளுடன் **100% துல்லியமாகப் பொருந்துகின்றன (42/42 PASS)**.

### 7.2. Precheck Branch Local Tree Presence: DEFERRED (0 / 42)
- `precheck/class-03-viewer-and-index` கிளை தற்போதைய `main`-லிருந்து (`a7206fe3...`) உருவாக்கப்பட்டதால், அதன் Tree-ல் பழைய 1,473 கோப்புகள் மட்டுமே உள்ளன; `books/2026-27/` கோப்புகள் Step 6 Active Upgrade வரை ஏற்றப்படாது. எனவே இது **Live PDF Routing PASS அல்ல; Planned Destination Mapping PASS** என வகைப்படுத்தப்பட்டுள்ளது.

### 7.3. Legacy Term 3 Active Book Routes: PASS (8 / 8)
- `index.html`-ல் இணைக்கப்பட்டுள்ள 8 பருவம் 3 பாடநூல்களின் தொடக்க PDF கோப்புகளும் (`./<subject>/term3/00_prelims/page_02.pdf`) நடப்பு `main` கிளையில் **100% உண்மையாக உள்ளன (8/8 PASS)**.

---

## 8. Viewer திருத்தச் சான்றுகள் (Viewer Fix Evidence)

[`precheck/class-03-viewer-and-index`](https://github.com/Eaglesiva/tn-class-03/blob/precheck/class-03-viewer-and-index/viewer.html)-ல் commit [`b1bf4ab6bd6fa763a806154c256018436f00b3d6`](https://github.com/Eaglesiva/tn-class-03/commit/b1bf4ab6bd6fa763a806154c256018436f00b3d6) மூலம் Class 03-க்குரிய புதிய தலைப்புகள் மற்றும் பருவம் 3 பழைய தலைப்புகள் சேர்க்கப்பட்டுள்ளன:

```javascript
    const bookTitleMap = {
      'term1/vol1_tamil_english': 'வகுப்பு 3 — பருவம் 1: தொகுதி 1 (தமிழ் & ஆங்கிலம்)',
      'term1/vol2_maths_sci_soc_tm': 'வகுப்பு 3 — பருவம் 1: தொகுதி 2 (கணக்கு, அறிவியல் & சமூக அறிவியல் - தமிழ் வழி)',
      'term1/vol2_maths_sci_soc_em': 'Class 3 — Term 1: Volume 2 (Mathematics, Science & Social Science - English Medium)',
      'term2/vol1_tamil_english': 'வகுப்பு 3 — பருவம் 2: தொகுதி 1 (தமிழ் & ஆங்கிலம்)',
      'term2/vol2_maths_sci_soc_tm': 'வகுப்பு 3 — பருவம் 2: தொகுதி 2 (கணக்கு, அறிவியல் & சமூக அறிவியல் - தமிழ் வழி)',
      'term2/vol2_maths_sci_soc_em': 'Class 3 — Term 2: Volume 2 (Mathematics, Science & Social Science - English Medium)',
      'tamil/term3': 'வகுப்பு 3 — தமிழ் (பருவம் 3 - பழைய பதிப்பு)',
      'english/term3': 'Class 3 — English (Term 3 - Legacy Edition)',
      'maths_tm/term3': 'வகுப்பு 3 — கணக்கு (பருவம் 3 - தமிழ் வழி - பழைய பதிப்பு)',
      'maths_em/term3': 'Class 3 — Mathematics (Term 3 - English Medium - Legacy Edition)',
      'science_tm/term3': 'வகுப்பு 3 — அறிவியல் (பருவம் 3 - தமிழ் வழி - பழைய பதிப்பு)',
      'science_em/term3': 'Class 3 — Science (Term 3 - English Medium - Legacy Edition)',
      'social_tm/term3': 'வகுப்பு 3 — சமூக அறிவியல் (பருவம் 3 - தமிழ் வழி - பழைய பதிப்பு)',
      'social_em/term3': 'Class 3 — Social Science (Term 3 - English Medium - Legacy Edition)'
    };
```

---

## 9. மூலத் தரவு முரண்பாடு (Source Metadata Conflict Status)

- **முரண்பாடு:** EMIS API Record ID 22-ல் `TAMIL & ENGLISH_3_II_VOL-I.pdf` கோப்பிற்கு தலைப்பு `VOL-I (MATHS, SCIENCE & SOCIAL)` எனக் குறிப்பிடப்பட்டுள்ளது.
- **ஆய்வு நிலை:** அசல் கோப்பு அட்டை மற்றும் TOC ஆகியவை தமிழ் & ஆங்கிலம் என்பதை உறுதிப்படுத்தினாலும், அதிகாரப்பூர்வ EMIS பதிவேட்டின் ஒருமைப்பாட்டைப் பேணும் வகையில் இக்குறிப்பு **`SOURCE_METADATA_CONFLICT` (PENDING_CONFIRMATION)** என்ற தணிக்கை நிலையிலேயே பராமரிக்கப்படுகிறது.

---

## 10. கட்டுப்பாடுகள் மற்றும் தற்போதைய நிலை (Gate Controls & Current Status)

1. **Step 6 (Archive Transfer / Active Upgrade):** **தற்காலிக நிறுத்திவைப்பு (ON HOLD).** பயனரின் வெளிப்படையான எழுத்துப்பூர்வ அனுமதி இன்றி Step 6 தொடங்கப்படாது.
2. **Main Branch Protection:** `Eaglesiva/tn-class-03/main` (`a7206fe3...`) மற்றும் `Eaglesiva/tn-class-03-archive/main` (`babaf6b5...`) எந்த மாற்றமும் இன்றிப் பூட்டப்பட்டுள்ளன (LOCKED).
3. **Master Index Safeguard:** `MASTER_CROSS_VERIFICATION_INDEX.md`-ல் `ARCHIVE_APPROVED` குறிச்சொல் சேர்க்கப்படவில்லை.
4. **Zero Local Storage:** உள்ளூர் கணினியில் எந்த PDF கோப்பும் பதிவிறக்கப்படவில்லை; Git Clone செய்யப்படவில்லை.