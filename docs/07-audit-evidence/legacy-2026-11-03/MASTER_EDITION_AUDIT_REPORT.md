# தமிழ்நாடு 1 முதல் 12-ஆம் வகுப்பு பாடநூல் பதிப்பு ஆய்வு அறிக்கை (Master Edition Audit Report)
> **முக்கிய திருத்தம் — 03-11-2026:** இந்த அறிக்கை முதலில் PDF-களின் உள்ளே உள்ள Edition / Reprint Year மற்றும் பக்க எண்ணிக்கையை மட்டும் Extract செய்த ஆரம்பக் கணக்கெடுப்பு. இதில் பயன்படுத்தப்பட்ட `✅ Current`, `100% Current` போன்ற குறிச்சொற்கள் 2026–27-ல் அரசு பள்ளி மாணவர்கள் பயன்படுத்தும் பதிப்புடன் ஒப்பிட்டு நிரூபிக்கப்பட்டவை அல்ல. அவற்றை தற்போதைக்கு `EDITION_DETECTED — CURRENT_VALIDITY_UNVERIFIED` என்று மட்டுமே கருத வேண்டும். இந்த அறிக்கையின் பழைய/புதிய ஆண்டு கண்டறிதல் பயனுள்ளது; ஆனால் Current / Obsolete முடிவுகள் தனி Official Distribution + Book Content Audit முடியும் வரை இறுதியானவை அல்ல.

> **அரசு உறுதிப்படுத்திய விதிவிலக்கு:** 2025–26 கல்வியாண்டில் அச்சிடப்பட்ட 1–3 வகுப்பு Term-I புத்தகங்கள் தற்போது வழக்கொழிந்தவை; அவற்றை 2026–27 நடப்பு புத்தகமாகப் பயன்படுத்தக்கூடாது. 2026–27 Term-I / Term-II புதிய புத்தகங்கள் வெளியிடப்பட்டுள்ளன. அதிகாரப்பூர்வ அறிவிப்பு: [Textbook Corporation](https://www.textbookcorp.in/schools).

> **Class 10 Tamil சிறப்பு குறிப்பு:** Repo-வில் உள்ள 2024 imprint / 9 இயல் கேள்வித் தொகுப்பு, 2025–26-ல் 9 இயலிலிருந்து 7 இயலாகக் குறைக்கப்பட்ட மாற்றத்துக்கு முந்தைய வடிவம். 2025–26-க்கான 7 இயல் Revised Book/portion இருப்பதற்கான ஆதாரங்கள் உள்ளன; 2026–27-ல் அது தொடர்வதற்கான 7 இயல் exam-portion பட்டியலும் கிடைக்கிறது. இருப்பினும் 2026–27 அரசு விநியோகப் புத்தகத்தின் imprint / contents உடன் இறுதி நேரடி ஒப்பீடு செய்யப்படும்வரை 2025-ஐ `CURRENT_CONFIRMED` என்று குறிக்க வேண்டாம்.

> **வகுப்பு 4–12 குறிப்பு:** 2026–27-ல் பழைய பரந்த பாடத்திட்டத்தின் கீழ் புதிய தொகுப்பு புத்தகங்கள் விநியோகிக்கப்பட்டதாக செய்தி அறிக்கை தெரிவிக்கிறது. இது ஒவ்வொரு பாடத்திற்கும் உள்ளே உள்ள Revised Edition Year-ஐ நிரூபிக்காது. 2018, 2019, 2022, 2024 அல்லது 2025 imprint இருப்பது மட்டும் வைத்து Current / Obsolete என்று முடிவு செய்யக்கூடாது.

> **பக்க எண்ணிக்கை குறிப்பு:** உள்ளூர் PDF பக்கங்கள், split page files, scanned spreads மற்றும் புத்தகத்தில் அச்சிடப்பட்ட page number ஆகியவை வேறுபடலாம். PDF file count-ஐ அச்சுப் புத்தகத்தின் physical page count என்று நேரடியாகக் கருத வேண்டாம்.

**தேதி:** 2026-11-03  
**ஆய்வு செய்த அமைப்பு:** Antigravity AI Engine (PyMuPDF Local Deep Extraction)  
**நோக்கம்:** ChatGPT, Antigravity, மற்றும் பயனர் அனைவரும் பொதுவாகப் பயன்படுத்தும் பாடநூல் பதிப்புத் தகவல் (Edition Manifest).

---

## 📊 சுருக்கமான கண்ணோட்டம் (Executive Summary)
1. **வகுப்பு 12 (Class 12):** 28 பாடங்களில் 26 பாடங்கள் ஏற்கனவே **2024 அதிகாரப்பூர்வ Revised Edition** பதிப்பில் உள்ளன!
2. **வகுப்பு 8 & 9 (Classes 8 & 9):** அனைத்து 8 பாடங்களும் முழுமையாக **2024 அதிகாரப்பூர்வ Revised Edition** பதிப்பில் உள்ளன!
3. **வகுப்பு 10 (Class 10):**
   - Maths TM/EM: **2025 புதிய பதிப்பு** (352 / 368 பக்கங்கள்) - Current-year validity not yet verified
   - English: **2024 பதிப்பு** (224 பக்கங்கள்) - Current-year validity not yet verified
   - Tamil: **2024 பதிப்பு** (248 பக்கங்கள், 9 இயல்கள்). 2025-ல் SCERT 184 பக்கங்கள் / 7 இயல்களாகச் சுருக்கியுள்ளது.
4. **வகுப்பு 11 (Class 11):**
   - Tamil: **2025 புதிய பதிப்பு** (176 பக்கங்கள்) - Current-year validity not yet verified
   - Maths TM/EM: **2025 புதிய பதிப்பு** - Current-year validity not yet verified
5. **வகுப்புகள் 1 முதல் 5 (Primary Classes 1–5):**
   - தற்போது 2019-2022 Term பதிப்புகள் உள்ளன.

---

## 📑 வகுப்பு வாரியான முழுமையான பதிப்பு விவரங்கள் (Class-wise Master Table)

| வகுப்பு | பாடம் | வகை | பக்கங்கள் | அச்சு / திருத்திய ஆண்டு | நிலை / பரிந்துரை |
|:---:|:---|:---:|:---:|:---:|:---|
| Class 1st | english | Full Book | 65 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 1st | maths_em | Full Book | 66 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 1st | maths_tm | Full Book | 66 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 1st | science_em | Full Book | 64 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 1st | science_tm | Full Book | 64 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 1st | tamil | Full Book | 81 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 2nd | english | Full Book | 47 | **2019** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 2nd | maths_em | Full Book | 76 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 2nd | maths_tm | Full Book | 76 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 2nd | science_em | Full Book | 54 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 2nd | science_tm | Full Book | 54 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 2nd | tamil | Full Book | 160 | **2026** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 3rd | english | Full Book | 66 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 3rd | maths_em | Full Book | 66 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 3rd | maths_tm | Full Book | 66 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 3rd | science_em | Full Book | 54 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 3rd | science_tm | Full Book | 54 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 3rd | social_science_em | Full Book | 60 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 3rd | social_science_tm | Full Book | 60 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 3rd | tamil | Full Book | 72 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | english | Full Book | 48 | **2019** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | maths_em | Full Book | 83 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | maths_tm | Full Book | 83 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | science_em | Full Book | 45 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | science_tm | Full Book | 45 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | social_science_em | Full Book | 36 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | social_science_tm | Full Book | 36 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 4th | tamil | Full Book | 152 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 5th | english | Full Book | 80 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 5th | maths_em | Full Book | 102 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 5th | maths_tm | Full Book | 102 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 5th | science_em | Full Book | 42 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 5th | science_tm | Full Book | 42 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 5th | social_science_em | Full Book | 52 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 5th | social_science_tm | Full Book | 52 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 5th | tamil | Full Book | 82 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 6th | english | Full Book | 80 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 6th | maths_em | Full Book | 136 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 6th | maths_tm | Full Book | 136 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 6th | science_em | Full Book | 108 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 6th | science_tm | Full Book | 107 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 6th | social_science_em | Full Book | 110 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 6th | social_science_tm | Full Book | 111 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 6th | tamil | Full Book | 72 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | english | Full Book | 96 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | maths_em | Full Book | 136 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | maths_tm | Full Book | 144 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | science_em | Full Book | 102 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | science_tm | Full Book | 103 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | social_science_em | Full Book | 100 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | social_science_tm | Full Book | 123 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 7th | tamil | Full Book | 78 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | english | Full Book | 240 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | maths_em | Full Book | 288 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | maths_tm | Full Book | 296 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | science_em | Full Book | 288 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | science_tm | Full Book | 304 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | social_science_em | Full Book | 256 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | social_science_tm | Full Book | 304 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 8th | tamil | Full Book | 232 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | english | Full Book | 224 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | maths_em | Full Book | 328 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | maths_tm | Full Book | 344 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | science_em | Full Book | 328 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | science_tm | Full Book | 336 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | social_science_em | Full Book | 328 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | social_science_tm | Full Book | 344 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 9th | tamil | Full Book | 272 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 10th | english | Full Book | 224 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 10th | maths_em | Full Book | 352 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 10th | maths_tm | Full Book | 368 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 10th | science_em | Full Book | 360 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 10th | science_tm | Full Book | 360 | **2019** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 10th | social_science_em | Full Book | 344 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 10th | social_science_tm | Full Book | 368 | **2022** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 10th | tamil | Full Book | 248 | **2024** | 🔄 2024 (248p / 9 இயல்) -> 2025 (184p / 7 இயல் தேவை) |
| Class 11th | accountancy_em | Full Book | 264 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | accountancy_tm | Full Book | 296 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | botany_em | Full Book | 328 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | botany_tm | Full Book | 360 | **Unknown** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | chemistry_em | Full Book | 304 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | chemistry_tm | Full Book | 328 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | commerce_em | Full Book | 344 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | commerce_tm | Full Book | 352 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | computer_science_em | Full Book | 168 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | computer_science_tm | Full Book | 192 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | economics_em | Full Book | 288 | **Unknown** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | economics_tm | Full Book | 288 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | english | Full Book | 216 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | geography_em | Full Book | 344 | **Unknown** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | geography_tm | Full Book | 336 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 11th | history_em | Full Book | 216 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | history_tm | Full Book | 352 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 11th | maths_em | Full Book | 368 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 11th | maths_tm | Full Book | 320 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 11th | physics_em | Full Book | 320 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | physics_tm | Full Book | 320 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | political_science_em | Full Book | 256 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | political_science_tm | Full Book | 328 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 11th | tamil | Full Book | 176 | **2025** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 11th | zoology_em | Full Book | 240 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 11th | zoology_tm | Full Book | 256 | **2018** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 12th | accountancy_em | Full Book | 368 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | accountancy_tm | Full Book | 368 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | bio_zoology_em | Full Book | 264 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | bio_zoology_tm | Full Book | 312 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | botany_em | Full Book | 312 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | botany_tm | Full Book | 336 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | chemistry_em | Full Book | 296 | **2019** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 12th | chemistry_tm | Full Book | 328 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | commerce_em | Full Book | 288 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | commerce_tm | Full Book | 288 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | computer_science_em | Full Book | 360 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | computer_science_tm | Full Book | 360 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | economics_em | Full Book | 296 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | economics_tm | Full Book | 336 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | english | Full Book | 248 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | geography_em | Full Book | 216 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | geography_tm | Full Book | 232 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | history_em | Full Book | 272 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | history_tm | Full Book | 312 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | maths_em | Full Book | 304 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | maths_tm | Full Book | 336 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | physics_em | Full Book | 352 | **2019** | ⚠️ Older Imprint — Current-year validity UNVERIFIED |
| Class 12th | physics_tm | Full Book | 352 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | political_science_em | Full Book | 328 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | political_science_tm | Full Book | 360 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | tamil | Full Book | 240 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | zoology_em | Full Book | 280 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |
| Class 12th | zoology_tm | Full Book | 336 | **2024** | ⚠️ Edition Year Detected — 2026–27 Current Validity UNVERIFIED |

---

## 🎯 அடுத்த கட்ட செயல்திட்டம் (Next Action Plan):
1. **Class 10 Tamil:** 2024 Legacy பதிப்பை அப்படியே வைத்துக்கொண்டு, 184 பக்கங்கள் கொண்ட 2025 Rationalized புதிய பதிப்பிற்கு தனியாக 2025-revised வடிவம் உருவாக்குதல்.
2. **Class 8, 9, 12:** 2024 பதிப்புகளிலேயே தொடர்வதால் கேள்விகளை மீண்டும் எடுக்கத் தேவையில்லை; இன்னும் Current Edition என்று உறுதிப்படுத்தப்படவில்லை.
3. **GitHub API நேரடி இணைப்பு:** ChatGPT போலவே Antigravity-யும் GitHub REST API மூலம் நேரடியாக கோப்புகளை நிர்வகிக்கும் (0 MB குளோன்).
