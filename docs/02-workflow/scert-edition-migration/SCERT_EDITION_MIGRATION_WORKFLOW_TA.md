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

ஒரு வகுப்பில் உள்ள ஒவ்வொரு புத்தகத்தையும் தனித்தனி Record-ஆகப் பதிவு செய்யவும்.

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

### STEP 5 — Migration Plan மற்றும் Approval Gate

Draft Register முடிந்த பிறகு:

1. பழைய Edition எந்த Archive Folder-க்கு செல்ல வேண்டும் என்று பட்டியலிடவும்.
2. புதிய Edition எந்த Active Folder-ல் இருக்க வேண்டும் என்று பட்டியலிடவும்.
3. பழைய Questions / Answers / Quiz-க்கான Archive Mapping தரவும்.
4. புதிய Questions / Answers / Quiz எந்த ஆதார Branch-ல் இருந்து வர வேண்டும் என்பதை குறிப்பிடவும்.
5. மாற்றப்பட வேண்டிய கோப்புகள், மாற்றப்படக்கூடாத கோப்புகள் இரண்டையும் பட்டியலிடவும்.
6. எதிர்பார்க்கப்படும் File Count மற்றும் Destination Path-களைத் தெளிவுபடுத்தவும்.
7. Draft / Mapping-ஐ பயனரிடம் Review-க்கு கொடுக்கவும்.

**பயனர் ஒப்புதல் கிடைக்கும் வரை எந்த File Move, Delete, Overwrite, Main Merge-மும் செய்யக்கூடாது.**

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

#### B. ஒரு Repository-லிருந்து மற்றொரு Repository-க்கு Archive Transfer

1. Source Repository-யின் குறிப்பிட்ட Branch Tree-ஐ வாசிக்கவும்.
2. தேவையான Legacy Folder-கள் மற்றும் Blob SHA-களை மட்டும் பட்டியலிடவும்.
3. Destination Archive Repository-யில் அதே Content-ஐ Blob-ஆகப் பதிவு செய்யவும்.
4. முழு Legacy Folder Structure-ஐ Destination Tree-ல் உருவாக்கவும்.
5. ஒரே Batch Commit உருவாக்கவும்.
6. Destination Branch-ஐ புதுப்பிக்கவும்.
7. Source / Destination Path எண்ணிக்கை மற்றும் Blob SHA-களை ஒப்பிடவும்.
8. எல்லா கோப்புகளும் Destination-ல் சரியாக உள்ளன என்று உறுதிப்படுத்திய பிறகே Source Migration Branch-ல் பழைய Path-களை நீக்கவும்.

Cross-repository transfer-க்கு இரண்டு Repository-களுக்கும் தனித்தனி Git Object Database உள்ளது. எனவே புதிய Repository-யில் Blob பதிவு தேவைப்படலாம். ஆனால் இதற்காக பயனரின் கணினிக்கு கோப்புகளை Download செய்யக்கூடாது.

**API அளவு / Rate Limit / Binary Limit காரணமாக இயலவில்லை என்றால் நிறுத்தவும்.** Local Clone வழியாக மாற்று முயற்சி செய்யக்கூடாது. தேவையானால் GitHub-hosted Cloud Runner வழியை முன்மொழிந்து அனுமதி பெறவும்.

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

### STEP 9 — Central Register மற்றும் Link Update

Migration Merge முடிந்த பிறகு மட்டுமே Final Links புதுப்பிக்க வேண்டும்.

ஒவ்வொரு புத்தகத்திற்கும்:

- Official CDN PDF Link
- Official CDN PDF + #page=2
- புதிய Active GitHub PDF Link
- புதிய Active GitHub Page 2 Link
- புதிய Questions / Answers / Quiz Link
- பழைய Archive GitHub PDF Link
- பழைய Archive GitHub Page 2 Link
- பழைய Questions / Answers / Quiz Archive Link
- Final Repository / Main Branch / Folder Path
- Migration Commit SHA

**Links உருவாக்கும் விதி:**

1. GitHub Tree / Contents API-ல் உண்மையாக உள்ள Path-ஐப் பெறு.
2. அந்த Path-ஐப் பயன்படுத்தி Link உருவாக்கு.
3. Link உண்மையாக திறக்கிறதா என்று Test செய்.
4. /questions.md என்று ஊகிக்காதே. உண்மையான Path book_back_questions/questions.md என்றால் அதையே பயன்படுத்து.
5. Link 404 கொடுத்தால் Register-ல் வெளியிடாதே.
6. #page=2 Link-ன் அடிப்படை PDF சரியான புத்தகத்திற்குரியது என்பதை உறுதிசெய்.

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
| ஒவ்வொரு Branch Tree-ஐ ஒருமுறைப் பெற்று அதிலிருந்து தேவைப்படும் File பட்டியலை உருவாக்குதல் | ஒவ்வொரு File-க்கும் மீண்டும் மீண்டும் முழு Tree கேட்பது |
| ஒரே Batch-ல் பல Blob / Tree / Commit செயல்கள் | நூற்றுக்கணக்கான தனித்தனி File Commit-கள் |
| ஒரே Repo-க்குள் Existing Blob SHA மறுபயன்பாடு | PDF-களை மீண்டும் Download / Upload செய்தல் |
| Cross-Repo-க்கு தேவையான கோப்புகள் மட்டும் மாற்றுதல் | முழு Repository-யையும் Clone செய்தல் |
| ஏற்கெனவே உள்ள Verified Page Assets பயன்படுத்துதல் | தேவையில்லாமல் மீண்டும் PDF Split செய்தல் |
| Task முடிந்ததா என்று உண்மையான Branch SHA / Commit மூலம் சரிபார்த்தல் | அதே Background Task-ஐ அடிக்கடி Poll செய்து நேரம் வீணாக்குதல் |
| API Error-ஐ ஒருமுறை ஆய்வு செய்து துல்லியமான மாற்று முயற்சி | Clone / Fetch / Download என்று தொடர்ந்து முறை மாற்றுதல் |
| சுருக்கமான ஆனால் முழு Audit Report | ஒவ்வொரு 5–10 விநாடிக்கும் பயனற்ற Status Message |

**Token Saving முக்கியம்; ஆனால் ஆதாரம் குறையக்கூடாது.** குறைந்த API Calls பயன்படுத்தலாம். ஆனால் முக்கியமான Book / Page / Question / Link Verification-ஐ தவிர்க்கக்கூடாது.

---

## 7. Class 01 Pilot-ல் கற்றுக்கொண்ட பாடங்கள்

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

**முதலில் ஆய்வு → ஆதார சரிபார்ப்பு → Rough Register → Folder Mapping → User Approval → GitHub-only Migration → SHA / Path / Link Audit → Archive Main Merge → Active Main Merge → Central Register Update → Final Cross-Verification → COMPLETE.**

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