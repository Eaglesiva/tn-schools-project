# SCERT பதிப்பு சரிபார்ப்பு மற்றும் GitHub Migration — பொதுவான செயல்முறை வழிகாட்டி

**ஆவண வகை:** கட்டாய Common Workflow Blueprint  
**பொருந்தும் வகுப்புகள்:** Class 01 முதல் Class 12 வரை  
**மைய Repository:** Eaglesiva/tn-schools-project  
**முக்கிய நோக்கம்:** பழைய பதிப்பு, புதிய பதிப்பு, Questions, Answers, Quiz மற்றும் அவற்றின் ஆதார இணைப்புகள் ஒன்றோடொன்று குழப்பமடையாமல் பிரித்து பராமரித்தல்.  
**செயல்பாட்டு விதி:** GitHub-to-GitHub; பயனரின் Local Computer-ல் Clone / Download / Extract செய்யக்கூடாது.  
**Pilot Reference:** Class 01 — 2026-11-07 அன்று Main-ல் Merge செய்யப்பட்ட வேலை.

> **இந்த ஆவணம் Class 01–12 Edition Migration-க்கான ஒரே பொதுவான Execution Workflow ஆகும்.** புதிய Chat, புதிய Agent அல்லது வேறு Operator வந்தாலும், முதலில் இந்த ஆவணத்தை முழுமையாகப் படித்துவிட்டுத்தான் பணியைத் தொடங்க வேண்டும்.

---

## 1. இந்த Workflow ஏன் தேவை?

Class 01 Pilot-ல் பல பயனுள்ள விஷயங்கள் உறுதி செய்யப்பட்டன. அதே சமயம் நேரம், Token, Local Disk Space வீணாகும் செயல்முறைகளும், இறுதியில் Link Correction தேவைப்பட்ட பிழைகளும் கண்டறியப்பட்டன.

இந்த Workflow-ன் நோக்கம்:

1. பழைய புத்தகமும் புதிய புத்தகமும் ஒரே Active Folder-ல் கலந்திருக்காமல் பிரித்தல்.
2. பழைய புத்தகத்திற்குரிய Questions / Answers / Quiz பழைய Edition-உடனேயே Archive-ல் பாதுகாக்கப்படுதல்.
3. புதிய புத்தகத்திற்குரிய Questions / Answers / Quiz புதிய Edition-உடனேயே Active Repository-ல் இருப்பதை உறுதிப்படுத்துதல்.
4. ஒவ்வொரு புத்தகத்திற்கும் Official PDF, Page 2 Imprint, GitHub PDF, GitHub Page 2, பழைய Folder மற்றும் புதிய Folder ஆகியவற்றுக்கான சரியான இணைப்புகளைப் பதிவு செய்தல்.
5. GitHub-ல் உள்ள கோப்புகளை மீண்டும் Local-க்கு Download செய்யாமல், GitHub API மூலம் நேரடியாகப் படித்து மாற்றுதல்.
6. ஒவ்வொரு வகுப்பையும் தனித்தனியாகச் சரிபார்த்து முடித்த பிறகே அடுத்த வகுப்புக்குச் செல்லுதல்.
7. இறுதியில் Cross-Verification, Main Merge மற்றும் Register Update முடிந்த பிறகே COMPLETE என்று அறிவித்தல்.

**இந்த ஆவணம் Edition Migration-க்கானது.** Book-back Questions / Answers / Quiz உருவாக்கும் தனி Step 1–3 பணிகளுக்கு, பொதுவான Book Back Quiz Workflow-ஐயும் கட்டாயம் பின்பற்ற வேண்டும். Edition Migration-ன் போது Quiz உள்ளடக்கத்தைத் தேவையின்றி மீண்டும் உருவாக்கக்கூடாது.

---

## 2. மாறாத அடிப்படை விதிகள் (Non-Negotiable Rules)

### 2.1 Local Clone / Download முற்றிலும் தடை

பயனரின் கணினியில் கீழ்கண்ட செயல்கள் செய்யக்கூடாது:

- **git clone**
- **git fetch / git pull**
- **git sparse-checkout**
- Repository ZIP / TAR Download
- முழு Repository அல்லது பெரிய Folder-களை Local-ல் சேமித்தல்
- PDF-களை Local-ல் Download செய்து பிரித்தல் / Extract செய்தல்
- Migration-க்காக C: Drive-ல் Temporary Workspace உருவாக்குதல்
- ஏற்கெனவே Local-ல் உள்ளதாக நினைத்து புதிய நகல் உருவாக்குதல்

**பயனரின் Local Computer இந்த Project-ன் Intermediate Storage அல்ல.**

### 2.2 GitHub-only செயல்பாடு

முதன்மையாகப் பயன்படுத்த வேண்டியவை:

- GitHub REST API
- GitHub Git Database API (Trees / Blobs / Commits / References)
- GitHub Contents API (சிறிய Text / JSON / Markdown கோப்புகள்)
- GitHub Pull Request / Merge API
- GitHub Actions போன்ற GitHub-hosted Cloud Runner — API மட்டும் போதாத, உண்மையான Processing தேவைப்படும் Exceptional Case-ல் மட்டும்; பயனரின் கணினியைத் தொடக்கூடாது. தேவையானால் அந்த Cloud Processing-க்கு முன் பயனரின் அனுமதி பெற வேண்டும்.

API Limit, Binary Size Limit அல்லது Permission பிரச்சினை ஏற்பட்டால் **Local Clone-க்கு மாறக்கூடாது**. BLOCKED_API_LIMIT / BLOCKED_PERMISSION என்று பதிவு செய்து, காரணத்தையும் மாற்று Cloud வழியையும் தெரிவிக்க வேண்டும்.

### 2.3 Main Branch பாதுகாப்பு

- முதலில் Main-ஐப் படிக்கவும்; Main-ல் நேரடியாக மாற்றம் செய்யக்கூடாது.
- தற்போதைய Main SHA-ஐ பதிவு செய்யவும்.
- தனியான Migration Branch உருவாக்கவும்.
- பழைய Branch பெயர் ஏற்கெனவே இருந்தால் அதன் உள்ளடக்கத்தைப் பார்க்காமல் மீண்டும் பயன்படுத்தக்கூடாது.
- Force Push, blind overwrite, bulk delete, unreviewed mass commit தடை.
- பயனர் வெளிப்படையாக ஒப்புதல் அளிக்கும் வரை Main Merge செய்யக்கூடாது.

### 2.4 ஆதாரம் இல்லாமல் முடிவு இல்லை

- Filename, Folder Name, File Size அல்லது Page Count மட்டும் வைத்து Edition முடிவு செய்யக்கூடாது.
- Page 2 Imprint முக்கிய ஆதாரம்; ஆனால் Page 2 மட்டும் முழு புத்தக ஒற்றுமையை நிரூபிக்காது.
- அரசு வெளியீட்டு Listing, Official CDN URL, Page Count, TOC, உள்ளடக்க வரிசை, Lesson Boundaries, Book-back பகுதிகள் ஆகியவற்றைச் சரிபார்க்கவும்.
- தெளிவில்லாததை PENDING / UNVERIFIED என்று வைத்திருக்கவும்.
- ஆதாரம் இல்லாமல் VERIFIED, MIGRATED, 100% COMPLETE என்று அறிவிக்கக்கூடாது.

### 2.5 பழைய மற்றும் புதிய கல்வி உள்ளடக்கம் கலக்கக்கூடாது

- பழைய Edition-க்குரிய Questions / Answers / Quiz பழைய Edition-உடன் Archive-க்கு செல்ல வேண்டும்.
- புதிய Edition-க்குரிய Questions / Answers / Quiz புதிய Edition-உடன் Active Repository-ல் இருக்க வேண்டும்.
- பழைய Questions-ஐ புதிய Edition-ல் தானாகப் பயன்படுத்தக்கூடாது.
- உள்ளடக்கம் புதிய புத்தகத்துடன் பொருந்துகிறது என்று தனியாகச் சரிபார்க்காமல் பழைய Answer / Quiz-ஐ புதிய புத்தகத்திற்கு மாற்றக்கூடாது.
- File பெயரை மட்டும் வைத்து Question எந்த Edition-க்கு உரியது என்று தீர்மானிக்கக்கூடாது.

---

### 2.6 Production Viewer & UI Routing கட்டாய விதி (Zero-Broken-Links Gate)

- **Git Blob SHA Match மட்டும் ஒரு Migration-ஐ COMPLETE ஆக்காது.** PDF கோப்புகள் சரியாக இருந்தும் இணையதளத்தில் (index.html / viewer.html) அவற்றைத் திறக்க முடியவில்லை என்றால் அது தோல்வியடைந்த மைக்ரேஷன் ஆகும்.
- `index.html`, `viewer.html`, `pages.json`, `toc.json` மற்றும் நேரடி PDF இணைப்புகள் அனைத்தும் **Production Routing Test**-ல் 100% PASS ஆக வேண்டும்.
- புதிய கோப்பகப் பாதைகளையும் (`books/2026-27/...`), புதிய கோப்புப் பெயரிடும் முறையையும் (`page-001.pdf`) Viewer ஆதரிப்பது கட்டாயம்.
- பழைய நீக்கப்பட்ட பாதைகள் (`./tamil/`, `./english/`, `./maths_tm/` போன்றவை) எங்கும் சுட்டப்படக்கூடாது. Default PDF ஒருபோதும் நீக்கப்பட்ட பாதையைக் கொண்டிருக்கக்கூடாது.
- **எந்தவொரு முக்கிய UI Link-ம் 404 கொடுத்தால் Step 8 Main Merge-க்கு அனுமதி கிடையாது.**

## 3. Repository பொறுப்புகள்

| Repository | பயன்பாடு |
|---|---|
| tn-schools-project | Common Blueprint, Workflow, Master Register, Cross-Class Index, Audit Evidence |
| tn-class-XX | அந்த வகுப்பின் தற்போதைய அங்கீகரிக்கப்பட்ட புத்தகங்கள், அதற்குரிய Questions / Answers / Quiz மற்றும் Production Assets |
| tn-class-XX-archive | அந்த வகுப்பின் பழைய / Superseded Editions மற்றும் அவற்றுடன் தொடர்புடைய வரலாற்று Questions / Answers / Quiz |

வகுப்பு Repository-யில் உள்ள Folder பெயர்கள் அனைத்தும் ஒரே மாதிரி என்று கருதக்கூடாது. ஒவ்வொரு வகுப்பின் உண்மையான Git Tree-ஐப் பார்த்து அந்த Repository-யின் naming convention-ஐப் பின்பற்ற வேண்டும்.

---

## 4. கட்டாய செயல்முறை — Step 0 முதல் Step 10 வரை

### STEP 0 — தொடங்குவதற்கு முன் பாதுகாப்பு ஆய்வு (Pre-Work Gate)

முதலில் செய்ய வேண்டியது:

1. அந்த வகுப்பின் Active Repository மற்றும் Archive Repository-யை அடையாளம் காண்க.
2. இரு Repository-களின் Default Branch மற்றும் தற்போதைய Main Commit SHA-ஐப் பெறுக.
3. GitHub Permissions / Read / Write அணுகல் உள்ளதா என்று உறுதிப்படுத்துக.
4. Common Repository-யில் உள்ள இந்த Workflow, Edition Rules, Page 2 Gate, Archive Policy ஆகியவற்றைப் படிக்கவும்.
5. அந்த வகுப்பில் ஏற்கெனவே உள்ள Audit Branch, Edition Branch, Migration Branch, பழைய Register மற்றும் Evidence-களைப் பட்டியலிடவும்.
6. ஏற்கெனவே உள்ள புத்தகம் அல்லது Audit Evidence-ஐ மீண்டும் உருவாக்க வேண்டிய அவசியமுண்டா என்று பாருங்கள்.

**இந்த Step முடிவில் கிடைக்க வேண்டியது:** Repository Map, Main SHA, Branch List, Existing Evidence List.

**செய்யக்கூடாதவை:** Clone தொடங்குதல், PDF Download, Folder Move, Main-ல் மாற்றம்.

### STEP 1 — முழுமையான Book Inventory

ஒரு வகுப்பின் Active Repository main-ஐ முதலில் Recursive Git Tree மூலம் முழுமையாகப் பார்த்து, **எத்தனை உண்மையான புத்தகங்கள் / Volume-கள் உள்ளன** என்பதை முதலில் கணக்கிடவும். ஒவ்வொரு புத்தகத்தையும் தனித்தனி Book Record-ஆகப் பதிவு செய்யவும். ஒரே புத்தகத்தின் duplicate folders / versions இருந்தால் அவற்றையும் தனித்தனி candidate-ஆகப் பதிவு செய்யவும்; எண்ணிக்கையை ஊகிக்கக்கூடாது.

**முக்கிய வரிசை:** முதலில் புத்தகத்தைக் கண்டறி → புத்தகத்தின் இரண்டாம் பக்கத்தை (page_02.pdf, page-002.pdf அல்லது manifest-ல் குறிப்பிடப்பட்ட சரியான Page 2) திறந்து imprint-ஐப் பார் → Edition-ஐ வகைப்படுத்து → அந்த புத்தகத்துக்குரிய support files-ஐ map செய் → அதன் பிறகே migration. Book split முடிவதற்கு முன் unrelated code / quiz / correction வேலையில் மாறக்கூடாது.

கட்டாய அடையாள விவரங்கள்:

- Class / Standard
- Subject / Exact Book Title
- Medium (Tamil / English / பிற)
- Term / Annual
- Volume
- Academic Year
- Official Edition / Printed Imprint
- Official CDN URL
- Official PDF Page Count
- தற்போதைய GitHub Repository / Branch / Folder
- தற்போதைய PDF / Page Manifest
- Questions / Answers / Quiz / JSON / Index கோப்புகள்

ஒரே Combined Volume-ல் இரண்டு பாடங்கள் இருந்தால், புத்தகத்தின் உண்மையான அமைப்பு மற்றும் பக்க எல்லைகளைப் பார்த்தே Mapping செய்ய வேண்டும். பெயரின் அடிப்படையில் பிரிக்கக்கூடாது.

**முடிவு:** அந்த வகுப்பில் உள்ள அனைத்து புத்தகங்களின் Inventory தயாராக வேண்டும். API-ல் கிடைத்த ஒவ்வொரு Record-க்கும் Status இருக்க வேண்டும்; எந்த Record-யும் அமைதியாக விடுபடக்கூடாது.

### STEP 2 — Official Edition Verification

ஒவ்வொரு Book Record-க்கும்:

1. அரசு / SCERT Official Listing-ல் அந்த புத்தகம் உள்ளதா என்று உறுதிப்படுத்தவும்.
2. Official CDN PDF URL-ஐ அப்படியே பதிவு செய்யவும்.
3. URL, Title, Class, Subject, Medium, Term, Volume ஆகியவை ஒன்றுக்கொன்று பொருந்துகிறதா என்று பார்க்கவும்.
4. Official PDF Page Count பதிவு செய்யவும்.
5. PDF-ன் Page 2-ல் அச்சிடப்பட்டுள்ள Imprint-ஐ அப்படியே பதிவு செய்யவும்.
6. First Edition / Revised Edition / Reprint / Correction போன்ற சொற்களைத் தெளிவாக வேறுபடுத்தவும்.
7. Page 2-க்கான Direct View Link உருவாக்கவும்: Official PDF URL + #page=2.
8. TOC, பாட / இயல் வரிசை, Book-back / Evaluation பகுதிகள் ஆகியவற்றை ஒப்பிடவும்.
9. பழைய மற்றும் புதிய பதிப்பில் உள்ள முக்கிய உள்ளடக்க வேறுபாடுகளை ஆதாரத்துடன் குறிப்பிடவும்.

**முக்கியம்:** Academic Year மற்றும் Printed Edition Year இரண்டும் வேறு தகவல்கள். 2026–27 Academic Year என்று இருப்பதாலேயே First Edition 2026 என்று முடிவு செய்யக்கூடாது.

PDF-ஐ Browser / Remote Viewer மூலம் நேரடியாகத் திறந்து பார்க்கவும். API மூலம் வேண்டிய ஆதாரம் கிடைக்கவில்லை என்றால், Local-ல் Download செய்யாமல் UNVERIFIED என்று பதிவு செய்யவும். தேவையான Cloud Processing-க்கு முன் அனுமதி பெறவும்.

**முடிவு Status:** PAGE2_VERIFIED, OFFICIAL_SOURCE_VERIFIED, IMPRINT_UNCLEAR, SOURCE_UNAVAILABLE, PENDING_FULL_CONTENT_CHECK போன்ற தெளிவான நிலைகளைப் பயன்படுத்தவும்.

#### STEP 2-A — இரண்டு புத்தகங்கள் இருந்தால் Old / New / Identical முடிவு

ஒவ்வொரு ஒரே Class + Subject + Medium + Term + Volume புத்தகத்திற்கும் Main-ல் உள்ள candidate-களை Page 2 imprint மூலம் முதலில் ஒப்பிடவும்:

1. Page 2-ல் உள்ள First Edition / Revised Edition / Reprint / Correction மற்றும் அச்சிடப்பட்ட ஆண்டை அப்படியே பதிவு செய்யவும். Academic Year-ஐ Printed Edition Year என்று தவறாகக் கருதக்கூடாது.
2. இரண்டு candidate-களின் Page 2 வேறு edition / year என்பதை காட்டினால், அதிகாரப்பூர்வ listing மற்றும் book identity மூலம் எது புதியது, எது பழையது என்பதை உறுதி செய்யவும்.
3. இரண்டும் ஒரே புத்தகம், ஒரே edition / year என்று தெரிந்தால் உடனே Archive செய்யக்கூடாது. முழு PDF அல்லது எல்லா page-level Blob SHA-களையும் ஒப்பிட்டு **100% identical** என்பதை உறுதிப்படுத்தவும்; page count, TOC, lesson order, book-back பகுதிகளையும் cross-check செய்யவும்.
4. 100% identical duplicate என்றால் சமீபத்திய / அதிகாரப்பூர்வமாகத் தேர்ந்தெடுக்கப்பட்ட ஒரு canonical copy-ஐ Active-ல் வைத்துக் கொள்ளவும். தேவையற்ற duplicate path-ஐ Archive-க்கு அனுப்ப வேண்டாம்; அது user-approved Migration Branch-ல் மட்டும் நீக்கப்படலாம். Register-ல் IDENTICAL_DUPLICATE_NO_ARCHIVE என்று பதிவு செய்து “பழைய edition தனியாக இல்லை; identical duplicate மட்டும் இருந்தது” என்று குறிப்பிடவும்.
5. Same imprint/year இருந்தும் ஏதேனும் page/content வேறுபாடு இருந்தால் SAME_EDITION_CONTENT_MISMATCH_REVIEW என்று நிறுத்தவும். வேறுபாட்டை ஆய்வு செய்யாமல் old/new என்று தானாகப் பிரிக்கவோ duplicate என்று நீக்கவோ கூடாது.
6. ஒரே புத்தகம் மட்டுமே இருந்தால் official source + Page 2 மூலம் அதன் நிலையைத் தீர்மானிக்கவும். Current edition என்று உறுதியானால் Active-ல் வைத்திருக்கவும். ஒரே பழைய edition மட்டுமே இருந்து புதிய edition இன்னும் வெளியிடப்படவில்லை என்றால் அதை புதியதாகக் காட்டக்கூடாது; தேவையானால் Archive-ல் வைத்துப் Active-ல் RELEASE_PENDING / Archive link மட்டும் காட்டவும்.

**கட்டாய Decision Labels:** NEW_EDITION, LEGACY_EDITION, IDENTICAL_DUPLICATE_NO_ARCHIVE, SINGLE_CURRENT_EDITION, LEGACY_ONLY_RELEASE_PENDING, SAME_EDITION_CONTENT_MISMATCH_REVIEW, EDITION_UNVERIFIED.

### STEP 3 — பழைய / புதிய உள்ளடக்க Mapping

GitHub Main Tree மற்றும் பொருத்தமான Audit / Edition Branch Tree-ஐப் பெற்று ஒப்பிடவும்.

ஒவ்வொரு புத்தகத்திற்கும்:

- Old Edition Current Path
- Old Edition Destination Archive Path
- New Edition Source Path
- New Edition Destination Active Path
- PDF / Page Files
- pages.json / edition.json / toc.json / Manifest
- questions.md
- answers.md
- quiz.md
- quiz.json
- Master Quiz / Index / Routing தொடர்புகள்

ஒவ்வொரு Question / Answer / Quiz கோப்பும் எந்த Edition-ஐ அடிப்படையாகக் கொண்டு உருவாக்கப்பட்டது என்பதைச் சரிபார்க்க வேண்டும்.

**Book Package Rule:** ஒரு புத்தகத்துடன் நேரடியாகச் சேர்ந்துள்ள அனைத்து PDF page files, pages.json, toc.json, edition metadata, manifests, questions.md, answers.md, quiz.md, quiz.json, source references மற்றும் அதன் index/mapping கோப்புகளையும் ஒரே Book Package-ஆகக் கருதவும். Folder-க்கு தொடர்பில்லாத root-level / subject-level question files-ஐ உள்ளடக்க ஆதாரத்தின் அடிப்படையில் அந்தந்த புத்தகத்துடன் map செய்யவும். உறுதி இல்லாததை UNMAPPED_SUPPORT_FILE என்று பதிவு செய்து, தவறான edition-க்கு நகர்த்த வேண்டாம்.

**முக்கியம்:** பழைய புத்தகம் Archive-க்கு நகரும்போது அதற்குரிய முழு support package-மும் அதனுடன் செல்ல வேண்டும். PDF-ஐ மட்டும் நகர்த்தி அதனுடன் தொடர்புடைய questions / manifests-ஐ விட்டுவிடக்கூடாது.

**இந்த Step-ல் செய்யக்கூடாதவை:**
- Questions-ஐ புதிய புத்தகத்தில் தானாக copy செய்தல்.
- Answers-ஐ புதிய Edition-க்கு தானாகப் பயன்படுத்துதல்.
- Quiz-ஐ மீண்டும் Generate செய்தல்.
- Source Mapping தெரியாத கோப்புகளை அழித்தல்.
- பழைய கோப்பை புதிய கோப்பால் Overwrite செய்தல்.

### STEP 4 — Rough Master Register உருவாக்குதல்

முதலில் Draft மட்டும் உருவாக்கவும். எந்த Migration-மும் இன்னும் செய்யக்கூடாது.

ஒவ்வொரு புத்தகத்திற்கும் கீழ்கண்ட Column-கள் இருக்க வேண்டும்:

| Column | விவரம் |
|---|---|
| Book ID | தனிப்பட்ட நிலையான அடையாளம் |
| Class / Term / Subject / Medium / Volume | புத்தக அடையாளம் |
| Academic Year | கல்வியாண்டு |
| Official CDN PDF | அரசு PDF Link |
| Official Page 2 Link | CDN Link + #page=2 |
| Official Page 2 Imprint | அசல் Imprint Text |
| Official Page Count | அரசு PDF பக்க எண்ணிக்கை |
| Old Edition Imprint | பழைய பதிப்பு ஆதாரம் |
| Old Current Repository / Branch / Path | பழைய தற்போதைய இருப்பிடம் |
| Old Page 2 Link | பழைய புத்தகத்தின் உண்மையான பக்கம் 2 |
| Old Archive Destination | Archive-ல் செல்ல வேண்டிய Path |
| New Edition Imprint | புதிய பதிப்பு ஆதாரம் |
| New Current Repository / Branch / Path | புதிய பதிப்பின் தற்போதைய இருப்பிடம் |
| New Page 2 Link | புதிய புத்தகத்தின் உண்மையான பக்கம் 2 |
| New Active Destination | Active-ல் செல்ல வேண்டிய Path |
| Questions / Answers / Quiz Paths | Edition-க்கு உரிய உள்ளடக்கப் பாதைகள் |
| Verification Status | Verified / Pending / Blocked |
| Migration Status | Planned / Approved / Migrated / Merged |
| Final Links | உண்மையில் Merge ஆன பிறகு பயன்படுத்த வேண்டிய Links |
| Commit SHA | செயல்பாட்டு ஆதாரம் |
| Notes / Next Action | தீர்க்கப்படாத பிரச்சினைகள் |

**Current Path, Planned Destination Path, Final Path ஆகிய மூன்றையும் ஒரே Column-ல் கலக்கக்கூடாது.** Migration முடியும் முன் Planned Path-ஐ Live Link என்று காட்டக்கூடாது.

கூடுதல் கட்டாய Register fields: Book Count / Candidate Count, Page 2 Imprint, Edition Decision, Full Content Identity Result, Canonical Active Copy, Archive Required (YES/NO), Package File Count, Batch Checkpoint, Last Verified Batch Commit, Unmapped Support Files. IDENTICAL_DUPLICATE_NO_ARCHIVE என்றால் Archive Destination காலியாகவே இருக்க வேண்டும்; காரணம் Notes-ல் குறிப்பிடப்பட வேண்டும்.

### STEP 5 — Migration Plan மற்றும் ARCHIVE_APPROVED Gate

Draft Register முடிந்த பிறகு:

1. **ARCHIVE_POLICY கட்டுப்பாடு:** Master Cross-Verification Index-ல் குறிப்பிட்ட வகுப்பிற்கு வெளிப்படையான `ARCHIVE_APPROVED` முடிவு பதிவு செய்யப்படாமல் பழைய புத்தகங்களை Archive செய்யத் தொடங்கக்கூடாது.
2. **Viewer / UI Routing முன்கூட்டிய சோதனை:** புதிய கோப்பமைப்பு மற்றும் கோப்புப் பெயரமைப்பை `viewer.html` மற்றும் `index.html` ஆதரிப்பது உறுதி செய்யப்பட வேண்டும்.
3. **கோப்புப் பிரிப்புத் திட்டம்:**
   - பழைய Edition எந்த Archive Folder-க்கு (`legacy-2018-2022/...`) செல்ல வேண்டும் என்று பட்டியலிடவும்.
   - புதிய Edition எந்த Active Folder-ல் (`books/2026-27/...`) இருக்க வேண்டும் என்று பட்டியலிடவும்.
   - பழைய Questions / Answers / Quiz-க்கான Archive Mapping தரவும் (பழைய கேள்விகள் Archive-க்கு மட்டுமே செல்ல வேண்டும்).
   - மாற்றப்பட வேண்டிய பழைய பாடநூல் கோப்புகள் (Archive Payload) மற்றும் மாற்றப்படக்கூடாத Infrastructure கோப்புகள் (HTML, JS, Docs, CSV) இரண்டையும் தனித்தனியாகப் பட்டியலிடவும்.
4. **பயனர் ஒப்புதல்:** Draft Register, Payload எண்ணிக்கை, ஒவ்வொரு புத்தகத்தின் Old / New / Identical முடிவு, support-file mapping மற்றும் batch திட்டத்தைப் பயனரிடம் சமர்ப்பித்து நேரடி ஒப்புதல் பெற வேண்டும்.
5. **Book-first execution gate:** புத்தகத்தின் edition முடிவும் முழு package mapping-மும் முடியும் முன் TOC/Viewer redesign, question correction, answer writing, quiz regeneration அல்லது unrelated cleanup தொடங்கக்கூடாது. முதலில் தேவையான புத்தகங்கள் சரியான Active / Archive இடத்திற்குச் செல்ல வேண்டும்; அதன் பிறகே தனியாக அனுமதிக்கப்பட்ட corrections செய்யலாம்.

**பயனரின் தெளிவான எழுத்துப்பூர்வ ஒப்புதல் கிடைக்கும் வரை எந்த File Move, Delete, Overwrite, Transfer அல்லது Branch Merge-மும் செய்யக்கூடாது.**

### STEP 6 — GitHub-only Migration Execution

#### A. ஒரே Repository-க்குள் Folder மாற்றம்

முதன்மையாக GitHub Git Database API பயன்படுத்தவும்:

1. தற்போதைய Branch Commit மற்றும் Tree SHA-ஐப் பெறுக.
2. தேவையான கோப்புகளின் தற்போதைய Path மற்றும் Blob SHA-ஐப் பெறுக.
3. புதிய Path-ல் அதே Blob SHA-ஐப் பயன்படுத்தி புதிய Tree Entry உருவாக்குக.
4. பழைய Path-ஐ Migration Branch Tree-ல் மட்டும் நீக்குக.
5. ஒரே Batch Tree / Commit உருவாக்குக.
6. புதிய Branch Reference-ஐ Expected SHA உடன் புதுப்பிக்கவும்.

இதனால் PDF Content-ஐ மீண்டும் Download / Upload செய்ய வேண்டியதில்லை. அதே Repository-க்குள் Path மட்டும் மாறுகிறது.

#### B. Cross-Repository Book Package Transfer — Book-first, resumable batches

**ஒரே பெரிய upload / tree / commit ஆக முழு class-ஐ நகர்த்தக்கூடாது.** ஒரே Chat / Session-ல் தொடர்ச்சியாகப் பணியைச் செய்யலாம்; ஆனால் commit / recovery unit என்பது ஒரு புத்தகம் மற்றும் அதன் support package.

1. **ஒரு புத்தகத்தைத் தேர்வு செய்:** STEP 1–4-ல் உறுதி செய்யப்பட்ட Book ID-ஐ மட்டும் எடுத்துக் கொள்ளவும். அந்த புத்தகத்தின் source paths, destination paths, file count மற்றும் source Blob SHA-களை immutable manifest-ல் பதிவு செய்யவும்.
2. **Book Package-ஐ முழுமையாகப் பட்டியலிடு:** PDFs / page files, pages.json, toc.json, edition metadata, questions, answers, quiz, source references, relevant index mapping ஆகியவற்றை ஒரே package manifest-ல் சேர்க்கவும். புத்தகத்துக்கு தொடர்பில்லாத files-ஐ சேர்க்கக்கூடாது.
3. **Batch அளவு:** ஒரு நேரத்தில் ஒரு புத்தகத்தின் package மட்டுமே செயல்படுத்தவும். ஒரு package 200–300 files-ஐத் தாண்டினால், அதே புத்தகத்தை தொடர்ச்சியான page-range / file-range sub-batches-ஆகப் பிரிக்கவும். ஒவ்வொரு batch-லும் அதிகபட்சம் 200–300 file operations மட்டும். இரண்டு சிறிய புத்தகங்களை ஒரே commit-ல் சேர்க்க வேண்டுமானால் அவற்றின் மொத்தமும் 300 files-க்கு உட்பட்டிருக்க வேண்டும்; இல்லையெனில் தனித்தனி commit. அடுத்த புத்தகத்துக்கு மாறுவதற்கு முன் தற்போதைய புத்தகத்தின் அனைத்து batches-மும் PASS ஆக வேண்டும்.
4. **Idempotent destination check:** ஒவ்வொரு batch தொடங்கும் முன் Archive branch tree-ல் destination paths உள்ளனவா என்று பார்க்கவும். Path + Blob SHA இரண்டும் source-க்கு சமமாக இருந்தால் ALREADY_VERIFIED என்று குறித்துத் upload-ஐத் தவிர்க்கவும். Path இல்லை என்றால் மட்டும் upload செய்யவும். Path ஏற்கெனவே இருந்தும் SHA வேறுபட்டால் overwrite செய்யாமல் DESTINATION_CONFLICT என்று நிறுத்தி ஆய்வு செய்யவும்.
5. **Controlled Blob transfer:** Cross-repo file-களுக்குத் தேவையான Blob மட்டும் GitHub API மூலம் in-memory/base64 முறையில் உருவாக்கவும். குறைந்த concurrency (பரிந்துரை 2–4 requests) பயன்படுத்தவும்; uncontrolled parallel uploads / rapid polling கூடாது. ஒரே repository-க்குள் path மட்டும் மாறினால் existing Blob SHA-ஐ மறுபயன்படுத்தவும்.
6. **ஒவ்வொரு batch-க்கும் Commit:** அந்த batch-ன் Tree-ஐ மட்டும் உருவாக்கி, batch commit செய்யவும். Commit SHA, source SHA, destination SHA, source path, destination path, batch range மற்றும் count ஆகியவற்றை migration-checkpoint manifest-ல் உடனடியாகப் பதிவு செய்யவும். முழு 1,000+ file class payload-ஐ ஒரே Tree / Commit request-ல் உருவாக்கக்கூடாது.
7. **Batch-level verification:** Commit ஆன உடனே destination tree-ல் batch-ன் ஒவ்வொரு path-யும் இருக்கிறதா, source/destination Git Blob SHA match ஆகிறதா, Missing = 0 / Mismatch = 0 / unexpected extra = 0 தானா என்று சரிபார்க்கவும். Batch PASS ஆன பிறகே அடுத்த batch-ஐத் தொடங்கவும். Book package முழுமை அடைந்ததும் BOOK_PACKAGE_COMPLETE என்று checkpoint செய்யவும்.
8. **Retry / Back-off:** 403 / 429 அல்லது secondary rate limit வந்தால் Retry-After / reset தகவலை மதித்து காத்திருந்து மீண்டும் முயற்சிக்கவும். Exponential back-off + jitter பயன்படுத்தவும். 422 வந்தால் அதே பெரிய Tree-ஐ மீண்டும் மீண்டும் அனுப்பக்கூடாது; invalid path / entry / missing object / tree payload காரணத்தைத் தனியாகக் கண்டறிந்து, தேவையானால் batch-ஐச் சிறிதாக்கி மீண்டும் முயற்சிக்கவும். நிரூபிக்கப்படாத காரணத்தை rate limit என்று கூறக்கூடாது.
9. **Checkpoint & Resume:** ஒவ்வொரு வெற்றிகரமான blob மற்றும் ஒவ்வொரு batch commit-க்குப் பிறகும் checkpoint update செய்யவும். Connection interruption / process stop / API failure ஏற்பட்டால் முதல் batch-இலிருந்து restart செய்யக்கூடாது. தற்போதைய destination tree-ஐ checkpoint-உடன் ஒப்பிட்டு ஏற்கெனவே SHA-match ஆன கோப்புகளைத் தவிர்த்து, missing / failed file-களை மட்டும் மீண்டும் முயற்சிக்கவும். ஒரே file-ஐ வெற்றிக்குப் பிறகும் மீண்டும் upload செய்ய வேண்டாம்.
10. **Current book recovery gate:** ஒரு batch தோல்வியடைந்தால் அந்தப் புத்தகத்தின் வேலை PAUSED_RECOVERABLE ஆக checkpoint செய்யப்பட வேண்டும். அதே புத்தகத்தை முதலில் மீட்டெடுத்து முழுமைப்படுத்தவும்; வேறு புத்தகத்துக்கு அல்லது unrelated task-க்கு மாறி source/destination mapping-ஐக் குழப்பக்கூடாது.
11. **Source deletion gate:** Archive-ல் அந்தப் புத்தகத்தின் முழு package-மும் 100% SHA-verified ஆகவும், book-level file count / dependencies சரியாகவும் இருக்க வேண்டும். பயனர் ஒப்புதல் கிடைத்த பிறகே Active Migration Branch-ல் பழைய package paths-ஐ நீக்கலாம். Active main-ஐ நேரடியாக மாற்றக்கூடாது. Infrastructure கோப்புகளை நீக்கக்கூடாது.
12. **Two-step merge:** Archive Main-ல் merge செய்து Main Tree-ஐ மீண்டும் verify செய்த பிறகே Active Migration Branch-ஐ Active Main-ல் merge செய்ய வேண்டும்; இரண்டிற்கும் user approval அவசியம்.

#### C. New Edition Promotion

- ஏற்கெனவே GitHub-ல் சரிபார்க்கப்பட்ட புதிய PDF / Page Files இருந்தால் அவற்றின் Blob-களை மறுபயன்படுத்தவும்.
- தேவையில்லாமல் PDF-ஐ மீண்டும் Split செய்யக்கூடாது.
- Page 2 Link மட்டும் தேவையென்றால் முழு PDF URL + #page=2 பயன்படுத்தவும்.
- தனிப்பக்க PDF-கள் தற்போதைய Viewer / Application-க்கு உண்மையாகத் தேவைப்பட்டால் மட்டுமே உருவாக்கவும்.
- பழைய கேள்விகளை புதிய புத்தகத்திற்காக மாற்றவோ மறுபெயரிடவோ கூடாது.

### STEP 7 — Migration முடிந்த பின் தொழில்நுட்ப Audit

Archive Branch மற்றும் Active Branch ஆகியவற்றைத் தனித்தனியாகச் சரிபார்க்கவும்.

**Archive சோதனைகள்:**
- எதிர்பார்க்கப்பட்ட எல்லா Legacy Files உள்ளனவா?
- PDF / Markdown / JSON எண்ணிக்கை சரியா?
- Questions / Answers / Quiz கோப்புகள் பழைய புத்தகத்துடன் உள்ளனவா?
- Source-ல் இருந்த கோப்புகள் அனைத்தும் Destination-ல் உள்ளனவா?
- ஒரே Repository-க்கு இடையிலான Copy-யில் Blob SHA பொருந்துகிறதா?
- Missing / Extra / Mismatch எண்ணிக்கை என்ன?

**Active சோதனைகள்:**
- புதிய Edition Files சரியான Folder-ல் உள்ளனவா?
- பழைய Edition Path-கள் தவறுதலாக மீதமுள்ளனவா?
- புதிய Questions / Answers / Quiz சரியான Edition-க்குரியவையா?
- pages.json குறிப்பிடும் ஒவ்வொரு File-மும் உள்ளதா?
- Page Sequence-ல் Gap / Duplicate உள்ளதா?
- Viewer / Index / Route பயன்படுத்தும் Path-கள் சரியா?
- தேவையான PDF Page 2 உண்மையாகத் திறக்கிறதா?

**Checksum பற்றிய துல்லியமான மொழி:**
- Git Blob SHA ஒன்றாக இருந்தால் GIT_BLOB_SHA_MATCH என்று குறிப்பிடவும்.
- SHA-256 உண்மையாக கணக்கிட்டு ஒப்பிட்டிருந்தால் மட்டுமே SHA256_MATCH என்று குறிப்பிடவும்.
- File Size / Page Count சமம் என்பதைக் Checksum Match என்று கூறக்கூடாது.
- Audit-ல் பயன்படுத்திய Algorithm-ஐத் தெளிவாக எழுதவும்.


#### D. Production UI & Viewer Routing Audit (கட்டாய Gate)
1. **index.html Link Audit:** இணையதள முகப்பில் உள்ள அனைத்து `href` இணைப்புகளும் புதிய `books/2026-27/...` பாதைகளைச் சுட்டுகின்றனவா, அவற்றில் 404 கொடுக்கும் பழைய பாதைகள் ஏதேனும் உள்ளனவா என்று சோதிக்க வேண்டும்.
2. **viewer.html Compatibility Audit:**
   - Default PDF சரியான 2026 புத்தகத்தின் முதல் பக்கத்தைக் காட்டுகிறதா?
   - `pages.json` சரியாகத் தானாகவே கண்டறியப்பட்டு (auto-detect) பக்க வரிசை இயங்குகிறதா?
   - `page-001.pdf` போன்ற 3-இலக்க பெயர்களை regex சரியாக ஏற்கிறதா?
   - முந்தைய / அடுத்த பக்கம் (Previous / Next) மற்றும் விசைப்பலகை அம்புக்குறிகள் (Arrow keys) சரியாக இயங்குகின்றனவா?
   - அனைத்துப் புதிய புத்தகங்களிலும் பக்கம் 1, பக்கம் 2 (Imprint), கடைசிப் பக்கம் ஆகியவை திறக்கின்றனவா என்று சரிபார்க்கப்பட வேண்டும்.
3. UI Audit 100% வெற்றி பெற்றதாக அறிக்கை சமர்ப்பிக்கப்படாமல் Step 8-க்குச் செல்லக்கூடாது.

### STEP 8 — பயனர் Approval மற்றும் Main Merge

Main Merge-க்கு முன்:

1. Archive Migration Branch-ன் முழு Audit Report தயார்.
2. Archive Tree-ல் Missing = 0, Mismatch = 0 என்பதை உறுதிப்படுத்தல்.
3. பயனர் ஒப்புதல்.
4. முதலில் Archive Branch-ஐ Archive Main-ல் PR / GitHub Merge API மூலம் Merge செய்தல்.
5. Archive Main Tree-ஐ மீண்டும் Verify செய்தல்.
6. Archive Main பாதுகாப்பானது உறுதி ஆன பிறகு Active Migration Branch-ஐ Active Main-ல் Merge செய்தல்.
7. Active Main Tree-ஐ மீண்டும் Verify செய்தல்.
8. எந்த Merge-மும் Main Branch-ல் பிரதிபலிக்காத வரை MERGED என்று கூறக்கூடாது.

Merge Commit SHA, Parent Commit SHA, Branch Name, Date, Merge Result ஆகியவற்றைச் சேமிக்கவும்.

### STEP 9 — Central Register மற்றும் Documentation ஒத்திசைவு (Post-Merge Sync)

Main Merge முடிந்தவுடன் கீழ்கண்ட அனைத்து ஆவணங்களும் **ஒரே நேரத்தில் புதுப்பிக்கப்பட்டு உறுதிப்படுத்தப்பட வேண்டும்:**
1. **Active Repo README (`tn-class-XX/README.md`):** பழைய பக்க எண்ணிக்கையை நீக்கி, 2026 First Edition புதிய புத்தகங்கள், பக்கங்கள் (824 verified pages போன்றவை) மற்றும் JSON மேனிஃபெஸ்ட்டுகளைப் பதிவு செய்ய வேண்டும்.
2. **Archive Repo README (`tn-class-XX-archive/README.md`):** Pending தகவல்களை நீக்கி, Archive Main Merge Commit SHA மற்றும் பழைய கோப்புகளின் எண்ணிக்கையை (1,176 / 1,189) உறுதி செய்ய வேண்டும்.
3. **Central Final Register (`tn-schools-project/.../edition-verification-register.md`):** Final Register-ஐ வெளியிட வேண்டும்.
4. **Central Migration Audit Report (`.../edition-migration-audit-report.md`):** Main Merge Commit SHA-கள் (`bcf8c73`, `8c0f739` போன்றவை) மற்றும் Main Blob எண்ணிக்கையைச் சேர்க்க வேண்டும்.
5. **Master Cross-Verification Index (`MASTER_CROSS_VERIFICATION_INDEX.md`):** வகுப்புப் பதிவேட்டின் இணைப்பையும், Updated Date மற்றும் Final Merged நிலையை மாற்ற வேண்டும்.
6. **Archive Policy (`ARCHIVE_POLICY.md`):** முந்தைய காலி நிலையை நீக்கி, அந்தந்த வகுப்பின் உண்மையான Archive நிலையைப் பதிவு செய்ய வேண்டும்.

### STEP 10 — இறுதி Report மற்றும் Class Closure

ஒரு வகுப்பை COMPLETE என்று அறிவிக்க இந்த நிபந்தனைகள் அனைத்தும் பூர்த்தியாக வேண்டும்:

- [ ] அந்த வகுப்பின் அனைத்து Official API / SCERT Book Records பட்டியலிடப்பட்டுள்ளன.
- [ ] ஒவ்வொரு புத்தகத்திற்கும் Edition Status உள்ளது.
- [ ] வெளியிடப்படாத / கிடைக்காத புத்தகங்கள் Pending எனத் தெளிவாக உள்ளன.
- [ ] பழைய புத்தகங்கள் மற்றும் தொடர்புடைய கேள்வி உள்ளடக்கங்கள் பாதுகாக்கப்பட்டுள்ளன.
- [ ] புதிய புத்தகங்கள் சரியான Active Folder-ல் உள்ளன.
- [ ] Archive File Count / Active File Count பொருந்துகின்றன.
- [ ] Blob SHA / Checksum Audit முடிந்துள்ளது.
- [ ] Main Merge Commit-கள் உறுதிப்படுத்தப்பட்டுள்ளன.
- [ ] Official CDN / Page 2 / Active / Archive / Questions Links அனைத்தும் சரிபார்க்கப்பட்டுள்ளன.
- [ ] Central Master Register புதுப்பிக்கப்பட்டுள்ளது.
- [ ] Final Audit Report வெளியிடப்பட்டுள்ளது.
- [ ] இறுதியில் கண்டுபிடிக்கப்பட்ட Link / Path Correction-கள் சரிசெய்யப்பட்டு மீண்டும் Test செய்யப்பட்டுள்ளன.
- [ ] எந்த Local Clone / Download-மும் பயனரின் கணினியில் செய்யப்படவில்லை.

இந்த Check-list-ல் ஏதேனும் ஒன்று நிறைவேறாவிட்டால் முழு வகுப்பையும் COMPLETE என்று அறிவிக்கக்கூடாது. தேவையானால் MIGRATION_COMPLETE_DOCUMENTATION_PENDING அல்லது MIGRATION_BLOCKED என்று துல்லியமான நிலை தெரிவிக்கவும்.

---

## 5. Questions / Answers / Quiz பிரிப்பு விதிகள்

### பழைய Edition

பழைய புத்தகத்தின் கீழ் உருவாக்கப்பட்ட:
- questions.md
- answers.md
- quiz.md
- quiz.json
- Master Quiz Mapping
- Book-back Questions
- Source / Page References

இவை அந்தப் பழைய Edition-ன் வரலாற்று ஆதாரங்களாக Archive-க்கு செல்ல வேண்டும். Archive-ல் அவற்றின் பழைய Folder Structure மற்றும் உறவுகளைப் பாதுகாக்கவும்.

### புதிய Edition

புதிய புத்தகத்திற்காக உருவாக்கப்பட்டு ஆதாரம் சரிபார்க்கப்பட்ட கோப்புகள் மட்டும் Active Folder-ல் இருக்க வேண்டும்.

- பழைய Questions-ஐ அப்படியே புதிய Edition Questions என்று மாற்றக்கூடாது.
- Answers-ன் Source Page பழைய புத்தகத்தைச் சுட்டினால் அதை புதிய Edition-ல் பயன்படுத்தக்கூடாது.
- புதிய புத்தகத்தின் Book-back / Evaluation பகுதிகள் மாறியுள்ளனவா என்று சரிபார்க்கவும்.
- இந்த Migration பணியில் Answer உருவாக்குதல் அல்லது Quiz மாற்றம் தனி அனுமதி இல்லாமல் செய்யக்கூடாது.

### Path / Link கட்டுப்பாடு

ஒவ்வொரு கோப்பின் உண்மையான GitHub Path-ஐ Tree-ல் பார்த்தே பதிவு செய்ய வேண்டும்.

உதாரணமாக, உண்மையான Path:

**books/2026-27/term1/vol1_tamil_english/book_back_questions/questions.md**

இதற்குப் பதிலாக:

**books/2026-27/term1/vol1_tamil_english/questions.md**

என்று தவறாக உருவாக்கக்கூடாது.

---

## 6. நேரம் மற்றும் Token செலவை குறைக்கும் முறை

| செய்ய வேண்டியது | தவிர்க்க வேண்டியது |
|---|---|
| முதலில் முழு class tree-யில் உள்ள உண்மையான புத்தக எண்ணிக்கையைக் கண்டறிதல் | PDF-களைப் பார்த்தவுடன் upload / move தொடங்குதல் |
| ஒவ்வொரு புத்தகத்தின் Page 2 imprint-ஐ வைத்து edition அடையாளம் காணுதல் | Folder name / filename மட்டும் வைத்து old/new முடிவு செய்தல் |
| ஒரே edition duplicate என்றால் முழு 100% content SHA ஒப்பிட்டு canonical copy மட்டும் வைத்தல் | ஒரே பதிப்பின் duplicate-ஐத் தவறாக Archive-ல் சேமித்தல் |
| ஒரு புத்தகத்தின் முழு package-ஐ 200–300 file-க்குள் batch செய்து commit செய்தல் | 1,000–1,500 files-ஐ ஒரே upload / tree / commit-ல் அனுப்புதல் |
| ஒவ்வொரு batch-க்கும் checkpoint + SHA audit செய்து அடுத்த batch-க்கு நகர்தல் | வெற்றி பெற்ற files-ஐ மீண்டும் upload செய்தல் |
| Retry-க்கு back-off; interruption-க்கு checkpoint resume | ஒரே request-ஐ வேகமாகத் தொடர்ந்து retry செய்து rate limit தூண்டுதல் |
| ஒரே புத்தகத்தை முடித்து BOOK_PACKAGE_COMPLETE செய்த பின் அடுத்த புத்தகம் | புத்தகத்தை பாதியில் விட்டுவிட்டு unrelated correction / UI / quiz வேலையில் மாறுதல் |
| ஒரே Repo-க்குள் Existing Blob SHA மறுபயன்பாடு | PDF-களை மீண்டும் Download / Upload செய்தல் |
| Branch / batch commit SHA மூலம் ஒவ்வொரு checkpoint-யும் உறுதிப்படுத்துதல் | Background task-ஐ அடிக்கடி poll செய்து அல்லது வெறும் progress percentage-ஐ நம்புதல் |

**Token Saving முக்கியம்; ஆனால் ஆதாரம் குறையக்கூடாது.** குறைந்த API Calls பயன்படுத்தலாம். ஆனால் முக்கியமான Book / Page / Question / Link Verification-ஐ தவிர்க்கக்கூடாது.

---

## 7. Pilot-ல் கற்றுக்கொண்ட பாடங்கள் (Class 01, Class 02 & Class 03)

### Class 03 Migration — பெரிய ஒரே upload-இல் ஏற்பட்ட recovery / rate-limit பிரச்சினை (2026-11-08)

Class 03 Archive transfer log-ல் 1,462 பழைய files-ஐ ஒரே பெரிய transfer task-ஆக நகர்த்தும்போது repeated retry, task interruption, GitHub rate-limit checks மற்றும் Tree உருவாக்கத்தில் HTTP 422 failure ஆகியவை பதிவாகின. பின்னர் recovery முயற்சிகளுடன் migration முடிந்ததாக report செய்யப்பட்டது. Log மட்டும் பார்த்து 422-ன் துல்லியமான காரணம் உறுதி செய்யப்படவில்லை; எனவே அதை rate limit அல்லது payload size என்று ஆதாரமின்றி வகைப்படுத்தக்கூடாது.

**கட்டாய மாற்றம்:** இனி ஒரே பெரிய class-wide upload தடை. Book-first + 200–300 file sub-batches + per-batch commit + immediate Blob SHA verification + persisted checkpoint + idempotent resume விதி கட்டாயம். ஏற்கெனவே வெற்றி பெற்ற file-களை மீண்டும் upload செய்யக்கூடாது. 422 வந்தால் காரணத்தைத் தனியாக ஆய்வு செய்ய வேண்டும்; same payload-ஐ loop-ஆக retry செய்யக்கூடாது. ஒரே புத்தகத்தின் package முழுமை அடையும் வரை அடுத்த புத்தகத்துக்கோ unrelated correction-க்கோ மாறக்கூடாது.


### Class 02 Pilot-ல் கற்றுக்கொண்ட முக்கியமான பாடம் — Production Viewer & UI Routing பிழை
- **பிரச்சினை:** Class 02-ல் கோப்புகள் அனைத்தும் Archive மற்றும் Active Repository-களில் 100% Git Blob SHA பொருத்தத்துடன் Merge செய்யப்பட்டன. ஆனால், `index.html`-ல் இருந்த 222 இணைப்புகள் நீக்கப்பட்ட பழைய `./tamil/...` போன்ற Subject Folder-களைச் சுட்டின (404 பிழை). மேலும், `viewer.html`-ல் Default PDF பழைய பாதையைச் சுட்டியதுடன், `page-001.pdf` என்ற புதிய 3-இலக்கப் பெயரமைப்பை ஆதரிக்காமல் முந்தைய/அடுத்த பக்க நகர்வு தடைபட்டது.
- **கற்றுக்கொண்ட பாடம்:** 
  1. PDF கோப்புகள் Branch-ல் சரியாக இருப்பது மட்டும் ஒரு பாடநூல் போர்ட்டலின் வெற்றியாகாது.
  2. Main Merge செய்வதற்கு முன்பாக, இணையதள UI மற்றும் Viewer புதிய பாதைகளையும், புதிய கோப்புப் பெயரமைப்பையும் சரியாகக் கையாள்கிறதா என்பதை ஒரு தனி `fix/` கிளையில் வைத்து முழுமையாகச் சோதிக்க வேண்டும்.
  3. எந்தவொரு இணைப்பு 404 கொடுத்தாலும் Step 8 Main Merge தடை செய்யப்பட வேண்டும்.
  4. Merge முடிந்த பிறகு README, Audit Report, Master Index, Archive Policy ஆகிய ஐந்து ஆவணங்களும் தற்போதைய Main நிலைக்கு உடனடியாக ஒத்திசைக்கப்பட வேண்டும்.

### Class 01 Pilot-ல் கற்றுக்கொண்ட பாடங்கள்

Class 01-ன் 2026-11-07 Migration-ல் கிடைத்த சரிபார்க்கப்பட்ட குறிப்புகள்:

### Archive Main
- 1,189 Legacy Files
- 1,062 PDF
- 109 Questions Markdown
- 18 pages.json Manifest
- மொத்தம்: 1,189
- Source மற்றும் Archive Tree-ல் 1,189 Git Blob SHA-கள் பொருந்தியதாக Audit செய்யப்பட்டது.
- Archive Main Merge Commit: 1a38a4c6d8dcaba7b4e1b511a089656fca4260d7

### Active Main
- 848 புதிய 2026 Page PDF Files
- 6 புதிய Edition-க்கான Questions Markdown
- 30 JSON Manifest / Metadata Files
- மொத்தம்: 884
- 848 Page PDF-களும் ஏற்கெனவே உள்ள Verified Edition Branch-ன் அதே Blob SHA-களுடன் பொருந்தின.
- Active Main Merge Commit: b20b8d38a2decd66db25e8053318027d23a04c1e

### முக்கியமான தவறுகள் / மேம்பாடுகள்

1. தேவையற்ற Local Clone-கள் C: Drive-ல் அதிக Storage எடுத்தன. Cleanup Report-ல் 11.39 GB மீட்கப்பட்டதாக Agent தெரிவித்தது. இதுபோன்ற Storage பயன்பாடு மீண்டும் ஏற்படக்கூடாது.
2. ஒரே Repository-க்குள் Folder Path மட்டும் மாற்ற வேண்டிய இடத்தில் Git Trees API மூலம் Existing Blob SHA-ஐ மறுபயன்படுத்தியிருக்க முடியும்.
3. புதிய 848 PDF Pages ஏற்கெனவே Audit Branch-ல் இருந்ததால் அவற்றை மீண்டும் Download / Split செய்யத் தேவையில்லை.
4. Archive File Count-ல் 18 கோப்புகள் குறைவாகத் தோன்றிய கணக்கு, 18 pages.json Manifest-கள் என வகைப்படுத்தப்பட்ட பிறகு தீர்ந்தது.
5. Git Blob SHA Match மற்றும் SHA-256 Match இரண்டும் வேறு; அறிக்கையில் பயன்படுத்திய Algorithm-ஐத் தெளிவாகக் குறிப்பிட வேண்டும்.
6. Main Merge-க்கு முன் Branch-ல் இருப்பதை மட்டும் வைத்து COMPLETE என்று அறிவிக்கக்கூடாது.
7. Main Merge ஆன பிறகும் Register Link-களைத் தனியாகச் சரிபார்க்க வேண்டும்.
8. Class 01-ல் ஆறு Questions Link-கள் தவறான shallow path-ஐச் சுட்டின. உண்மையான Path book_back_questions/questions.md என்று GitHub Tree-ல் உறுதிசெய்து திருத்த வேண்டிய நிலை ஏற்பட்டது.
9. Final Report-ல் பழைய Migration Branch Link மட்டும் இருப்பது போதாது; Main Branch Link மற்றும் Merge SHA-ஐப் பதிவு செய்ய வேண்டும்.
10. வகுப்பு 1-ல் ஆறு 2026 Term-I / Term-II Books Active-ல் வைக்கப்பட்டன. Term-III-க்கு 2026 Official Edition கிடைக்காத நிலையில் பழைய Edition Archive-ல் பாதுகாக்கப்பட்டது. மற்ற வகுப்புகளுக்கு இதே நிலை என்று முன்கூட்டியே கருதக்கூடாது; ஒவ்வொரு முறையும் live official listing மூலம் சரிபார்க்க வேண்டும்.

**இந்த எண்ணிக்கைகள் Class 01 Pilot-ன் வரலாற்று ஆதாரம் மட்டுமே. மற்ற வகுப்புகளுக்கான எதிர்பார்க்கப்படும் File Count ஆகப் பயன்படுத்தக்கூடாது.**

---

## 8. Final Report — கட்டாய வடிவம்

ஒவ்வொரு வகுப்பும் முடிந்ததும் இந்த வடிவில் அறிக்கை கொடுக்க வேண்டும்:

### A. Edition Inventory
- மொத்த Official Book Records:
- Verified Current Editions:
- Legacy / Superseded Editions:
- Pending / Unavailable Editions:
- Unresolved Mapping:

### B. Migration Summary
- Active Repository / Main SHA:
- Archive Repository / Main SHA:
- Active Files Added / Reused:
- Legacy Files Archived:
- Questions / Answers / Quiz Files:
- JSON / Manifest Files:
- Source Files Removed from Active:
- Missing / Extra / Mismatched Files:

### C. Integrity Audit
- Git Blob SHA Match:
- SHA-256 Match (உண்மையாக கணக்கிட்டிருந்தால் மட்டும்):
- Missing:
- Mismatch:
- Duplicate:
- Page Manifest Validation:
- Question / Answer Edition Mapping:

### D. Link Audit
- Official CDN PDF:
- Official Page 2:
- Active GitHub Page 2:
- Archive GitHub Page 2:
- Active Questions / Answers / Quiz:
- Archive Questions / Answers / Quiz:
- Broken Links:

### E. Merge / Documentation
- Migration Branch:
- Archive Merge Commit:
- Active Merge Commit:
- Central Register Commit:
- Final Audit Report Link:
- Remaining Corrections:

### F. Local Storage Safety
- User Local Clone: NO
- User Local Download: NO
- User Local Extraction: NO
- GitHub API / Cloud Operations Only: YES / BLOCKED + காரணம்

---

## 9. பிழை கண்டறியப்பட்டால் என்ன செய்ய வேண்டும்?

Migration முடிந்ததாக அறிவித்த பிறகு ஒரு Link, Folder Path, Page Count, Questions Mapping அல்லது Manifest பிழை கண்டுபிடிக்கப்பட்டால்:

1. உடனடியாக அந்த வகுப்பை முழுமையான Finalized என்று உறுதிப்படுத்த வேண்டாம்.
2. பிழை எந்த Repository / Branch / File / Register Row-ல் உள்ளது என்று குறிப்பிடவும்.
3. பாதிக்கப்பட்ட கோப்புகள் மட்டும் GitHub API வழியாக ஆய்வு செய்யவும்.
4. பாடப்புத்தக PDF / Questions உள்ளடக்கம் சரியாக இருந்தால் அவற்றைத் தொடக்கூடாது; தேவையான Documentation / Link மட்டும் திருத்தவும்.
5. திருத்தத்திற்கு தனி Commit உருவாக்கவும்.
6. திருத்தப்பட்ட Link / File-ஐ மறுபடியும் GitHub-ல் திறந்து உறுதிப்படுத்தவும்.
7. Central Register மற்றும் Final Audit Report இரண்டிலும் சரியான விவரம் பிரதிபலிக்கிறதா பார்க்கவும்.
8. புதிய Commit SHA மற்றும் Correction Summary-ஐ இறுதி அறிக்கையில் சேர்க்கவும்.
9. மீண்டும் தவறான Link இருப்பின் பழைய COMPLETE Status-ஐ வைத்திருக்கக்கூடாது.

**பிழையை கண்டுபிடிப்பது தோல்வி அல்ல; சரிசெய்து மறுபரிசோதனை செய்யாமல் COMPLETE என்று விடுவது தான் தவறு.**

---

## 10. புதிய Chat / புதிய Agent தொடங்கும்போது பின்பற்ற வேண்டிய கட்டளை

இந்த Project-ல் புதிய Chat அல்லது புதிய Agent தொடங்கும்போது முதலில்:

1. இந்த Workflow ஆவணத்தை முழுமையாக வாசிக்கவும்.
2. Common Repository README மற்றும் Repository Map-ஐப் பார்க்கவும்.
3. Book Edition Verification Rules மற்றும் Page 2 Gate-ஐ வாசிக்கவும்.
4. அந்த வகுப்பின் Edition Register, Audit Summary, Migration Branches ஆகியவற்றைப் படிக்கவும்.
5. ஏற்கெனவே முடிந்த பணியை மீண்டும் செய்யாமல் தற்போதைய Main / Branch SHA மூலம் நிலையை உறுதிப்படுத்தவும்.
6. பயனர் ஏற்கெனவே வழங்கிய No Local Clone விதியை மீண்டும் கேட்க வேண்டாம்; அது நிரந்தர கட்டுப்பாடு.
7. அடுத்த செய்ய வேண்டிய ஒரு படியைத் தெளிவாகச் சொல்லி, அனுமதி தேவைப்படும் செயலுக்கு முன் நிறுத்தவும்.
8. ஒரு வகுப்பை முடிக்காமல் அடுத்த வகுப்பைத் தொடங்கக்கூடாது.

### சுருக்கமான கட்டாய விதி

**முதலில் Main Book Inventory / Book Count → ஒவ்வொரு புத்தக Page 2 Imprint → Old / New / Identical Duplicate முடிவு → Questions / Manifests / Support Files Package Mapping → Book-wise 200–300 File Batches + Checkpoint Commits → Batch SHA Audit → Archive Main Verify / Merge → Active Main Verify / Merge → அதன் பிறகே Corrections / UI / Quiz பணிகள் → Central Register → Final Cross-Verification → COMPLETE.**

இந்த வரிசையைத் தவிர்த்து நேரடியாக File Move / Delete / Main Merge செய்யக்கூடாது.

---

## 11. Class 01 முதல் Class 12 வரை ஒரே தரநிலை

- Class 01 Pilot-ன் செயல்முறை மற்றும் தவறுகள் வழிகாட்டியாகப் பயன்படுத்தப்பட வேண்டும்.
- Class 02 முதல் Class 12 வரை ஒவ்வொரு வகுப்பின் உண்மையான Book Structure, Official Release, Folder Structure, File Count ஆகியவை தனியாகச் சரிபார்க்கப்பட வேண்டும்.
- Class 01-ன் 6 Books / 848 Pages / 1,189 Legacy Files போன்ற எண்ணிக்கைகளை மற்ற வகுப்புகளுக்கு Copy செய்யக்கூடாது.
- ஒவ்வொரு வகுப்புக்கும் தனி Migration Branch, தனி Register, தனி Audit Report இருக்க வேண்டும்.
- ஒரே நேரத்தில் பல வகுப்புகளின் Main-ஐ மாற்றக்கூடாது.
- ஒரு வகுப்பின் Migration மற்றும் Documentation Correction முழுமையாக முடிந்த பிறகே அடுத்த வகுப்புக்குச் செல்ல வேண்டும்.

**ஆவணத்தின் இறுதி நோக்கம்:** குறைந்த Token செலவு, குறைந்த API Calls, Local Disk பயன்பாடு இல்லாமை, தவறான Edition கலப்பு இல்லாமை, சரியான GitHub Folder அமைப்பு மற்றும் ஆதாரத்துடன் நிரூபிக்கக்கூடிய Final Result.