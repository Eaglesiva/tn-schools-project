# SCERT Book Edition Verification — Common Rules (Classes 1–12)

> இந்த ஆவணம் Class 1–12 அனைத்திற்கும் பொதுவான Book Version Gate. ஒவ்வொரு Class / Subject / Medium / Term / Volume-க்கும் தனித்தனி முடிவுகளைப் பதிவு செய்ய வேண்டும்.

## 1. அடிப்படை விதிகள்

1. உண்மை ஆதாரமே முதன்மை; ஆதாரம் இல்லாததை `VERIFIED` என்று கூற வேண்டாம்.
2. Filename, file size, PDF page count, imprint year அல்லது ஒரு sample page மட்டும் வைத்து இரண்டு புத்தகங்களும் ஒரே edition என்று முடிவு செய்யக்கூடாது.
3. ஒவ்வொரு பாடத்திற்கும் Class + Subject + Medium + Term / Annual + Volume ஆகியவற்றைத் தனித்தனியாக அடையாளம் காணவும்.
4. அதிகாரப்பூர்வ SCERT / Textbook Corporation / Government distribution source-ஐ முதலில் பார்க்கவும்.
5. Third-party mirror கிடைத்தால் அதை `THIRD_PARTY_MIRROR` என்று குறிக்கவும்; Government-hosted source என்று கூறக்கூடாது.
6. ஏற்கெனவே உள்ள PDF / page files / questions / quiz-ஐ ஆதாரமின்றி overwrite, delete, rename அல்லது move செய்யக்கூடாது.

## 2. ஒவ்வொரு புத்தகத்திற்கும் சரிபார்க்க வேண்டியவை

- Class / Standard.
- Subject / exact textbook title.
- Tamil Medium / English Medium அல்லது பொருந்தும் பிற Medium.
- Term-based book ஆ, Annual / Full-year book ஆ; உண்மையான structure பார்த்தே முடிவு செய்யவும்.
- Volume number, if applicable.
- Official record / distribution listing / direct PDF URL.
- PDF opens, valid PDF bytes, file length, PDF page count.
- Cover, title page, copyright / imprint, First Edition / Revised Edition / Reprint / Correction year.
- Contents / TOC, chapter / lesson names and order.
- Book Back / Evaluation sections மற்றும் முக்கிய கேள்விப் பக்கங்கள்.
- Local PDF-ஐ official PDF-உடன் file-level comparison செய்ய முடிந்தால் SHA-256; ETag-ஐ தனியாக metadata-ஆகப் பதிவு செய்யவும்.

## 3. Match முடிவு எப்படி எடுக்க வேண்டும்?

| நிலை | பயன்படுத்த வேண்டிய பதிவு |
|---|---|
| முழு file SHA-256 match | `OFFICIAL_API_SHA256_MATCH` |
| வலுவான byte / MD5 / ETag match (முறை விளக்கத்துடன்) | `OFFICIAL_API_MD5_ETAG_MATCH` |
| அதிகாரப்பூர்வ PDF உள்ளது; local file வேறுபடுகிறது | `OFFICIAL_API_LISTED_LOCAL_MISMATCH` |
| அதிகாரப்பூர்வ PDF உள்ளது; local copy இல்லை | `OFFICIAL_API_LISTED_LOCAL_MISSING` |
| Local file தற்போதைய API-ல் தெரியவில்லை | `LOCAL_NOT_FOUND_IN_CURRENT_API` — review தேவை; உடனே obsolete என்று சொல்லக்கூடாது |
| Official listing உள்ளது; actual PDF திறக்க / match செய்ய முடியவில்லை | `OFFICIAL_LISTING_FOUND_PDF_UNVERIFIED` |
| Edition அல்லது school-use status உறுதியாகவில்லை | `CURRENT_VALIDITY_UNVERIFIED` |

Page count / imprint / filename மட்டும் பொருந்தினால் exact match status கொடுக்க வேண்டாம்.

### 3.1 ஒரே புத்தகத்தின் இரண்டு பிரதிகள் இருந்தால்

1. முதலில் இரண்டும் ஒரே Class + Subject + Medium + Term + Volume + exact title தானா என்று உறுதி செய்யவும்.
2. இரண்டின் PDF Page 2-ஐத் திறந்து First Edition / Revised Edition / Reprint / Correction imprint மற்றும் அச்சிடப்பட்ட ஆண்டை பதிவு செய்யவும். Page 2 என்பது edition அடையாளத்திற்கான ஆரம்ப ஆதாரம்; முழு புத்தக ஒற்றுமைக்கான தனி proof அல்ல.
3. Imprint / year வேறுபட்டால் official listing மற்றும் all-pages / content evidence மூலம் பழையது, புதியது என்று வகைப்படுத்தவும்.
4. Imprint / year ஒன்றாக இருந்தால் இரண்டையும் 100% identical என்று கருதக்கூடாது. முழு master SHA-256 அல்லது ஒவ்வொரு page-ன் Blob SHA / bytes-ஐ ஒப்பிட்டு, manifests, page order, TOC மற்றும் book-back பகுதிகளும் பொருந்துகிறதா என்று சரிபார்க்கவும்.
5. எல்லா உள்ளடக்கமும் 100% identical என்றால் ஒரே canonical latest/official copy மட்டும் Active-ல் வைத்திருக்கவும். இரண்டாவது duplicate-ஐ Archive-ல் வைக்கக்கூடாது. Register: IDENTICAL_DUPLICATE_NO_ARCHIVE; Archive Required: NO.
6. Same imprint/year இருந்தும் content mismatch இருந்தால் SAME_EDITION_CONTENT_MISMATCH_REVIEW. Manual review முடியும் வரை எந்த copy-யையும் அழிக்கவோ Archive-க்கு நகர்த்தவோ கூடாது.
7. ஒரே copy மட்டுமே இருந்தால் SINGLE_EDITION_ONLY என்று பதிவு செய்து official current status உறுதியானால் Active-ல் வைத்திருக்கவும். பழையது மட்டும் உள்ளது, புதிய term இன்னும் வெளியிடப்படவில்லை என்றால் legacy content-ஐ புதியதாகக் காட்டாமல் RELEASE_PENDING / Archive link policy-ஐப் பின்பற்றவும்.

## 4. மாற்று Edition கண்டறியப்பட்டால்

1. புதிய Edition உண்மையில் வேறுபடுகிறது என்பதை official record அல்லது school-issued book மூலம் உறுதிப்படுத்தவும்.
2. பழைய Edition-ஐ அழிக்க வேண்டாம்; existing files மற்றும் production path-ஐப் பாதுகாக்கவும்.
3. புதிய Edition-ஐ தனி branch / தனி version path-ல் வைத்துக் கொள்ளவும்.
4. Cover / TOC / page count / Book Back question changes-ஐப் பதிவு செய்யவும்.
5. `questions.md` மற்றும் Quiz-ஐ புதிய Edition என்று finalize செய்வதற்கு முன் page-level question check செய்யவும்.
6. Active edition மாற்றம், production routing மாற்றம், deploy போன்றவை தனி review / explicit approval-க்கு உட்பட்டவை.

## 5. Evidence மற்றும் Report

ஒவ்வொரு Edition decision-க்கும் `docs/`-ல் ஒரு class-specific audit note / manifest வைத்திருக்கலாம். அதில்:

- தேதி / UTC timestamp.
- அதிகாரப்பூர்வ source URL மற்றும் பார்த்த API / listing record.
- local path மற்றும் file identity.
- PDF page count, imprint / revision தகவல்.
- SHA-256 / file size / ETag கிடைத்தால், ஒவ்வொன்றின் பொருளைத் தெளிவுபடுத்தி.
- TOC / lesson structure match.
- Book Back question page match.
- முடிவு, நம்பகத்தன்மை, கிடைக்காத ஆதாரம் / blocker.

ஒரு வகுப்பில் செய்யப்பட்ட exact match-ஐ மற்ற வகுப்புகளுக்கும் தானாகப் பொருத்தக்கூடாது. ஒவ்வொரு புத்தகமும் தனியாக verify செய்யப்பட வேண்டும்.

## 6. Workflow-உடன் இணைப்பு

Edition Gate என்பது Book Back / Quiz Workflow-க்கு முன் செய்ய வேண்டிய புத்தக அடையாளச் சரிபார்ப்பு. Edition உறுதியாகிய பிறகு, `BOOK_BACK_QUIZ_WORKFLOW_TA.md`-ல் உள்ள ஒரே பொதுவான Answer / Quiz நடைமுறையைப் பின்பற்றவும்.

**இந்த ஆவணம் Class 10 அல்லது வேறு ஒரு வகுப்பின் பழைய audit முடிவுகளைப் பொதுவான உண்மையாகக் கருதாது. Evidence ஒவ்வொரு repository / subject-க்கும் தனியாக இருக்க வேண்டும்.**