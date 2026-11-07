# TN Samacheer Kalvi — Project Blueprint & Source Research Report

> **ஆவண நிலை:** Working Blueprint / Source Research & Operating Rules  
> **கடைசி முக்கிய பணிமுறை மாற்றம்:** 05-11-2026  
> **மொழி:** தமிழ் + தேவையான Technical English  
> **Repository:** [Eaglesiva/tn-class-10](https://github.com/Eaglesiva/tn-class-10)

## 1. Project நோக்கம்

இந்தத் திட்டத்தில் இரண்டு தனித்தனி வேலைகள் உள்ளன:

1. **Quiz Creation:** பாடநூலில் ஏற்கெனவே objective / MCQ வடிவில் உள்ள கேள்விகளுக்கான quiz கோப்புகளை தனியாகப் பராமரித்தல்.
2. **Answer Source Collection:** Book Back கேள்விகளுக்கு வெளிப்புற கல்வி இணையதளங்கள், இலக்கண ஆதாரங்கள், Publisher Guide-களில் பதில் எங்கு உள்ளது என்பதை கண்டறிந்து, கேள்விவாரியாக நேரடி source links சேகரித்தல்.

**இந்த Answer Source Collection கட்டத்தில் மாணவர் விடைகளை எழுதுவது இலக்கு அல்ல.** Non-objective கேள்விகளுக்கு ChatGPT அல்லது extractor சொந்தமாக விடை எழுதவோ, source-களை ஒன்றிணைத்து paraphrase செய்யவோ, 3-tier model answer உருவாக்கவோ கூடாது. User பின்னர் source-களைத் திறந்து ஒப்பிட்டு தன் சொந்த விடையைத் தயாரிப்பார்.

## 2. User-authoritative decisions — தற்போதைய கட்டாய விதிகள்

| எண் | முடிவு | செயல்படுத்த வேண்டியது |
|---|---|---|
| 1 | questions.md தான் கேள்வி அடிப்படை | அசல் கேள்வி உரை, வரிசை, எண், பிரிவு மாற்றப்படக்கூடாது |
| 2 | Non-objective கேள்விகள் | விடை எழுத வேண்டாம்; 3 காலி placeholders + எல்லா சரிபார்க்கப்பட்ட direct source links மட்டும் |
| 3 | மூன்று Answer Tiers | 🔑 விடைக்குறிப்பு, 📝 சாதாரண விடை, 📖 விரிவான விடை — அனைத்தும் [TO_BE_PREPARED_LATER] |
| 4 | Objective / one-word / MCQ | Source-ல் காணப்பட்ட option code + குறுகிய answer text மட்டும்; ஒவ்வொரு source தனித்தனியாக |
| 5 | காரண விளக்கம் | ஒவ்வொரு one-mark / one-word வினாவுக்கும் பொருத்தமான காரண விளக்கம்: இலக்கணம், பாடநூல் சொற்பொருள், பாடப்பொருள், வகைப்பாடு அல்லது பொதுத் தகவல்; ஆதார URL கட்டாயம் |
| 6 | பொருள்/அறிவு சார்ந்த MCQ | இலக்கணம் அல்லாத வினாவுக்கும் பாடநூல் / கருத்து / வகைப்பாடு source-ஐ வைத்து காரண விளக்கம் தேட வேண்டும்; ஆதாரம் இல்லையெனில் EXPLANATION_SOURCE_NOT_FOUND |
| 7 | Source எண்ணிக்கை | 3 அல்லது 5 என்ற வரம்பு இல்லை; உண்மையில் பதில் உள்ள எல்லா சரிபார்க்கப்பட்ட source-களையும் சேர்க்க வேண்டும் |
| 8 | Source fidelity | ஒவ்வொரு தளமும் சொல்வதை தனித்தனியாக வைக்க வேண்டும்; விடைகளை merge செய்யவோ ஒன்றைத் தேர்ந்தெடுத்து மற்றதை மறைக்கவோ கூடாது |
| 9 | Guide PDF | நேரடி PDF மற்றும் சரியான page number திறந்து சரிபார்த்தால் மட்டுமே answer source; விற்பனைப் பக்கம் PDF-க்கு மாற்றாகாது |
| 10 | கேள்வி வேறுபாடு | Wording / பெயர் / சொல் வேறுபாட்டை WORDING_VARIANT அல்லது QUESTION_MISMATCH என்று காட்ட வேண்டும் |
| 11 | கிடைக்காத தகவல் | ஊகிக்காமல் ANSWER_NOT_FOUND, ACCESS_BLOCKED, GRAMMAR_RULE_NOT_FOUND போன்ற status |
| 12 | GitHub பங்கு | பல கருவிகளுக்கான temporary common workspace மட்டும்; public student website அல்ல |
| 13 | Deployment / merge | Deploy, publish, merge to main, site routing மாற்றம் செய்யக்கூடாது |
| 14 | Cleanup | User தானாகக் கோப்புகளை எடுத்துக்கொண்ட பிறகு temporary files / branches cleanup செய்வார்; assistant delete செய்யக்கூடாது |

## 3. Repository மற்றும் File Structure

தற்போதைய Class 10 working repository:

[https://github.com/Eaglesiva/tn-class-10](https://github.com/Eaglesiva/tn-class-10)

### ஒவ்வொரு Chapter-ன் அடிப்படை அமைப்பு

    <subject>/
    └── <chapter>/
        └── book_back_questions/
            ├── questions.md
            ├── quiz.md
            ├── quiz.json
            └── answers.md

| File | பணி |
|---|---|
| questions.md | அசல் Book Back Questions; இந்த Answer Source பணியில் read-only |
| quiz.md | Objective quiz-க்கான தனி வாசிப்பு வடிவம் |
| quiz.json | Quiz structured data |
| quiz.start.md / quiz.start.json | One-mark quiz generation-க்கான இடைநிலை input/output கோப்புகள் என user குறிப்பிடுகிறார்; இந்த branch-ல் schema/blueprint இல்லை. Antigravity வழங்கும் canonical schema கிடைத்த பிறகே உருவாக்க வேண்டும் |
| answers.md | கேள்வி வாரியான answer source links; objective source answers; தேவையான grammar-rule reason; non-objective காலி placeholders |

Project-wide edition/source research docs/PROJECT_BLUEPRINT_TA.md-ல் இருக்கும். Chapter-specific answer collection rules ANSWER_RESEARCH_BLUEPRINT_TA.md-ல் இருக்கும்.

## 4. Quiz Creation Rules

Quiz பணி Answer Source Collection-இலிருந்து தனியாகவே இருக்கும்.

### Quiz-ல் சேர்க்கக்கூடியவை
- பாடநூலில் நேரடியாக உள்ள one-word / one-mark / objective கேள்விகள்.
- பாடநூலில் ஏற்கெனவே நான்கு தேர்வுகளுடன் உள்ள MCQ-கள் — கேள்வி, option வரிசை, சரியான விடை ஆகியவற்றை source-க்கு ஏற்றபடி பாதுகாத்து பயன்படுத்த வேண்டும்.
- பாடநூலில் one-word / one-mark வினாவாக உள்ள fill-in-the-blank, பொருத்துக, கூற்று சார்ந்த வினா, சொல்/பொருள் தேர்வு போன்ற பிற objective வடிவங்கள் — அவற்றின் மூல வினா நோக்கத்தை மாற்றாமல் நான்கு-option MCQ-ஆக மாற்றலாம்.
- இவ்வாறு மாற்றும்போது ஒரு சரியான விடை + மூன்று தவறான ஆனால் நம்பத்தகுந்த distractor-கள் அமைக்க வேண்டும். சரியான விடை source-ல் உறுதிப்படுத்தப்பட்டிருக்க வேண்டும்; distractor-கள் கேள்வியின் பாடப்பகுதியைச் சேர்ந்த தவறான தேர்வுகளாக இருக்க வேண்டும்.
- ஒவ்வொரு one-mark வினாவுக்கும் பொருத்தமான காரண விளக்கம் சேர்க்க வேண்டும். அது இலக்கண விதி, பாடநூல் சொற்பொருள், பாடப்பொருள் விளக்கம், வகைப்பாடு அல்லது பொது அறிவு சார்ந்ததாக இருக்கலாம். காரண விளக்கத்திற்கும் தனி ஆதார URL கட்டாயம்.
- ஏற்கெனவே 4 options உள்ள கேள்விகளின் option-களை தேவையின்றி மறுஎழுதவோ மாற்றவோ கூடாது.

### Quiz-ல் சேர்க்கக்கூடாதவை
- குறுவினா, சிறுவினா, நெடுவினா.
- திறந்தநிலை உரையாடல், மேடைப்பேச்சு, கட்டுரை, எழுதிப் பழகும் பணிகள்.
- பெரிய கேள்வியின் உள்ளடக்கத்திலிருந்து புதிதாக ஒரு one-word / MCQ வினாவை உருவாக்குதல்.
- நீண்ட விடையின் ஒரு வரியை மட்டும் வெட்டி objective கேள்வியாகக் காட்டுதல்.
- பாடநூலில் இல்லாத கேள்வி வடிவம் அல்லது வெளியிலிருந்து உருவாக்கிய புதிய வினாக்களை book-back quiz எனக் கலப்பது.

### Answer-to-Quiz data flow
- `answers.md` தான் answer verification-க்கான canonical source register: source-wise correct answer, conflict status, reason text, reason source URL ஆகியவை அங்கே முதலில் உறுதி செய்யப்பட வேண்டும்.
- அதே verified one-mark question, correct answer, reason, source links ஆகியவை Antigravity வழங்கும் schema-க்கு ஏற்ப `quiz.start.md` / `quiz.start.json`-க்கு மாற்றப்பட வேண்டும்.
- Quiz output-ல் answer.md-ல் இல்லாத அல்லது உறுதிசெய்யப்படாத correct answer உருவாக்கக்கூடாது.
- ஒரு கேள்விக்கு source conflict தீர்க்கப்படவில்லை என்றால் அது final quiz-க்கு செல்லக்கூடாது; `CONFLICT_REVIEW_REQUIRED` எனத் தற்காலிகமாக நிறுத்த வேண்டும்.
- Non-objective கேள்விகளின் மூன்று answer tiers quiz-க்கு செல்லாது.

### காரண விளக்கம் — எல்லா one-mark கேள்விகளுக்கும்
- இலக்கணம் மட்டுமல்ல; பாடநூல் சொற்பொருள், இலக்கிய/பாடப்பொருள், தாவர/வகைப்பாடு, பொதுத் தகவல் போன்றவற்றுக்கும் வினாவுக்கு ஏற்ற விளக்கம் தர வேண்டும்.
- முதன்மை ஆதாரம் பாடநூலின் தொடர்புடைய பகுதி. தேவைப்பட்டால் நம்பகமான வெளி source பயன்படுத்தலாம்.
- Extractor தன் சொற்களில் விளக்கத்தைச் சுருக்கினால் `Extractor-written explanation based on cited source` என்று label செய்ய வேண்டும்.
- ஆதாரம் இல்லாத விளக்கத்தை ஊகிக்கக்கூடாது; `EXPLANATION_SOURCE_NOT_FOUND` என்று குறிக்க வேண்டும்.

### quiz.start schema status
- இந்த repository / working branch-ல் `quiz.start.md`, `quiz.start.json` அல்லது அவற்றுக்கான dedicated blueprint கண்டறியப்படவில்லை.
- தற்போது உள்ள `quiz.md`, `quiz.json` என்பது ஏற்கெனவே உள்ள quiz artifact-கள்; அவை quiz.start schema-வாகக் கருதப்படக்கூடாது.
- Antigravity-யிடம் canonical field list, ID convention, option format, correct-answer representation, explanation/source fields, conversion rules, sample files ஆகியவற்றைக் கேட்டு பெற வேண்டும்.
- அந்த schema கிடைக்கும் வரை quiz.start கோப்புகளை உருவாக்கவோ, தற்போதைய quiz.md/json-ஐ overwrite செய்யவோ கூடாது.

## 5. Answer Source Collection — தற்போதைய ஒரே நடைமுறை

### 5.1 Non-objective கேள்விகளுக்கு source links மட்டும்

குறுவினா, சிறுவினா, நெடுவினா, திறந்தநிலைப் பயிற்சி, உரையாடல்/மேடைப்பேச்சு போன்ற கேள்விகளுக்கு:
- questions.md-இல் உள்ள அசல் கேள்வியை அப்படியே இடு.
- மூன்று காலி placeholders மட்டும் சேர்:
  - 🔑 விடைக்குறிப்பு — [TO_BE_PREPARED_LATER]
  - 📝 சாதாரண விடை — [TO_BE_PREPARED_LATER]
  - 📖 விரிவான விடை — [TO_BE_PREPARED_LATER]
- அந்தக் கேள்விக்குப் பதில் உள்ள எல்லா நேரடி Website / Guide PDF links-ஐத் தனித்தனியாகக் கொடு.
- அந்த source page-ல் பதில் உள்ளது என்று திறந்து உறுதி செய்யாவிட்டால் ANSWER_FOUND எனக் குறிக்கக்கூடாது.
- நீண்ட answer உரை, paraphrase, சுருக்கம், சொந்த bullet points, சொந்த model answer எதுவும் எழுதக்கூடாது.

### 5.2 Objective / one-word / MCQ கேள்விகள்

இந்த வகையில் மட்டும்:
- Source-ல் நேரடியாகக் காணப்பட்ட option code + குறுகிய answer text.
- ஒவ்வொரு Website / Source-ன் answer தனித்தனி record.
- Source-கள் முரண்பட்டால் ஒவ்வொன்றையும் காட்டி CONFLICT எனக் குறி.
- இலக்கண விதி கேள்வி என்றால் மட்டுமே, பொருந்தும் விதியை நேரடியாக விளக்கும் இலக்கண source-ஐத் திறந்து, 1–2 வரி காரண விளக்கத்தை எழுது.
- அந்தக் காரண விளக்கத்தின் direct grammar-rule URL கட்டாயம்.
- காரண விளக்கம் source-லிருந்து verbatim copy அல்ல; cited grammar rule / textbook fact / subject-matter source-ஐ அடிப்படையாகக் கொண்டு extractor எழுதும் குறுகிய குறிப்பு. அதை "Extractor-written explanation based on cited source" என்று தெளிவாக label செய்.
- பொருள்/பொது அறிவு சார்ந்த MCQ-க்கு இலக்கண காரணம் தேடிப் பொருத்தக்கூடாது.

### 5.3 Source எண்ணிக்கை மற்றும் source தரம்

- Source எண்ணிக்கைக்கு 3/5 cap கிடையாது.
- ஒரே கேள்விக்கு உண்மையில் பதில் உள்ள அனைத்து நம்பகமான, திறந்து சரிபார்க்கப்பட்ட source-களையும் பதிவு செய்.
- Page title, publish/update date, edition, exact question match, HTML section/PDF page ஆகியவை கிடைத்தால் சேர்.
- Homepage / search result / index மட்டும் answer page ஆக ஏற்றுக்கொள்ளப்படாது.
- Guide product page என்பது Guide இருப்பதற்கான தகவல்; அது Guide answer/PDF content-க்கு ஆதாரம் அல்ல.

### 5.4 Guide மற்றும் PDF சரிபார்ப்பு

- SURA, DON போன்ற publisher Guide-களைத் தேடு.
- Product listing கிடைத்தால் GUIDE_PRODUCT_PAGE_ONLY என்று குறி.
- Direct PDF திறக்கப்பட்டு கேள்வி மற்றும் விடை கண்டறியப்பட்டால்தான் Answer Source எனக் குறி.
- PDF page number சரியாகத் தெரிந்தால் பதிவு செய்; தெரியாவிட்டால் PDF_PAGE_NOT_VERIFIED.
- Online-ல் இலவச PDF கிடைக்கவில்லை என்றால் இல்லை என்று நேர்மையாகக் குறி; கற்பனை download URL உருவாக்க வேண்டாம்.

### 5.5 Source mismatch மற்றும் conflict

கேள்வியின் சொல், ஆசிரியர் பெயர், option உரை அல்லது வினா அமைப்பு வேறுபட்டால்:
- Original question-ஐத் திருத்தாதே.
- பொருத்தமில்லாத source-ஐ exact match எனக் காட்டாதே.
- WORDING_VARIANT / QUESTION_MISMATCH என்று குறி.
- விடைகள் மாறினால் source ஒவ்வொன்றையும் தனித்தனியாகக் காட்டி CONFLICT குறி.
- ஆதாரம் இல்லாமல் conflict-ஐத் தீர்க்கவோ answer ஒன்றை மறைக்கவோ வேண்டாம்.

### 5.6 ஒரு கேள்விக்கான Output Template

**Objective:**
    ### [Question ID]. [questions.md-இல் உள்ள அசல் வினா]
    S1 — [Source]: [Option code + exact short answer] — [Direct URL]
    S2 — [Source]: [Option code + exact short answer] — [Direct URL]
    💡 காரண விளக்கம்: [Grammar-rule based 1–2 lines, only when supported]
    காரண விளக்க Source: [Direct grammar rule URL]
    QC: [CONFLICT / QUESTION_MISMATCH, if any]

**Non-objective:**
    ### [Question ID]. [questions.md-இல் உள்ள அசல் வினா]
    🔑 விடைக்குறிப்பு — [TO_BE_PREPARED_LATER]
    📝 சாதாரண விடை — [TO_BE_PREPARED_LATER]
    📖 விரிவான விடை — [TO_BE_PREPARED_LATER]
    Source links மட்டும்: [Source name — direct answer page/PDF — match status]

### 5.7 Completion status

ஒவ்வொரு கேள்விக்கும் குறைந்தது ஒன்று:
- ஒன்று அல்லது அதற்கு மேற்பட்ட direct source records;
- அல்லது ANSWER_NOT_FOUND;
- அல்லது ACCESS_BLOCKED;
- அல்லது QUESTION_MISMATCH.

Non-objective 3-tier fields அனைத்தும் காலியாகவே இருக்க வேண்டும்.

## 6. Source Research Report — ஆரம்ப Source பட்டியல்

இந்தப் பட்டியல் 03-11-2026 அன்று நடந்த ஆரம்ப Web Research அடிப்படையில் தொகுக்கப்பட்டது. இது முழுமையான Coverage Audit அல்ல. ஒவ்வொரு Class / Subject / Medium / Term / Chapter-க்கும் தனியாகச் சரிபார்க்க வேண்டிய Source Candidates.

### A. Answer Websites — நேரடி பதில்கள்

| Source | முக்கிய இணைப்பு | இப்போது தெரிந்த Coverage / பயன்பாடு | நிலை / கவனம் |
|---|---|---|---|
| **BrainKart** | [1st–12th State Board Index](https://www.brainkart.com/materials/1st-to-12th---tamilnadu-state-board-school-%28english-and-tamil-medium%29-1001/) | 1–12 TM/EM என்று Class Index; Book Back Answers, One Mark, Guides போன்றவை பட்டியலிடப்பட்டுள்ளன | **High Priority.** Class-wise index உள்ளது; எல்லா பாடங்களிலும் முழு Answers உள்ளதா Audit செய்ய வேண்டும் |
| **BrainKart — Example Answer Page** | [10th Tamil — இயல் 1](https://www.brainkart.in/article/Questions-and-Answers_11807/) | ஒரு மதிப்பெண், குறுவினா, சிறுவினா, நெடுவினா போன்ற பல Question Types | குறிப்பிட்ட பாடத்திற்கான உண்மையான Answer Page எடுத்துக்காட்டு |
| **FreeTNBooks** | [Book Back Questions Index](https://www.freetnbooks.com/samacheer-kalvi-book-back-questions/) | Tamil: Class 3–12; English: Class 5–12 என்று பக்கத்தில் தெளிவாகக் காணப்படுகிறது. பிற Subject Links-யும் உள்ளன | **High Priority.** 1–2க்கு Answer Coverage இந்தப் பக்கத்தில் உறுதி செய்யப்படவில்லை |
| **Padasalai** | [10th Guide / Book Back / Answer Key Index](https://www.padasalai.net/2025/06/10th-Standard-Book-Back-Questions-and-Answer-Keys-Full-Guide.html) | Guide, Answer Key, Question Paper, Study Material Index | Index / Material Source; ஒவ்வொரு Destination Page-ஐத் திறந்து சரிபார்க்க வேண்டும் |
| **KalviTips** | [10th Tamil — Unit 1 Answers](https://www.kalvitips.com/2025/05/10th-tamil-book-back-answers-unit-1-guide-tamilnadu-school-books.html) | 10ஆம் வகுப்பு தமிழ் இயல் 1-க்கான பாடம்-குறிப்பிட்ட Answer Page | நேரடி Answer Source; பிற Class / Subject Coverage தனியாக Audit |
| **Kalvi Imayam** | [12th All Subject Book Back Answers](https://www.kalviimayam.com/2023/02/12th-all-subject-guide-book-back-answers.html) | 12ஆம் வகுப்பு பல பாடங்களுக்கு Book Back Answer Links | 2023 பக்கம்; தற்போதைய Edition-ஐ உறுதிப்படுத்த வேண்டும் |
| **StudentsGuide360** | [10th Tamil Unit 1–9](https://www.studentsguide360.com/10th-tamil-guide-unit-1-to-9-full-answers/) | 10ஆம் வகுப்பு தமிழ் பாடம் வாரியான Answer Material | பழைய / குறைக்கப்பட்ட பாடத்திட்டம் இருக்கலாம் |
| **GreenTamil** | [10th Tamil — இயல் 1](https://www.greentamil.in/2021/06/1-10-tamil-iyal-1-book-back-question.html) | 10ஆம் வகுப்பு தமிழ் Unit 1க்கு கூடுதல் Answer Reference | பழைய பக்கம்; தற்போதைய Textbook Edition-உடன் பொருத்திப் பார்க்க வேண்டும் |
| **eKalvi** | [Solutions Index](https://ekalvi.in/solutions/) | சில வகுப்புகள் / பாடங்களுக்கு Solutions | Partial Source Candidate; முழு 1–12 coverage என்று கருத வேண்டாம் |
| **Nibunan** | [Tamil Study Material](https://nibunan.in/clear-tnpsc-tamil/) | கூடுதல் One-mark / தமிழ் கேள்வி-பதில் போன்றவற்றுக்கு உதவலாம் | Book Back Answer-களுக்கான முதன்மை Source அல்ல; Supplementary மட்டும் |

**Source Independence கவனம்:** BrainKart .com / .in பக்கங்கள் அல்லது ஒரே Content-ஐ Mirror செய்யும் தளங்களை இரண்டு சுயாதீன Sources என்று எண்ணக்கூடாது. Content Origin தெரிந்தால் பதிவு செய்ய வேண்டும்.

### B. Guide PDF Index / Download Websites

| Source | இணைப்பு | பயன்பாடு | கவனம் |
|---|---|---|---|
| **Samacheer Kalvi Students** | [Class 1–12 Guide Index](https://samacheerkalvistudents.in/tamilnadu-school-guides/) | 1–12 Classes; Tamil / English Medium மற்றும் Subject-wise Guide பட்டியல் | Class Pages-ல் நேரடி PDF உள்ளதா திறந்து சரிபார்க்க வேண்டும்; பழைய PDF-களும் இருக்கலாம் |
| Class 1 Guide Page | [1st Standard](https://samacheerkalvistudents.in/tamilnadu-school-guides/1st-standard.html) | Primary Guides, TM/EM என்று பட்டியலிடுகிறது | Term / Edition / Download File சரிபார்ப்பு அவசியம் |
| **KalviMani** | [Main Website](https://kalvimani.in/) | 2026–27 Textbooks; 1–12 Guides 2024–2026; TM/EM மற்றும் Primary Guide Hub என்று தெரிவிக்கிறது | Browser fetch சில நேரங்களில் 521 Error கொடுத்தது; நேரடியாக திறந்து PDF Links சரிபார்க்க வேண்டும் |
| KalviMani Primary | [Classes 1–5 Guides](https://kalvimani.in/primary-school-guides/) | Primary Guide PDF தேடல் | Term மற்றும் உண்மையான PDF Edition சரிபார்க்க வேண்டும் |
| KalviMani — Class 10 | [10th Sura Guides](https://kalvimani.in/10th-standard/sura-guides/) | 10ஆம் வகுப்பு Sura Guide பட்டியல் | PDF Download / Edition சரிபார்ப்பு |
| KalviMani — Class 11 | [11th Sura Guides](https://kalvimani.in/11th-standard/sura-guides/) | 11ஆம் வகுப்பு Guide பட்டியல் | PDF Download / Medium சரிபார்ப்பு |
| KalviMani — Class 12 | [12th Sura Guides](https://kalvimani.in/12th-standard/sura-guides/) | 12ஆம் வகுப்பு Guide பட்டியல் | Subject / Stream / Medium சரிபார்ப்பு |
| **Kalvi Kadal** | [Site Map](https://www.kalvikadal.in/p/sitemap.html) | 9th–12th Guide PDF, Question Paper, Answer Keys, Materials | சில Page-கள் பழைய தேதியுடன் இருக்கலாம்; உள்ளே உள்ள PDF Link-ஐச் சரிபார்க்க வேண்டும் |
| **Tamilaruvi** | [6th–12th All Subject Full Guides](https://www.tamilaruvi.in/p/6th-to-12th-all-subject-full-study.html) | 6–12க்கு Sura, Don, Way to Success, Selection, Penguin, Brilliants, EC Loyola போன்ற Publisher Guides | 2026–27 என்று பட்டியல் கூறுகிறது; PDF Edition / Medium / Page சரிபார்க்க வேண்டும் |
| Tamilaruvi — Class 10 | [10th All Subject Full Guides](https://www.tamilaruvi.in/p/10th-all-subject-full-study-guide.html) | 10ஆம் வகுப்பு பல Publisher Guide-கள் | சில PDF-கள் மூன்றாம் தரப்பு Upload / Mirror; Origin அறிய வேண்டும் |
| Tamilaruvi — Class 11 | [11th Full Guide Collection](https://www.tamilaruvi.in/2022/08/11th-standard-all-subjects-full-study-guides-collection-tamil-medium-and-english-medium-download-pdf.html) | 11ஆம் வகுப்பு பாடங்கள், TM/EM, பல Publishers | பழைய URL; தற்போதைய Download Links தனியாகச் சரிபார்க்க வேண்டும் |
| Tamilaruvi — 2024–25 Collection | [6th–12th 2024–25 Guide List](https://www.tamilaruvi.in/2024/07/tamilnadu-schools-notes-guides-all-subjects-pdf-download-6th-to-12th-all-subjects-full-study-guides-notes-2024-2025.html) | பழைய Editions-ஐ ஒப்பிடவும் | 2026–27 Answer Source ஆக நேரடியாகப் பயன்படுத்த வேண்டாம் |
| **NCERTBooksPDF** | [Tamil Nadu Textbook PDF Index](https://ncertbookspdf.com/tamilnadu-samacheer-kalvi-books/) | 2026–27 Textbook PDF Class 1–12 TM/EM Index | Textbook Source மட்டுமே; Guide Answer Source என்று கருத வேண்டாம் |

### C. Professional Guide Publishers

இவை Publisher / Guide பெயர்கள். ஒவ்வொரு Publisher-ன் முழு PDF இலவசமாகக் கிடைக்கிறது என்று அர்த்தமில்லை.

| Publisher / Guide | எங்கு காணப்பட்டது | Coverage Candidate | சரிபார்க்க வேண்டியது |
|---|---|---|---|
| **Sura Publications** | [Official 2026–27 School Guides](https://www.surabooks.com/collections/school-guides-2026-27) | 6–12; பல Subjects மற்றும் TM/EM | Official Catalogue / Paid Guide / Sample PDF; முழு இலவச PDF என்று கருதக்கூடாது |
| **Ganga Publications** | SamacheerKalviStudents, KalviMani, Tamilaruvi Index-கள் | Primary முதல் Higher Classes வரை | Class / Term / Medium PDF உறுதி |
| **Way to Success** | Tamilaruvi, KalviMani Index-கள் | Middle / High / Higher Secondary | Edition மற்றும் PDF முழுமை |
| **EC Loyola** | Tamilaruvi, KalviKadal, KalviMani | 6–12 Guide Candidates | Sample vs Full Guide பிரிக்க வேண்டும் |
| **Don Publications** | Tamilaruvi மற்றும் பிற Index-கள் | 6–12 Guide Candidates | Edition / Subject / Medium |
| **Selection** | Tamilaruvi / பிற Index-கள் | 6–10 Guide Candidates | Subject / Medium |
| **Penguin** | Tamilaruvi | 6–12 Guide Candidates | Edition / PDF முழுமை |
| **Brilliants / Brilliant** | Tamilaruvi | 6–12 Guide Candidates | Publisher / PDF Origin உறுதி |
| **Dolphin** | Tamilaruvi | 9–12 Guide Candidates | Subject-wise PDF |
| **Diamond, Kavin, KSJ, Nithish, Rasi, Kavimani, Surya, Roots** | Tamilaruvi / பிற Guide Index-கள் | குறிப்பிட்ட Class / Subject / Edition-களில் கூடுதல் Reference | ஒவ்வொன்றையும் தனியாகச் சோதிக்க வேண்டும் |

### D. Play Store Apps — App Source Candidates

| App | Google Play Link | Listing-ல் கூறப்படும் Coverage | பயன்பாடு / வரம்பு |
|---|---|---|---|
| **TN School App — BrainKart** | [Play Store](https://play.google.com/store/apps/details?id=in.brainkart.tnschool) | Class 1–12; TM/EM; Book Back Answers, Solutions, Notes, Question Papers | 10K+ Downloads என்று Play Store காட்டியது. Public Listing பார்க்க முடியும்; App-க்குள் உள்ள ஒவ்வொரு Answer-யும் Browser-ல் நேரடியாக ஆய்வு செய்ய முடியாது |
| **TN TextBooks: Samacheer Kalvi — VirkozKalvi** | [Play Store](https://play.google.com/store/apps/details?id=com.virkoz.tntextbooks) | Class 1–12 Textbooks, Book Back Solutions, TM/EM என்று கூறுகிறது | 10K+ Downloads. Ads / In-App Purchases உள்ளது; Developer தன்னை Independent Initiative என்று குறிப்பிடுகிறது |
| **TN 12th Guide (All sub)** | [Play Store](https://play.google.com/store/apps/details?id=com.samacheerkalvi.tn12thguide) | Class 12; TM/EM; Book Back, Detailed Explanations, Long Answers | 1K+ Downloads; 12ஆம் வகுப்புக்கான Supplementary Candidate |
| **Padi App: TN Samacheer Kalvi** | [Play Store](https://play.google.com/store/apps/details?id=com.tndigitalapps.padi_app) | Public Listing-ல் Class 10 மற்றும் 12 பகுதிகள், TM/EM, Book Back / Board Questions / MCQ Practice | 1–12 முழு Answer Source என்று கருத வேண்டாம்; குறிப்பிட்ட Class / Subject மட்டும் சோதிக்கவும் |

**App Access Limitation:** Public Google Play Listing, App Description, Downloads, Ratings / Reviews போன்றவற்றைப் பார்க்க முடியும். ஆனால் Play Store-லிருந்து App-ஐ நிறுவி Login செய்து உள்ளே உள்ள ஒவ்வொரு பாடம் / Answer-ஐ நேரடியாகத் திறந்து ஆய்வு செய்ய முடியாது. App Content Public Website / PDF-ல் கிடைத்தால் அதைத் தனியாக ஆய்வு செய்யலாம். இல்லையெனில் User வழங்கும் Export / PDF / Screenshot போன்ற அணுகக்கூடிய Reference தேவைப்படும்.

### E. Official Textbook / Syllabus Verification

| Official Source | Link | பயன்பாடு |
|---|---|---|
| Tamil Nadu Textbook and Educational Services Corporation | [textbookcorp.in](https://www.textbookcorp.in/) | Official Textbook Release / Term / Academic Year / Edition அறிவிப்புகள் |
| Official Textbook Sales / School Page | [textbookcorp.in/schools](https://textbookcorp.in/schools) | எந்த Class-க்கு எந்த Academic Year / Medium / Term புத்தகம் வெளியானது என்பதைச் சரிபார்க்க |
| SCERT Textbook Index (Secondary Index) | [NCERTBooksPDF Tamil Nadu Index](https://ncertbookspdf.com/tamilnadu-samacheer-kalvi-books/) | PDF Reference; Official Announcement-உடன் ஒப்பிட வேண்டும் |

Official Textbook Source தான் Edition / Term சரிபார்ப்புக்கான முதன்மை Reference. Guide Website-ல் இருக்கும் பழைய PDF-ஐ தற்போதைய புத்தகத்திற்குச் சரியானது என்று தானாக ஏற்றுக்கொள்ளக்கூடாது.

---

### F. Class 10 Tamil — 2026–27 Publisher Guide availability check (05-11-2026)

| Publisher | Direct listing | சரிபார்க்கப்பட்ட தகவல் | நிலை |
|---|---|---|---|
| **SURA Publications** | [SURA'S 10th Standard Tamil Urainool Guide — 2026–27](https://www.surabooks.com/Books/307923/www.surabooks.com) | 2026–27 Low Priced Edition / Tamil guide listing | `GUIDE_PRODUCT_PAGE_ONLY` — listing மட்டும்; இலவச PDF அல்லது இந்த இயலின் answer pages உறுதிப்படுத்தப்படவில்லை |
| **DON Publications** | [DON 10th Tamil Guide — 2026–27 listing](https://routemybook.com/publisher_details/Don-Publications-27?autshort=pop) | New Syllabus 2026–27 Tamil guide product listing | `RETAILER_PRODUCT_PAGE_ONLY` — விற்பனை விவரம் மட்டும்; இலவச PDF அல்லது answer page உறுதிப்படுத்தப்படவில்லை |

**Guide PDF முடிவு:** SURA / DON Guide பெயர் மற்றும் 2026–27 listing கண்டறியப்பட்டுள்ளன. இந்தப் பணி செய்யப்பட்ட நாளில் அவற்றின் முழு இலவச PDF மற்றும் Iyal 1-க்கான குறிப்பிட்ட PDF page-ஐ திறந்து verify செய்ய முடியவில்லை. எனவே இவற்றை தற்போதைக்கு answer source என்று எண்ணக்கூடாது. பின்னர் உண்மையான PDF கிடைத்தால் PDF page number உடன் மட்டுமே source record-ஆக உயர்த்தலாம்.

## 7. Source Quality, Popularity மற்றும் Reliability மதிப்பீடு

ஒரு Website பிரபலமானது என்பதால் அதிலுள்ள எல்லா Answers-யும் சரியானவை என்று கருதக்கூடாது.

| அளவுகோல் | சரிபார்க்க வேண்டியது |
|---|---|
| Coverage | 1–12 வகுப்புகள் முழுவதும் உள்ளதா? எந்த Class / Subject விடுபட்டுள்ளது? |
| Medium | TM மற்றும் EM இரண்டும் உள்ளனவா? |
| Term | Primary Classes-ல் Term 1 / 2 / 3 அனைத்தும் உள்ளனவா? |
| Edition | 2026–27 அல்லது தேவையான Academic Year-க்கு பொருந்துகிறதா? |
| Direct Access | குறிப்பிட்ட பாடம் / கேள்விக்கான Page அல்லது PDF நேரடியாகத் திறக்கிறதா? |
| Completeness | Short Answers மட்டும் தானா? Long Answers மற்றும் அனைத்து Exercises உள்ளனவா? |
| Source Origin | Publisher / ஆசிரியர் / ஆசிரியர் குழு யார்? Mirror Copy தானா? |
| Consistency | பல பாடங்களிலும் ஒரே மாதிரியான Answer Quality உள்ளதா? |
| Popularity Signal | Play Store Downloads / Reviews, Website Traffic Estimate போன்ற ஆதாரம் உள்ளதா? |
| Availability | Free, Sample-only, Paid, Login அல்லது App-only ஆக உள்ளதா? |

### இப்போது தெரிந்த Popularity Signals

- TN School App — Play Store-ல் 10K+ Downloads.
- TN TextBooks: Samacheer Kalvi — Play Store-ல் 10K+ Downloads.
- TN 12th Guide — Play Store-ல் 1K+ Downloads.

இவை Play Store Listing-ல் தெரிந்த Signals மட்டுமே. மாணவர்களின் உண்மையான பயன்பாடு, Review Quality அல்லது Answer Accuracy-க்கு முழு சான்று அல்ல. Website Traffic / Reviews கிடைத்தால் தேதி மற்றும் Data Provider உடன் பதிவு செய்ய வேண்டும். ஆதாரமில்லாமல் ஒரு தளத்தை “மிகவும் பிரபலமானது” என்று வகைப்படுத்தக்கூடாது.

---

## 8. முழுமையான Coverage Audit — அடுத்த கட்டத்தின் முக்கியப் பணி

ஒரு Website “1–12 All Subjects” என்று கூறினாலும், ஒவ்வொரு பாடத்திலும் முழு Answer இருப்பது உறுதியல்ல. எனவே Class × Subject × Medium × Term × Chapter அடிப்படையில் Audit செய்ய வேண்டும்.

### ஒவ்வொரு Book / Chapter-க்கும் பதிவு செய்ய வேண்டியவை

- Class: 1–12
- Subject
- Medium: TM / EM
- Academic Year
- Term: 1 / 2 / 3 / Annual
- Textbook Edition
- Chapter Number & Name
- questions.md உள்ளது / இல்லை
- PDF Reference உள்ளது / இல்லை
- PDF Page / Chapter Cross-check Status
- Source Website / Guide / App
- Direct Page / PDF Link
- Answer Found / Not Found
- Answer Completeness
- Source Version
- Verification Date

### Source Status Values

| Status | பொருள் |
|---|---|
| INDEX_FOUND | Website / Index Page கிடைத்தது; Answer சரிபார்க்கப்படவில்லை |
| PAGE_FOUND | குறிப்பிட்ட பாடத்தின் Direct Page கிடைத்தது |
| ANSWER_FOUND | அந்தப் பக்கத்தில் குறிப்பிட்ட கேள்விக்கான பதில் உள்ளது |
| PDF_FOUND | Guide PDF திறக்கப்பட்டது |
| PDF_PAGE_VERIFIED | குறிப்பிட்ட Answer PDF-ல் குறிப்பிட்ட Page-ல் சரிபார்க்கப்பட்டது |
| PARTIAL | சில கேள்விகளுக்கு மட்டுமே Answer உள்ளது |
| WRONG_EDITION | தற்போதைய Textbook-க்கு பொருந்தாத பழைய Edition |
| WRONG_MEDIUM | தேவைப்பட்ட TM / EM அல்ல |
| BROKEN_LINK | Link திறக்கவில்லை |
| APP_ONLY | App உள்ளே மட்டுமே உள்ளது; Public Page / PDF உறுதிப்படுத்தப்படவில்லை |
| NO_ANSWER_ON_PAGE | Page திறந்தது; ஆனால் அந்தக் கேள்விக்கான Answer இல்லை |
| ANSWER_NOT_FOUND | தேடலுக்குப் பிறகும் Answer கிடைக்கவில்லை |
| CONFLICT | இரண்டு அல்லது அதற்கு மேற்பட்ட Sources வேறுபட்ட Answers தருகின்றன |
| VERIFIED_FOR_CURRENT_EDITION | தற்போதைய சரியான Edition-க்கு பொருந்துவது உறுதி செய்யப்பட்டது |

### Coverage கணக்கிடும் முறை

உதாரணமாக ஒரு Website 10ஆம் வகுப்பு தமிழ் பாடத்தின் 20 Questions-ல் 15-க்கு மட்டும் பதில் கொடுத்திருந்தால்:

- Total Questions: 20
- Answer Found: 15
- Missing: 5
- Coverage: 75%

ஒரு பாடத்திற்கான Coverage-ஐ முழு வகுப்பின் Coverage என்று தவறாகக் கூறக்கூடாது. Class / Subject / Medium / Term / Chapter அடிப்படையில் கணக்கிட வேண்டும்.

---

## 9. Academic Year / Textbook Edition கவனம்

2026–27 Academic Year-க்கு Class மற்றும் Term அடிப்படையில் Textbook மாற்றங்கள் இருக்கலாம். குறிப்பாக Primary Classes-ல் Term-wise Books இருப்பதால் Edition தவறினால் Answer மாறக்கூடும்.

[Official Textbook Corporation](https://www.textbookcorp.in/) வெளியிட்டுள்ள 2026–27 அறிவிப்புகளில்:

- 1–3 வகுப்புகளுக்கான Term 1 புத்தகங்கள் 25-05-2026 முதல் கிடைக்கும் என்று அறிவிக்கப்பட்டது.
- 1–7 வகுப்புகளுக்கான Term 2 புத்தகங்கள் 22-09-2026 முதல் கிடைக்கும் என்று அறிவிக்கப்பட்டது.
- 4–7 வகுப்புகளுக்கான Term 1 மற்றும் 8ஆம் வகுப்பு Annual Textbooks உள்ளிட்டவை 14-05-2026 முதல் கிடைக்கும் என்று அறிவிக்கப்பட்டது.
- 2025–26-ல் அச்சிடப்பட்ட Classes 1–3 Term 1 புத்தகங்கள் தற்போது நடைமுறையில் இல்லாத பழைய பதிப்புகள் என்று Official Site குறிப்பிடுகிறது.

ஒவ்வொரு Source-க்கும் Edition Match கட்டாயம். பழைய Guide-ல் Answer கிடைத்தாலும் அது தற்போதைய Book Question-க்கு பொருந்துகிறதா என்று questions.md மற்றும் PDF Page மூலம் உறுதிப்படுத்த வேண்டும்.

---

## 10. Temporary Working Space, Source Use மற்றும் Copyright

### 10.1 GitHub-ன் பங்கு
GitHub பல AI/கருவிகள் ஒரே working materials-ஐப் பகிர்ந்து கொள்ளும் temporary common workspace. இது TN EXAM GURU மாணவர் Website-ன் public answer publishing destination அல்ல. Working branch-ஐ deploy செய்யக்கூடாது; main-க்கு merge செய்யக்கூடாது; user சொன்ன பிறகே web deployment தொடர்பான தனிப் பணி செய்ய முடியும்.

User தேவையான files/data-ஐ எடுத்துக்கொண்ட பிறகு cleanup-ஐ அவரே செய்வார். Assistant branches/files-ஐ தானாக delete செய்யக்கூடாது.

### 10.2 Source reference vs student answer
answers.md என்பது Source Index. Non-objective விடைகள் மூன்று tiers-ஆக பின்னர் user-ன் தனி workflow-ல் உருவாக்கப்படலாம்; அவை இக்கட்டத்தில் நிரப்பப்படாது. Objective வினாக்களுக்கு source-ல் காணப்பட்ட குறுகிய answer code/text மட்டும் காட்டப்படும். Source-களை இணைத்து ஒரே "ChatGPT answer" உருவாக்குவது தடை.

### 10.3 Source text handling
Short option/one-word values-ஐக் குறுகிய அளவில் பதிவு செய்யலாம். நீண்ட third-party Guide/Website விடைகளை முழுவதுமாக மீளெழுதாமல் direct page/PDF link மற்றும் page/section விவரத்தை மட்டும் கொடு. Summary-ஐ verbatim என்று காட்டக்கூடாது. Source-ன் முழு உரையை இந்த output-ல் தரவேண்டும் என்ற நிலை வந்தால், அதற்குப் பதிலாக user தானாகத் திறக்க வேண்டிய direct link-ஐத் தா.

### 10.4 Guide access clarity
Guide புத்தகத்தின் பெயர் அல்லது விற்பனைப் பக்கம் மட்டும் கிடைத்தால் அது answer source அல்ல. PDF-ஐ உண்மையில் திறந்து, கேள்விக்கான பதில் இருக்கும் page number-ஐச் சரிபார்த்த பிறகே PDF_ANSWER_VERIFIED எனக் குறிக்கலாம்.

## 11. Error Prevention / Quality Control

| பொதுவான பிழை | கட்டாயத் தடுப்பு |
|---|---|
| Assistant சொந்தமாக விடை எழுதுதல் | Non-objective-க்கு links + placeholders மட்டும் |
| பல website answer-களை ஒன்றாக்குதல் | ஒவ்வொரு source தனித்தனி record |
| Source-ல் இல்லாத answer-ஐ அந்தத் தளத்துக்கு உரிமை கூறுதல் | direct page open செய்து answer இருப்பதை உறுதி செய் |
| Search snippet-ஐ source proof என எடுத்துக்கொள்ளுதல் | original answer page திறக்கப்பட வேண்டும் |
| காரண விளக்கம் ஊகித்து எழுதுதல் | பாடநூல் / இலக்கணம் / பொருள் விளக்க source ஆகியவற்றில் பொருத்தமான ஆதாரம் தேடு; ஆதாரம் இல்லையெனில் EXPLANATION_SOURCE_NOT_FOUND |
| பொதுப் பொருள் வினாவுக்கு காரண விளக்கத்தைத் தவிர்த்தல் | பாடநூல் / கருத்து / வகைப்பாடு source-ல் விளக்கம் உள்ளதா தேடு; ஆதாரம் இல்லையெனில் EXPLANATION_SOURCE_NOT_FOUND |
| வேறுபட்ட source answers-ல் ஒன்றை மறைத்தல் | எல்லா variants-ஐ பதிவு செய்து CONFLICT |
| Source question பழைய/வேறுபட்ட edition | WORDING_VARIANT / QUESTION_MISMATCH |
| Guide product page-ஐ PDF எனக் கருதுதல் | GUIDE_PRODUCT_PAGE_ONLY |
| PDF page number ஊகித்தல் | PDF_PAGE_NOT_VERIFIED |
| Original question-ஐப் பொருத்தமாக மாற்றுதல் | questions.md read-only |
| பழைய AI-generated answer draft-ஐ தொடர்தல் | முழு answers.md source-index ஆகவே மாற்றப்பட வேண்டும் |

## 12. End-to-End Work Plan

| கட்டம் | பணி | Output |
|---|---|---|
| 1 | சரியான textbook edition / questions inventory உறுதி | Version/source audit |
| 2 | questions.md-இல் உள்ள கேள்விகளின் exact wording/order பதிவு | read-only question inventory |
| 3 | ஒவ்வொரு கேள்விக்கும் relevant website/guide search | source candidate list |
| 4 | ஒவ்வொரு direct answer page/PDF-ஐ திறந்து verify | question-wise source records |
| 5 | Objective answers மட்டும் source-wise குறுகிய பதிவு | option + answer text + source |
| 6 | Grammar-specific objective என்றால் actual grammar rule source தேடுதல் | reason + direct grammar citation |
| 7 | Non-objective கேள்விகளுக்கு மூன்று empty placeholders அமைத்தல் | no answer written |
| 8 | Conflict, mismatch, blocked links ஆகியவற்றைச் சுட்டுதல் | QC status table |
| 9 | இறுதி link/filename/branch verification | handoff links |
| 10 | User later source comparison and answer authoring | Assistant இக்கட்டத்தில் செய்யாது |

## 13. அடுத்ததாக செய்ய வேண்டியவை

1. Current chapter-இன் questions.md மற்றும் book edition status-ஐ மாற்றமின்றி reference ஆக வைத்துக் கொள்ளுதல்.
2. answers.md-ல் ஒவ்வொரு கேள்விக்கும் verified direct source links கிடைத்ததா எனக் கண்காணித்தல்.
3. K5, wording variants, MCQ conflicts போன்ற open QC-ஐ உரிய original page / edition-உடன் ஒப்பிடுதல்.
4. SURA / DON Guide-களின் சரியான edition மற்றும் கிடைக்கக்கூடிய PDF இருப்பதைத் தனியாக verify செய்தல்.
5. User-ன் அடுத்த அறிவுறுத்தல் இல்லாமல் model answers எழுதத் தொடங்கக்கூடாது.
6. User தேவையான content எடுத்துக்கொள்ளும் வரை working files-ஐ வைத்திருக்க வேண்டும்; delete/merge/deploy செய்யக்கூடாது.

## 14. Quick Handover Summary — புதிய Chat / Antigravity / மற்ற AI-க்காக

**Role:** Source finder and verifier. Non-objective answer writer அல்ல.

**Question authority:** Existing questions.md; exact wording/order preserve.

**Non-objective output:** 🔑 விடைக்குறிப்பு, 📝 சாதாரண விடை, 📖 விரிவான விடை — மூன்றும் [TO_BE_PREPARED_LATER]; அதன் கீழ் எல்லா direct source links மட்டும்.

**Objective output:** Source-ல் உண்மையில் காணப்பட்ட option code + short answer, source-wise. ஒவ்வொரு one-mark வினாவுக்கும் கேள்விக்கு ஏற்ற grammar / textbook / subject-matter காரண விளக்கம் மற்றும் direct supporting URL.

**Sources:** 3/5 count cap கிடையாது. உண்மையில் சரிபார்க்கப்பட்ட எல்லா relevant pages/PDFs-ஐ சேர்க்கவும். Product page ≠ Guide PDF.

**Never:** Non-objective own model answer, paraphrase as source text, source merge, unsupported answer, question wording alteration, பெரிய வினாவிலிருந்து புதிய one-word வினா உருவாக்குதல், deploy, merge to main, delete.

**Current chapter:** Class 10 Tamil — Iyal 1, tamil/01_mozhi_amuthaootru/book_back_questions/.

## 15. Execution Protocol — ஒவ்வொரு Subject / Chapter-க்கும்

### 15.1 Edition Gate
- Official textbook / user-supplied current book / repo PDF ஆகியவற்றின் edition details cross-check செய்ய வேண்டும்.
- Old guide page-ல் கேள்வி இருப்பதால் மட்டும் அது current question-க்கு exact answer source என்று கருதக்கூடாது.
- Edition mismatch இருந்தால் அது visible QC status ஆக இருக்க வேண்டும்.

### 15.2 Source collection
- கேள்வி வாரியாக web search செய்; search-result snippet-ஐ final proof ஆகப் பயன்படுத்தாதே.
- Direct answer page/PDF திறந்து question/answer location சரிபார்.
- Source count cap இல்லாமல் உண்மையில் கிடைத்த எல்லா relevant sources-ஐ பதிவு செய்.
- Source title, date, edition, PDF page number, question match ஆகியவை கிடைத்தால் சேர்க்கவும்.

### 15.3 Objective answer
- ஒவ்வொரு source கூறும் option code + short answer மட்டும்.
- Conflict இருந்தால் ஒவ்வொன்றும் தனித்தனி.
- ஒவ்வொரு one-mark / one-word வினாவுக்கும் பொருத்தமான காரண விளக்கம் தேடு; இலக்கணம், பாடநூல், சொற்பொருள், பாடப்பொருள் அல்லது பொதுத் தகவல் எனப் பொருத்தமான ஆதார URL கட்டாயம்.

### 15.4 Non-objective answer
- மூன்று placeholder-களையும் காலியாக வை.
- Source link, source title, page/section/PDF page மட்டும்.
- Source answer text copy, paraphrase அல்லது own answer எதுவும் வேண்டாம்.

### 15.5 Chapter completion
- எல்லா கேள்விகளும் source link அல்லது explicit missing/access/mismatch status பெற வேண்டும்.
- Non-objective placeholders நிரப்பப்படாமல் இருக்க வேண்டும்.
- questions.md, quiz files, book PDFs, routing files மாற்றப்படக்கூடாது.
- User பின்னர் தன் ஒப்பீடு/எழுத்துப்பணியைத் தொடங்குவார்; assistant அதற்காக answer tiers-ஐ முன்கூட்டியே நிரப்பக்கூடாது.

## 15.6 Class 10 முழு Coverage — Batch Execution Plan

Class 10-ன் அனைத்து பாடங்களையும் ஒரே பெரிய extraction run-ல் முடிப்பதை விட, ஒரே நிலையான விதிமுறையுடன் subject-wise சிறிய batch-களாகச் செய்வதே சரியான நடைமுறை. இதனால் source mismatch, தவறான edition, answer conflict, JSON field error ஆகியவை ஆரம்பத்திலேயே கண்டுபிடிக்கப்படும்.

### கட்டாய வேலை வரிசை

1. **முழு inventory முதலில்:** Class 10-ல் உள்ள ஒவ்வொரு subject, medium, textbook edition, book, chapter/lesson, Book Back question count ஆகியவற்றின் பட்டியலை உருவாக்கு. Edition verification முடியும் வரை current answer extraction தொடங்க வேண்டாம்.
2. **Subject-wise செயல்:** ஒரே நேரத்தில் ஒரு subject மட்டும். தமிழ், ஆங்கிலம், கணிதம், அறிவியல், சமூக அறிவியல் போன்ற பாடங்களை ஒன்றாகக் கலந்து ஒரே batch செய்ய வேண்டாம்.
3. **ஒவ்வொரு batch-லும் 2–3 chapters:** source search, direct page verification, answer conflict review, explanation source verification ஆகியவற்றை 2–3 chapters முடிந்ததும் QC செய்ய வேண்டும். Chapter/Unit மிகப்பெரியதாக இருந்தால் அதை ஒரு தனி batch ஆகப் பிரிக்கலாம்.
4. **ஒரே Book Back தொகுப்பு பல பாடங்களை உள்ளடக்கியிருந்தால்:** அது ஒரு integrated unit ஆகவே கையாளப்பட வேண்டும். கேள்வி எந்த lesson-க்கு சேர்ந்தது எனப் பிரிக்க முடியாவிட்டால் ஊகித்து பிரிக்க வேண்டாம்.
5. **Answer Source முதலில்:** அந்த batch-ன் எல்லா கேள்விகளுக்கும் source records, objective correct answers, one-mark reasons, non-objective placeholders முடிக்கப்பட வேண்டும்.
6. **Quiz Start அடுத்த கட்டம்:** Antigravity உறுதிசெய்த schema-க்கு ஏற்ப, அந்த batch-ன் verified one-mark questions-ஐ மட்டும் quiz.start.md/json-ல் உருவாக்க வேண்டும்.
7. **Batch QC:** question count, source links, explanation citations, conflict status, JSON validity, duplicate IDs, original question wording ஆகியவை சரிபார்க்கப்பட்ட பிறகே அடுத்த batch தொடங்க வேண்டும்.
8. **Subject completion:** அந்த subject-ன் எல்லா chapters-ம் முடிந்த பிறகு subject-level coverage summary உருவாக்கு; பின்னர் அடுத்த subject-க்கு நகரு.
9. **Class completion:** எல்லா subjects-ம் முடிந்த பிறகு மட்டுமே Class 10 consolidated coverage audit செய்ய வேண்டும்.

**முடிவு:** முழு Class 10-ஐ திட்டமிட்டு ஒரே project-ஆகக் கையாளலாம்; ஆனால் extraction மற்றும் quiz data generation 2–3 chapter batch-களாக, subject-wise நடைபெறும். இது வேலை அளவைச் சிறிதாக்குவதற்காக அல்ல; ஒவ்வொரு answer/source/quiz entry-யும் traceable மற்றும் சரிபார்க்கக்கூடியதாக இருக்கவே.

## 16. Current Audit Finding — Class 10 Tamil Book Version (Provisional Warning)

**Repository:** [Eaglesiva/tn-class-10](https://github.com/Eaglesiva/tn-class-10)

GitHub Tree Audit-ல் Tamil Subject-க்கான PDF Page Files:
- tamil/00_prelims/page_001.pdf முதல் page_010.pdf
- பாட அத்தியாயங்களின் கீழ் தொடர்ச்சியாக page_011.pdf முதல் page_248.pdf
- மொத்தம்: **248 individual one-page PDF files**.

### 16.1 வெளிப்புற புத்தகப் பதிப்பு ஒப்பீடு

- FreeTNBooks 10ஆம் வகுப்பு புத்தகப் பக்கம் 2024 Tamil PDF மற்றும் தனியாக “New” 2025 Tamil PDF என இரண்டு பதிவுகளை வேறுபடுத்துகிறது. 2025 Edition Tamil புத்தகம் வெளியிடப்பட்டதாகவும் அந்தப் பக்கம் குறிப்பிடுகிறது: [10th Standard Books](https://www.freetnbooks.com/10th-standard-books/).
- மற்றொரு 2026 textbook index 2025 10th Tamil book-ஐ 184 pages என்றும் 2024 Tamil book-ஐ 248 pages என்றும் வேறுபடுத்துகிறது: [Class 10 Tamil Book 2026 listing](https://cbsetamil.com/ncert-tamil-book-for-class-10-pdf/).
- Tamil Nadu Textbook and Educational Services Corporation 2026–27 Class 10 Annual Textbooks விற்பனை 10-04-2026 முதல் தொடங்கியதாக அறிவித்துள்ளது: [Official Textbook Corporation](https://textbookcorp.in/schools).
- 2026–27-ல் Classes 4–12 பழைய syllabus-ஐத் தொடரும் என்றும் புதிய curriculum 2027–28-ல் அமல்படுத்தப்படுமென்றும் செய்தி அறிக்கைகள் தெரிவிக்கின்றன: [DT Next — Classes 4–12 textbook work](https://www.dtnext.in/news/tamilnadu/teachers-continue-with-classes-4-12-textbook-work-despite-new-regime-uncertainty), [New Indian Express — draft curriculum](https://www.newindianexpress.com/states/tamil-nadu/2026/Aug/21/tn-revamps-syllabus-for-class-6-10-with-emphasis-on-critical-thinking).

### 16.2 தற்போதைய நிலை / தீர்மானம்

Repo-வில் உள்ள 248 page sequence, வெளியிடப்பட்ட 2024 Edition 248-page தகவலுடன் பொருந்துகிறது. 2025 Revised Tamil Edition 184 pages என்று மற்றொரு Source காட்டுகிறது. எனவே Repo-வில் உள்ள 248-page copy **2024 Edition ஆக இருக்கக்கூடிய வலுவான சாத்தியம் உள்ளது**.

ஆனால் PDF Cover / Imprint / Edition Page-ஐ நேரடியாகப் படித்து, 2025 copy-யுடன் page-level content comparison முடிக்காமல் இதை 100% உறுதிப்படுத்தக்கூடாது.

**தற்காலிக முடிவு:** தற்போதைய Repo PDF-ஐ 2026–27-க்கான Verified Current Edition என்று குறிக்க வேண்டாம். 2025 Revised Tamil PDF (அல்லது 2026–27 official reprint) கிடைத்து அதன் title page, revision imprint, TOC, lesson pages மற்றும் Book Back Questions ஒப்பிடப்படும் வரை Quiz Finalization-ஐ நிறுத்த வேண்டும்.

### 16.3 Class 10 Tamil — முதற்கட்ட Answer Source Candidate

[BrainKart — 10th Tamil, இயல் 1: அமுத ஊற்று — Questions & Answers](https://www.brainkart.in/article/Questions-and-Answers_11807/)

இந்தப் பக்கம் இயல் 1-க்கான Objective, குறுவினா, சிறுவினா, நெடுவினா வகை உள்ளடக்கங்களை வழங்குகிறது. அதே பாடத்திற்கான Subject Index-ல் பிற இயல்களுக்கும் தனிப்பட்ட Questions & Answers பதிவுகள் உள்ளன: [BrainKart 10th Tamil Subject Index](https://www.brainkart.in/subject/Tamil-10th-Std_396).

இது Round 1 Source Candidate மட்டுமே; பக்கம் 2022-ல் வெளியிடப்பட்டது. Current 2026–27 Textbook-உடன் ஒவ்வொரு கேள்வியும் பொருந்துகிறதா என்பதைக் கட்டாயம் சரிபார்க்க வேண்டும். இந்த Source-ல் இல்லாத கேள்விகளுக்கு பதில் உள்ளது என்று கருதக்கூடாது.

### 16.4 Existing Class 10 Tamil Unit 1 File Cross-check Note

தற்போதைய Repository-ல்:
- [questions.md — Unit 1](https://github.com/Eaglesiva/tn-class-10/blob/main/tamil/01_mozhi_amuthaootru/book_back_questions/questions.md)
- [quiz.md — Unit 1](https://github.com/Eaglesiva/tn-class-10/blob/main/tamil/01_mozhi_amuthaootru/book_back_questions/quiz.md)

இரண்டிலும் சில சொல் / Option வேறுபாடுகள் உள்ளன. உதாரணமாக:
- questions.md-ல் “எந்தமிழ்நா”; quiz.md-ல் “எண்தமிழ்நா” என்று உள்ளது.
- ஒரு கேள்வியின் பெயர்/சொல் மற்றும் சில Options-ன் wording / ordering மாறுபடுகின்றன.

இவை எது சரி என்று இப்போது தீர்மானிக்கக்கூடாது. சரியான 2026–27 Textbook Page-ஐப் பார்த்தே உறுதி செய்ய வேண்டும். தற்போதைய quiz.md-ன் **format**-ஐ மட்டும் Reference-ஆகப் பயன்படுத்தலாம்; அதில் உள்ள Question Content-ஐ Verified என்று கருதக்கூடாது.

மேலும் questions.md-ல் உள்ள file:///e:/... போன்ற Local Computer Links மற்ற AI-க்கு அணுக முடியாது. Cross-check முடிந்தபின் அவற்றை Repository-relative link அல்லது GitHub Page Link-ஆக மாற்ற வேண்டும்.

---

## 17. புதிய Chat / AI-க்கு உடனடி அடுத்த செயல் — Source-only workflow

1. அந்த chapter-ன் questions.md-ஐ வாசித்து exact wording/order-ஐ அப்படியே எடுத்துக்கொள்.
2. ஒவ்வொரு வினாவுக்கும் direct answer websites மற்றும் relevant publisher guide sources தேடு.
3. Direct page/PDF-ல் exact question மற்றும் answer presence-ஐ verify செய்; homepage/snippet போதாது.
4. Objective வினாக்களுக்கு source-ல் காணப்பட்ட option code + short answer மட்டும் பதிவு செய்.
5. எல்லா one-mark objective வினாக்களுக்கும் பொருத்தமான ஆதார விளக்கம் தேடு; grammar / textbook / subject-matter / general வகையைத் தேர்ந்து direct source link கொடு.
6. Non-objective வினாக்களுக்கு மூன்று காலி placeholders மற்றும் எல்லா verified direct source links மட்டும்.
7. Source conflict/mismatch/access block-ஐ மறைக்காமல் குறி.
8. questions.md, quiz files, PDF, site files மாற்றாதே. Deploy/merge/delete செய்யாதே.
9. User பின்னர் sources-ஐ ஒப்பிட்டு தன் சொந்த மூன்று-tier answer-ஐ உருவாக்குவார்; இந்தக் கட்டத்தில் அது செய்யப்படாது.

## 18. User Clarification + Cloudflare / Current-Book Verification Update (03-11-2026)

### 18.1 User's authoritative rule for textbook version

The project must use the textbook that students are actually studying in the **current academic year (2026–27)**. Do not assume a future year's planned syllabus, draft curriculum or proposed new edition is relevant.

For each supplied book, verify whether it matches the currently used student copy. A book may retain an older First Edition year while having a newer Revised Edition / Reprint / Correction. Therefore:
- First Edition year alone does not identify the current version.
- Reprint year alone does not prove content changed.
- Revised Edition / correction information, textbook contents, chapter structure, question text, page count and official current-year distribution must be compared together.
- If the same book was reprinted with corrections, record the correction/revision evidence and verify affected pages.
- If a substantially revised book has a new page count / TOC / unit structure, treat it as a different content version until verified.

**The user's supplied current book is the primary reference for question wording and scope once it is confirmed to match the current student edition.** Answer Websites such as BrainKart may be older. They are answer sources only: do not make the current questions fit an older website. Use an old Answer Source only where the underlying question and textbook context actually match; otherwise mark it as a mismatch and look for another source.

### 18.2 Cloudflare Pages URL supplied by user

- User-provided site: [https://tn-class-10.pages.dev/](https://tn-class-10.pages.dev/)
- The site is understood to be the Cloudflare Pages deployment of the same Class 10 GitHub repository.
- Its page links are relative, for example:
  - `./viewer.html?pdf=./tamil/00_prelims/page_001.pdf`
  - `./tamil/00_prelims/page_001.pdf`
- During this audit, the browser/web retrieval layer returned “URL is not accessible via this tool” for both the Cloudflare root and direct PDF route. This is a tool-access limitation; it does **not** establish that the site is broken for ordinary browsers.
- GitHub Repository access is working. The GitHub connector can read text files such as `index.html`, `viewer.html`, `questions.md`, `quiz.md`, and the recursive file Tree. It can retrieve PDF file bytes as Base64, but this connector response does not itself render PDF pages visually.
- The current Cloudflare deployment is a useful alternate page-viewing route for a browser that can access it. If direct PDF rendering is unavailable in the assistant's tools, record that limitation honestly; do not claim to have visually inspected the page.

### 18.3 Class 10 Tamil — comparison evidence

**Repo / Cloudflare index evidence (GitHub API):**
- Repository: [Eaglesiva/tn-class-10](https://github.com/Eaglesiva/tn-class-10)
- [Class 10 index.html](https://github.com/Eaglesiva/tn-class-10/blob/main/index.html) describes the site as the Class 10 annual textbook edition / digitised printed pages.
- Its Tamil section reports **248 pages**.
- It lists 9 Tamil lesson folders / units:
  1. mozhi_amuthaootru
  2. iyarkai_kaetkiradhaa
  3. panpaadu_virundhu
  4. ariviyal_seyarkai_nunnarivu
  5. kalvi_mozhipeyarppu
  6. kalai_panmugak_kalaignar
  7. naagarigam_sirragal_oli
  8. aram_sangailakkiyam
  9. manidham_jeyakaandham
- The PDF page files are split one page per file from `tamil/00_prelims/page_001.pdf` onward, continuing through `page_248.pdf`.

**Publicly viewable 2025 Revised Tamil textbook evidence:**
- [10th Tamil new book 2025–2026 — TAMILVITHAI FlipHTML5](https://fliphtml5.com/bison/xbxt/10th_Tamil_new_book_2025_-_2026/)
- The publication view contains **184 pages** (pages P:01 through P:184).
- Its second printed page states: First Edition 2019; Revised Editions 2020, 2021, 2022, 2023, 2024 and 2025; SCERT / Tamil Nadu Textbook and Educational Services Corporation details are printed on the page.
- Its Contents pages show **7 iyals**, not 9:
  1. மொழி, மனிதம்
  2. இயற்கை, சுற்றுச்சூழல், அறிவியல்
  3. பண்பாடு
  4. கல்வி
  5. கலை, அழகியல், புதுமை
  6. நாகரிகம், நாடு, சமூகம்
  7. அறம், தத்துவம், சிந்தனை
- The book's first Iyal begins with the same broad title group “மொழி, மனிதம்”; its contents include “அன்னை மொழியே”, “அமுதஊற்று”, “தமிழ்ச்சொல் வளம்”, etc.
- Page 184 is present as the final page in the publication view.

**Current academic-year distribution evidence:**
- [Tamil Nadu Textbook and Educational Services Corporation — Schools](https://textbookcorp.in/schools) states that the 2026–27 annual Tamil textbooks for Classes 1–10 and the annual books for Classes 9, 10 and 12 (Tamil and English Medium) went on sale from 10-04-2026.
- [Padasalai Class 10 2026–27 textbook page](https://www.padasalai.net/2026/05/Tamilnadu-Class-10-Text-Books-PDF-Download-2026-2027.html) separately lists 2026–27 Class 10 Tamil Medium and English Medium textbooks for Tamil, English, Maths, Science and Social Science. This is an index / distribution source, not the Government publisher itself.
- [CBSE Tamil Class 10 textbook comparison page](https://cbsetamil.com/ncert-tamil-book-for-class-10-pdf/) labels the 2025 Class 10 Tamil book as 184 pages and the 2024 book as 248 pages, and describes the 2025 book as current for 2026–27. This is a secondary comparison source; use the printed book / official distribution evidence as the authority.

### 18.4 Provisional finding — do not use repo Tamil PDF as the current book yet

There is a **strong structural mismatch**:
- Repo Tamil: 248 pages and 9 lesson folders.
- Public 2025 Revised Tamil book: 184 pages and 7 iyals.

The 2025 book publication also displays the 2025 revised-edition imprint. Official textbook distribution confirms 2026–27 annual Tamil books for Classes 1–10 are in the current distribution cycle.

Therefore, the current Repo Tamil PDF is **likely an older 248-page version**, while the 2025 Revised 184-page textbook is the leading candidate for the current 2026–27 student edition.

This remains a **strong provisional finding**, not a final visual audit of the supplied Repo PDF: the assistant's web/browser layer could not open the Cloudflare PDF page, and the GitHub PDF connector returned binary Base64 rather than a visual page. Before marking the Repo copy definitively “old”, compare the actual PDF's cover / imprint / contents / selected page images against the 184-page revised copy or an official 2026–27 issued copy.

**Do not generate or finalize current-year Tamil quiz data using the 248-page Repo book until this mismatch is resolved.** Preserve it as a legacy reference if needed.

### 18.5 Unit 1 Question wording clue

The 2025 Revised 184-page publication's first Iyal text includes the printed form **“எந்தமிழ்நா”** in the poem / prose section. The current Repo `questions.md` uses “எந்தமிழ்நா”, while the existing `quiz.md` has “எண்தமிழ்நா” in one question. This supports checking the original current textbook before copying quiz wording. It does not make the existing quiz question verified.

### 18.6 Correct next actions for Class 10 Tamil — source-only

1. தற்போதைய 248-page / 9-Iyal Tamil book source மற்றும் அதன் edition audit result-ஐ reference ஆக வைத்துக் கொள்ளவும்.
2. questions.md-இல் உள்ள கேள்வி உரை மற்றும் inventory மாற்றமின்றி பயன்படுத்தப்பட வேண்டும்.
3. ஒவ்வொரு கேள்விக்கும் direct answer page / Guide PDF தேடித் திறந்து verify செய்யவும்.
4. Objective questions-க்கு source-ல் காணப்பட்ட option code + answer text; எல்லா one-mark வினாக்களுக்கும் பொருத்தமான source-based காரண விளக்கம்.
5. குறுவினா/சிறுவினா/நெடுவினா/திறந்தநிலை வினாக்களுக்கு மூன்று empty placeholders + source links மட்டும்.
6. Old Answer Website-ன் question wording வேறுபட்டால் WORDING_VARIANT / QUESTION_MISMATCH என்று குறிக்கவும்; கேள்வியை மாற்றக்கூடாது.
7. Source conflict, inaccessible page, missing answer ஆகியவை தெளிவாகப் பதிவு செய்யப்பட வேண்டும்.
8. User தன் source comparison மற்றும் answer writing-ஐ பின்னர் செய்வார்.

### 18.7 Scope across other Classes

The supplied Cloudflare URL is specifically named `tn-class-10.pages.dev`. Do not infer Cloudflare hostnames for other classes. For Classes 1–12, obtain / verify the correct GitHub Repository or Cloudflare Pages URL for each class, then repeat the same Current-Book Version Gate at subject / medium / term level. A general URL pattern must not be invented.


---

## 19. New Source Candidate — TNTextbooks.in + 2026–27 Official Distribution Cross-check (03-11-2026)

### 19.1 Website Assessment

User-supplied index:
[https://www.tntextbooks.in/p/school-books.html](https://www.tntextbooks.in/p/school-books.html)

Class-wise pages are listed for 1st–12th standard. Example:
- [1st Books](https://www.tntextbooks.in/p/1st-books.html)
- [3rd Books](https://www.tntextbooks.in/p/3rd-books.html)
- [6th Books](https://www.tntextbooks.in/p/6th-books.html)
- [8th Books](https://www.tntextbooks.in/p/8th-books.html)
- [9th Books](https://www.tntextbooks.in/p/9th-books.html)
- [10th Books](https://www.tntextbooks.in/p/10th-books.html)
- [11th Books](https://www.tntextbooks.in/p/11th-books.html)
- [12th Books](https://www.tntextbooks.in/p/12th-books.html)

The pages often contain:
- Current / "New Edition" sections.
- Previous Edition sections.
- Older academic-year / syllabus sections.
- Tamil Medium and English Medium.
- Term-wise PDFs / ZIP files / EPUBs / Google Drive links.

**Assessment:** This is a useful third-party textbook discovery and download index. It is **not** the official Tamil Nadu Government textbook publisher or the authoritative place to decide the current edition. Use it to discover candidate PDFs, not to certify validity.

Official distribution authority:
[Tamil Nadu Textbook and Educational Services Corporation](https://www.textbookcorp.in/) and its [Schools / Textbook Distribution Notices](https://textbookcorp.in/schools).

### 19.2 Important reliability warnings from TNTextbooks.in

The pages contain broad "New Syllabus - 2026–27" headings, but some descriptive text is contradictory, stale, or inconsistent with official distribution information. Examples observed:

1. **Class 8 page:** It calls the books 2026–27 new books but also says students will follow old books until 2026–27. It separately labels 2024–25 as Previous Edition. A current-section Drive file title is `Class_8_Tamil_2025_Edition`. This title alone does not prove whether the book is the exact current 2026–27 school copy.
   - [Class 8 page](https://www.tntextbooks.in/p/8th-books.html)
   - Google Drive title returned from its current Tamil download: `Class_8_Tamil_2025_Edition-www.tntextbooks.in.pdf`.

2. **Class 1 page:** It labels its contents 2026–27 but the first Term-I current-section Drive PDF title is `Class_1_Tamil_Tamil_Tamil_-_Term_1_-_2025_Edition`. The official Corporation separately says 2025–26 Term-I books for Classes 1–3 are now obsolete and that 2026–27 Term-I / Term-II books have new distribution dates. Therefore this particular 2025-named Term-I file must be treated as **suspect / unverified**, not automatically current.
   - [Class 1 page](https://www.tntextbooks.in/p/1st-books.html)
   - Google Drive title returned: `Class_1_Tamil_Tamil_Tamil_-_Term_1_-_2025_Edition-www.tntextbooks.in.pdf`.

3. **Class 6 page:** It lists 2026–27 Term 1, Term 2 and Term 3 for TM / EM, plus a separate Previous Edition area. A current-section Drive title for Tamil Term-I appears as `6th_Tamil_Term_I - www.tntextbooks.in.pdf`; its filename does not itself identify an edition year. Verify the PDF's internal imprint and match against the current official book.
   - [Class 6 page](https://www.tntextbooks.in/p/6th-books.html).

4. **Class 12 page:** It has a heading "New Edition Books Update", but one current-section PDF title returned by Google Drive is `Class_12_Accountancy_Tamil_2024_Edition-www.tntextbooks.in.pdf`. This is a clear example that a file carrying a 2024 edition label may still appear in a page with a 2026–27 heading. Do not classify it as current or old until the actual inside imprint / contents and official current book are compared.
   - [Class 12 page](https://www.tntextbooks.in/p/12th-books.html).

5. **Class 10 page:** It has a 2026–27 "New Books" area and separate Previous Edition books, including 2024–25 / older editions. Download the current-section PDF candidate, inspect its internal title and revision page, and compare it with the exact 2026–27 school copy before use.
   - [Class 10 page](https://www.tntextbooks.in/p/10th-books.html).

These findings show why the heading / section name / file name cannot serve as the only edition proof. Page content and file metadata must be verified.

### 19.3 Official 2026–27 Distribution Schedule — Authoritative checkpoint

The Tamil Nadu Textbook and Educational Services Corporation's current public notice gives these 2026–27 sale / distribution dates:

| Classes | Current book structure / official release notice | Date |
|---|---|---|
| 1–3 | Term-I (TM / EM / minority languages) | 25-05-2026 |
| 1–3 | Term-II (TM / EM / minority languages) | 22-09-2026 |
| 4–7 | Term-I | 14-05-2026 |
| 1–7 | Term-II | 22-09-2026 |
| 8 and 11 | Annual textbooks (TM / EM) | 14-05-2026 |
| 9, 10 and 12 | Annual textbooks (all subjects, TM / EM) | 10-04-2026 |

The Corporation also lists 2026–27 Tamil textbooks for Classes 1–10 as available from 10-04-2026. Check the official notice wording for the exact subject / volume structure before creating a class inventory.

**Critical obsolete-book notice:** The Corporation explicitly says that Class 1–3 Term-I textbooks printed during academic year 2025–26 are now obsolete / no longer in use, and offers them at a discount for competitive-exam aspirants until 03-12-2026. Therefore, do not use those old 2025–26 Term-I PDFs as the current 2026–27 source.

Official source:
- [Textbook Corporation — Schools](https://textbookcorp.in/schools)
- [Textbook Corporation Home](https://www.textbookcorp.in/)

This schedule is a release/distribution confirmation. It does **not**, by itself, provide every book's internal edition/reprint metadata. The actual printed copy / official PDF still has to be inspected.

### 19.4 Critical distinction — Edition vs Reprint vs Academic Year

Do not treat these as the same field:

| Field | What it means | Example |
|---|---|---|
| First Edition | First publication year | 2019 |
| Revised Edition | Year the text was revised | 2024 or 2025 |
| Reprint / Printing Year | When the same edition was printed again; may include corrections | 2026 reprint |
| Academic Year Validity | School year in which this book is actually prescribed / used | 2026–27 |
| Term / Volume | Which term / volume the PDF belongs to | Term I, Term II, Annual, Volume I / II |
| Medium | Instruction language | TM / EM |

A 2024 Revised Edition may still be the current 2026–27 book if the same edition continues to be prescribed / reprinted. Conversely, a 2025-labeled Term-I file may already be obsolete if the Corporation has replaced that school-year volume. The only correct answer is established by matching the actual book against current official distribution and the book's internal contents / imprint.

### 19.5 Solution — Create a Version Manifest Before Re-extracting Questions

For every Class × Subject × Medium × Term / Volume, create an edition record:

| Field | Required value |
|---|---|
| Class | 1–12 |
| Subject | Exact subject name |
| Medium | TM / EM / other |
| Academic Year | 2026–27, etc. |
| Term / Volume | Term I / II / III / Annual / Vol I / II |
| First Edition | As printed |
| Revised Edition | As printed |
| Reprint Year | As printed |
| Total PDF Pages | Physical page count |
| Contents / Chapters | Exact chapter list |
| Current Official Release Evidence | Corporation notice / school-issued copy |
| Candidate PDF URL | Official URL if available; otherwise third-party mirror clearly marked |
| File SHA-256 | Hash of the exact downloaded source PDF |
| Edition Status | CURRENT / CURRENT_REPRINT / SUPERSEDED / UNVERIFIED |
| Verification Date | Date checked |
| Notes | Mismatch / correction / page or lesson differences |

A useful edition manifest filename can be `book_manifest.json` at the subject / book level or a master `edition_audit.csv` for all classes. Do not add unnecessary files to each lesson folder.

### 19.6 Versioned Storage — Never Delete the Existing Old Work

**Do not overwrite or delete the existing PDF pages, questions.md, quiz.md or quiz.json.** They are valuable work and may be reused where the content is unchanged.

Recommended principle:
- Existing edition = preserve as Legacy / Archive.
- Verified current edition = create as the Active version.
- Every question, answer and quiz must identify which book edition it belongs to.
- Keep the current lesson-folder pattern and the same file names inside each edition.

Example structure (implementation can be adjusted to avoid breaking existing Cloudflare URLs):

    <class>/<subject>/
    ├── _editions/
    │   ├── 2024-legacy/
    │   │   ├── source_book.pdf
    │   │   ├── pages/
    │   │   └── old_chapters/
    │   │       └── book_back_questions/
    │   │           ├── questions.md
    │   │           ├── quiz.md
    │   │           ├── quiz.json
    │   │           └── answers.md
    │   └── 2026-27-current/
    │       ├── source_book.pdf
    │       ├── pages/
    │       └── current_chapters/
    │           └── book_back_questions/
    │               ├── questions.md
    │               ├── quiz.md
    │               ├── quiz.json
    │               └── answers.md
    └── edition_audit.md

The exact location can be chosen during repository implementation. Existing live paths must remain intact until Cloudflare / viewer / index references are safely migrated. If moving files would break existing site URLs, leave the old paths untouched and build the current edition in a parallel folder first.

### 19.7 PDF Download and Single-page Extraction Procedure

For each verified current PDF:

1. Prefer the official Government / Corporation PDF link. If it is unavailable, use TNTextbooks.in as a discovery mirror and record that it is third-party.
2. Download the full original PDF first. Do not split directly from a browser preview.
3. Preserve the original unmodified PDF as the source copy. Record source URL, download date, exact filename, byte size, PDF page count and SHA-256.
4. Open and inspect:
   - Cover / title page.
   - Copyright / First Edition / Revised Edition / Reprint page.
   - Contents / TOC.
   - Chapter starting pages.
   - Every Book Back / Evaluation / Exercise page.
5. Split the original PDF into one-page PDF files, preserving physical sequence:
   - `page_001.pdf`
   - `page_002.pdf`
   - ...
   - `page_NNN.pdf`
6. Keep physical PDF page number separate from the printed textbook page number. Preliminary pages can cause offsets.
7. Create / update `pages.json` to map each physical PDF page to its chapter, printed page and page label.
8. Do not assume a smaller / larger page count alone proves a different edition. Compare text, TOC, chapter structure and Book Back pages.

### 19.8 Old-to-Current Question Migration

For every chapter, compare existing `questions.md` with the verified current textbook:

| Comparison Status | Meaning | Action |
|---|---|---|
| UNCHANGED | Same question and same meaning | Reuse after page and wording verification |
| WORDING_CHANGED | Question text revised | Update to exact current-book wording |
| PAGE_MOVED | Same content moved to another page | Update page reference |
| QUESTION_ADDED | New current-book question | Add to current questions.md |
| QUESTION_REMOVED | Old question no longer present | Keep in legacy edition only; do not include in current Quiz |
| CHAPTER_RESTRUCTURED | Chapters merged / split / renamed | Re-map old chapters to current TOC |
| NOT_MATCHED | No valid counterpart | Manual review; do not guess |

If chapter structure or exercises change substantially, re-extract the entire current edition's Book Back question set for that subject rather than trying to patch fragments. If only a few pages changed, update those pages and retain verified unchanged questions.

### 19.9 Answer Source Sequence for Each Current Chapter

1. Edition / question wording gate முடிந்த பிறகே source collection தொடங்கவும்.
2. questions.md-இல் உள்ள ஒவ்வொரு கேள்விக்கும் பொருத்தமான direct answer pages / guide PDFs தேடவும்.
3. ஒவ்வொரு page-ஐத் திறந்து answer உண்மையில் உள்ளதா, கேள்வி exact match ஆகிறதா என்று பதிவு செய்யவும்.
4. Non-objective questions: விடைக்குறிப்பு, சாதாரண விடை, விரிவான விடை மூன்றையும் [TO_BE_PREPARED_LATER] ஆக விட்டு, source links மட்டும் சேர்.
5. Objective questions: source-ல் காணப்பட்ட குறுகிய option/answer ஒவ்வொன்றையும் தனித்தனியாக சேர்; 3/5 source cap கிடையாது.
6. எல்லா one-mark / one-word வினாக்களுக்கும் காரண விளக்கம் தேடு: grammar / textbook vocabulary / lesson content / classification / general knowledge. 1–3 வரி விளக்கத்துடன் supporting URL கொடு.
7. Conflict / wording mismatch / access block / missing answer-ஐ பதிவு செய்; unsupported choice செய்யாதே.
8. Quiz file உருவாக்குதல் தனி task; அதற்கான தனி அறிவுறுத்தல் இல்லாமல் quiz files மாற்றாதே.
9. இந்தக் கட்டத்தில் சொந்த model answers எழுதப்படமாட்டாது.

### 19.10 Current Recommendation

Do not immediately redo all 12 classes. First build the edition audit matrix for all available class repositories and all books. This prevents redoing work that is already based on a still-current reprint.

Prioritize:
1. Class 10 Tamil — confirmed need for current-vs-legacy comparison because current Repo has 248 pages / 9 folders while the 2025 revised candidate has 184 pages / 7 iyals.
2. Classes 1–3 — urgently inspect Term-I PDFs because the Corporation explicitly says 2025–26 Term-I books are obsolete and 2026–27 Term-I / Term-II books have been issued.
3. Classes 4–7 — verify 2026–27 Term-I and Term-II books individually.
4. Classes 8, 9, 10, 11, 12 — verify each 2026–27 annual book and its internal edition / reprint page.

**Rule:** No mass deletion, no blind overwrite, no global “all 2024 books are old” assumption. Audit first; then archive, reuse, re-extract or update each subject based on evidence.


---

## 20. Official Current-Edition Verification — Government Sources and Decision Rules (03-11-2026)

### 20.1 The core rule

Do not determine the current school textbook from the imprint year alone.

A book can say "Revised Edition 2024" and still remain the prescribed 2026–27 textbook if the same content continues to be distributed. A book can have a 2025 printing / revision and still be superseded. A fresh 2026 reprint may reproduce a 2024 revised edition without changing lesson content.

Always separate these fields:
- First Edition year
- Revised Edition year
- Reprint / printing year
- Academic Year prescribed for school use
- Term / Volume
- Current syllabus / content structure
- Actual issue supplied to students in the target academic year

The **current school-issued book** is the authority for question extraction. The most recent imprint year is only bibliographic evidence.

### 20.2 Official Government sources checked

| Priority | Official source | Link | What it proves | What it does not prove |
|---|---|---|---|---|
| 1 | Tamil Nadu Textbook and Educational Services Corporation | [Official School / Distribution Notices](https://www.textbookcorp.in/schools) | 2026–27 class / term / annual textbook sale and distribution notices; obsolete book notices | Does not list each Subject's internal Revision Year, page count or direct public PDF link |
| 2 | Tamil Nadu Textbook and Educational Services Corporation | [Official Home](https://www.textbookcorp.in/) | Current 2026–27 distribution notice and official contact routes | Not a full public edition-history catalogue |
| 3 | Legacy official online textbook portal listed by India.gov | [textbookcorp.tn.gov.in](https://textbookcorp.tn.gov.in/) and [textbooksonline.tn.nic.in](https://textbooksonline.tn.nic.in/) | India.gov identifies the Corporation website as a place where school textbooks can be read online | During the assistant's check, the old domains returned timeout / 502 / access errors. This is tool access failure, not proof that all users cannot open them. Verify manually in a normal browser before relying on a PDF |
| 4 | SCERT / School Education digital learning platform | [TN DIKSHA](https://diksha.gov.in/tn/) | SCERT-curated curriculum-linked e-content, QR textbook resources and learning materials | Not confirmed as a complete downloadable PDF archive of every 2026–27 textbook |
| 5 | School Education learning resources | [Manarkeni](https://manarkeni.tnschools.gov.in/) | Public indexed pages expose Class / Subject / Medium / Chapter e-Book, Download and Book Preview resources | A complete current full-book catalogue for every class / medium was not confirmed |
| 6 | Official contact | [Textbook Corporation Contact](https://textbookcorp.in/schools/contact) | Direct email and regional offices for resolving edition / distribution questions | Contact support is required when a public edition-history answer is not published |

**Important:** The current Textbook Corporation public Website is primarily a distribution / sales notice and school-order portal. It is not presently a complete public "Edition History" register with every Class × Subject × Medium × Term and downloadable official PDF.

### 20.3 Official 2026–27 distribution facts (as published by the Corporation)

The Corporation's School Notices currently state:

| Classes | 2026–27 official distribution structure | Published start date |
|---|---|---|
| 1–3 | Term-I, TM / EM / minority languages | 25-05-2026 |
| 1–3 | Term-II, TM / EM / minority languages | 22-09-2026 |
| 4–7 | Term-I, TM / EM | 14-05-2026 |
| 1–7 | Term-II, TM / EM / minority languages | 22-09-2026 |
| 8 and 11 | Annual textbooks, TM / EM | 14-05-2026 |
| 9, 10 and 12 | Annual textbooks, TM / EM | 10-04-2026 |
| Tamil Textbooks | Classes 1–10 Annual Tamil textbook sale | 10-04-2026 |

Official references:
- [Textbook Corporation 2026–27 Notices](https://www.textbookcorp.in/schools)
- [Textbook Corporation Contact](https://textbookcorp.in/schools/contact)

**Obsolete-book warning:** The Corporation explicitly states that Classes 1–3 Term-I books printed during academic year 2025–26 are now obsolete and are sold at a discount for competitive-exam aspirants. Do not classify those books as current 2026–27 school textbooks. The current 2026–27 Term-I and Term-II books have separate distribution announcements.

### 20.4 Curriculum transition — Classes 1–3 vs Classes 4–12

A May 2026 report citing School Education Department officials says:
- Classes 1–3 receive newly designed syllabus textbooks for 2026–27.
- Classes 4–12 receive a new set of textbooks under the existing / old syllabus for 2026–27.
- The broader curriculum revision is planned for 2027–28.

Reference: [DT Next — 13 May 2026](https://www.dtnext.in/amp/story/news/tamilnadu/teachers-continue-with-classes-4-12-textbook-work-despite-new-regime-uncertainty).

A separate August 2026 report says SCERT released draft curriculum for Classes 6–10 for public feedback under the Tamil Nadu Curriculum Framework 2025. A draft is not the same as a final implemented textbook. Do not use a proposed 2027–28 curriculum to replace the current 2026–27 student book.

### 20.5 Class 10 Tamil — evidence and correct interpretation

Current evidence:
1. Repo's existing Tamil files were catalogued by Antigravity as a 2024-imprint book with 9 Iyal groups.
2. In March 2025, TamilVithai published a 2025–26 Class 10 Tamil revised-book / change-portion page stating that the earlier 9-Iyal syllabus was reduced to 7 Iyals; it lists deleted, changed and newly added questions:
   - [2025–26 new Class 10 Tamil book / change portion](https://www.tamilvithai.com/2025/03/10th-tamil-new-book-change-portion-2025.html)
   - [2025–26 revised book page](https://www.tamilvithai.com/2025/03/10th-tamil-new-syllabus-book-2025-26-pdf.html)
3. A 2025 third-party FlipHTML5 copy displays the textbook's printed imprint "Revised Edition 2025" and a 7-Iyal contents structure:
   - [10th Tamil 2025–26 — TAMILVITHAI FlipHTML5](https://fliphtml5.com/bison/xbxt/10th_Tamil_new_book_2025_-_2026/)
4. A July 2026 third-party exam-portion table lists Class 10 Tamil annual portions across Iyals 1–7. This is supporting school-use evidence but not a Government-issued edition file:
   - [2026–27 exam portions](https://www.tamilaruvi.in/2026/07/tn-school-exam-syllabus-2026-2027-class-6-to-12-full-portion-details.html)
5. The Corporation confirms 2026–27 annual Class 10 textbook distribution, but its public notice does not expose the exact Tamil PDF / revised imprint year.

**Interpretation:** The 2025 7-Iyal Tamil book is the strongest current-version candidate for Class 10 in 2026–27, while the Repo's 2024 / 9-Iyal book is a pre-reduction version and should be kept as a Legacy Reference for now. But the precise 2026–27 school-issued imprint / reprint must be verified before writing `CURRENT_CONFIRMED`.

Do not claim that a 184-page digital FlipHTML view is definitively the printed physical page count. Record separately:
- PDF viewer page count
- PDF file page count
- printed page numbers visible inside the book
- number of lesson units / TOC structure

Do not infer printed book page count from split PDF page files or a flipbook's viewer page count without confirming its scanning layout.

### 20.6 Why the Antigravity Master Edition Audit cannot declare "Current" yet

GitHub report:
[MASTER_EDITION_AUDIT_REPORT.md](https://github.com/Eaglesiva/tn-class-10/blob/main/docs/MASTER_EDITION_AUDIT_REPORT.md)

The extraction of the PDF imprint page, edition year, and file page count is useful. However, its initial labels such as `100% Current`, `Current (2024/2025)` or `Legacy` were assigned without matching every Subject / Medium / Term against the actual 2026–27 school-issued copy or a Government-published per-book edition register.

Therefore:
- Treat the report as **PDF Imprint Inventory**, not a final Current Edition Audit.
- All "Current" labels must remain `CURRENT_VALIDITY_UNVERIFIED` until distribution / content matching is done.
- Older imprint years such as 2018 / 2019 / 2022 do not automatically prove obsolescence.
- 2024 / 2025 imprint years do not automatically prove current status.
- The known Classes 1–3 Term-I obsolete notice is a confirmed exception.
- The Class 10 Tamil 2024 / 9-Iyal version requires migration to the 2025 revised / 7-Iyal candidate after 2026–27 copy verification.

### 20.7 Official confirmation request process

Where the public site does not show the exact edition history, request the Corporation to confirm the latest prescribed issue for a specific class / subject / medium / term.

Official contact:
- Email: `support@textbookcorp.in`
- Salem regional office: 0427-2351834 / 7395800457
- General contact page: [Official contact list](https://textbookcorp.in/schools/contact)

Suggested enquiry fields:
- Academic year: 2026–27
- Class
- Subject
- Medium (TM / EM)
- Term / Annual
- Latest Revised Edition year
- Latest Reprint / correction year
- Whether the listed older imprint remains the book distributed to schools in 2026–27
- Official PDF / e-book URL, if publicly available
- Whether any errata / correction circular has been issued

Use the school's actual 2026–27 distributed copy as a cross-check. A photo of its title page, imprint page and Contents page can resolve whether a PDF found online matches the physical student copy.

### 20.8 Correct method to obtain the current PDF

1. Start at the official Corporation notice and establish the correct class / term / annual book for 2026–27.
2. Try the official online textbook reading links listed by India.gov / the Corporation. If the legacy portal does not load, record the failure and do not assume a third-party download is official.
3. Check Manarkeni / TN DIKSHA for Government-hosted chapter e-Books or QR-linked resources where available.
4. If the full book PDF is not publicly exposed, request the exact digital file / e-book link from the school / Headmaster / subject teacher or the Corporation; use the actual school-issued 2026–27 book as the reference.
5. TNTextbooks.in and similar third-party indexes may be used to discover candidate PDFs, but must be labelled `THIRD_PARTY_MIRROR`; never certify their "Current/New Edition" heading without comparing the actual PDF to the official current book.
6. Download the entire PDF before splitting. Save the original, URL, access date, file size and SHA-256.
7. Inspect the Cover, imprint / correction page, Contents, and every Book Back exercise page.
8. Split into `page_001.pdf` etc. only after the PDF is verified. Keep physical PDF page, scanned spread page and printed page number as separate fields.
9. Preserve the existing old PDF and question work. Create the new active edition in a parallel versioned folder; do not overwrite old files.
10. Compare old questions with the current book using `UNCHANGED`, `WORDING_CHANGED`, `PAGE_MOVED`, `QUESTION_ADDED`, `QUESTION_REMOVED`, `CHAPTER_RESTRUCTURED`, `NOT_MATCHED`.

### 20.9 Edition status vocabulary — use instead of guessing

| Status | When to use |
|---|---|
| `IMPRINT_DETECTED` | Only the edition / reprint statement was extracted |
| `CURRENT_VALIDITY_UNVERIFIED` | Current academic-year use has not been proved |
| `CURRENT_CONFIRMED_2026_27` | Matched to the actual 2026–27 prescribed / school-issued book |
| `CURRENT_REPRINT_2026_27` | Reprint of an earlier revision, with content / official distribution match confirmed |
| `SUPERSEDED` | Official evidence shows a newer prescribed edition replaced it |
| `OBSOLETE_CONFIRMED` | Official Corporation / Department explicitly states it is no longer in use |
| `THIRD_PARTY_MIRROR` | PDF came from a non-government mirror, pending official cross-check |
| `CONTENT_MATCH_CONFIRMED` | TOC, chapter structure and question pages match the target current book |
| `ERRATA_PENDING` | Correction notice exists but has not been applied / checked |

**Final rule:** Edition year is metadata; current academic-year validity is a separate verification result. Never set `CURRENT_CONFIRMED_2026_27` from a printed year or a private website's section label alone.


---

## 21. Practical Current Textbook Download Route — Government First (03-11-2026)

### 21.1 Important distinction

The exact official 2026–27 digital PDF and the official distribution notice are two separate things.

- The Textbook Corporation notice proves that the relevant class / term / annual books have entered 2026–27 distribution.
- A PDF download link must still be matched with the actual printed book's title / imprint / contents / exercise pages.
- The Corporation's public site does not currently expose a complete public edition-history register for every class × subject × medium × term. Do not infer a full edition history from its annual sale notices or price list alone.

### 21.2 Government / school-education PDF route to try first

**Candidate official e-textbook route:**
[https://tnschools.gov.in/scert-textbook](https://tnschools.gov.in/scert-textbook)

This route is referenced by public textbook-download instructions as the Tamil Nadu School Education / SCERT textbook page. Suggested steps in a normal browser:

1. Open the link above.
2. Select the Class tab.
3. Select the Subject.
4. Select the Term / Full-year option actually prescribed for that class.
5. Select Tamil Medium / English Medium.
6. Click the download link (often described as "Click Here To Download").
7. Save the complete source PDF before making page splits.
8. Record the exact landing URL and direct PDF URL.

**Tool-access note:** On 03-11-2026, the assistant's web retrieval layer could not render `tnschools.gov.in` dynamic pages (the main page and `/scert-textbook` returned empty / cache errors). This is not proof that the route is broken in Chrome. The user should test it in a normal browser. Do not claim a successful PDF download until the actual PDF opens.

A third-party guide page describing this route is not the authority; the actual `tnschools.gov.in` domain / content and the downloaded book imprint must be checked.

### 21.3 Official distribution / edition-validity authority

**Tamil Nadu Textbook and Educational Services Corporation:**
- [Official School / Distribution Notices](https://www.textbookcorp.in/schools)
- [Official Contact and Regional Offices](https://textbookcorp.in/schools/contact)
- [Official Textbook Price List PDF](https://www.textbookcorp.in/files/PRICELIST.pdf)

The Corporation's current 2026–27 notices provide:
- 1–3: Term-I (25-05-2026) and Term-II (22-09-2026).
- 4–7: Term-I (14-05-2026); Term-II notice for 1–7 (22-09-2026).
- 8 and 11: Annual books (14-05-2026).
- 9, 10 and 12: Annual books (10-04-2026).
- Tamil textbooks 1–10: 10-04-2026.
- 2025–26 Term-I books for Classes 1–3: explicitly obsolete for current use.

Its public price list provides class / subject / medium / book prices. It may help identify which titles are being sold, but **it does not itself prove the Revised Edition Year / the precise PDF contents**.

### 21.4 Government resources that can supplement PDF acquisition

| Official resource | URL | What it can do | Limitation |
|---|---|---|---|
| TN Schools / SCERT E-Textbook route | [tnschools.gov.in/scert-textbook](https://tnschools.gov.in/scert-textbook) | Class / Subject / Medium / Term book download route described by public instructions | Dynamic page did not render through assistant's web tool; must be tested in Chrome |
| Manarkeni | [manarkeni.tnschools.gov.in](https://manarkeni.tnschools.gov.in/) | Government-hosted chapter e-Book / topic resources with Download and Book Preview on indexed records | Appears chapter/resource based; not confirmed as a complete full textbook PDF archive for every class |
| TN DIKSHA | [diksha.gov.in/tn](https://diksha.gov.in/tn/) | SCERT-curated curriculum-linked digital resources, energized textbook QR resources, teaching / learning material | Not confirmed as a complete current 2026–27 full-book PDF archive |
| Textbooksonline legacy portal | [textbooksonline.tn.nic.in](https://textbooksonline.tn.nic.in/) | Listed by India.gov as a government textbook online-reading service | Returned 502 during 03-11-2026 tool check; retry in normal browser, but do not treat a failure as evidence of obsolescence |
| India.gov official portal listing | [Tamil Nadu Textbook Corporation](https://www.india.gov.in/category/education-learning/subcategory/school-education/details/website-of-tamil-nadu-textbook-corporation) | Confirms Textbook Corporation site / online textbook-reading service as a Government resource | Directory listing; not an edition-history table |
| TN Textbook Corporation older catalogue route | [textbookcorp.in/textbook](https://textbookcorp.in/textbook/) | Government domain, book catalogue landing page | Current rendered page contains legacy / generic items and does not reliably expose the full current school textbook PDF collection |

**Do not confuse these similar-looking domains:**
- `textbooksonline.tn.nic.in`: the legacy online textbook portal listed by India.gov.
- `tntextbooksonline.com`: a Textbook Corporation storefront focused on rare books / children's books / collections; it is not the same school-textbook PDF catalogue.
- `tntextbooks.in`: third-party PDF aggregator, not a Government domain.
- `tnschools.gov.in/scert-textbook`: Government School Education / SCERT e-textbook route to test for downloadable school books.
- `textbookcorp.in`: official Corporation notices, contacts, price list and school distribution information.

### 21.5 What to do when the official PDF route does not work

1. First use the actual current 2026–27 book issued by a Government / Government-aided school as the physical reference. Ask the subject teacher / Headmaster to confirm the exact book being used.
2. Photograph or scan only the evidence pages needed:
   - Cover / title page.
   - Imprint / First Edition / Revised Edition / Reprint page.
   - Contents page.
   - Book Back / Evaluation pages.
3. If no official public PDF is available, contact the Corporation and ask for the digital textbook / exact current edition confirmation:
   - Email: `support@textbookcorp.in`
   - Salem Regional Office: `0427-2351834`
   - Salem mobile contact on the current Corporation contact page: `7395800457`
   - [Official contact page](https://textbookcorp.in/schools/contact)
4. Ask specifically for:
   - 2026–27 academic year prescribed book;
   - class, subject, medium and term / annual;
   - Revised Edition year;
   - reprint / correction year;
   - whether an earlier edition is still prescribed;
   - official PDF / e-book URL if available;
   - errata / correction circular, if any.
5. If using TNTextbooks.in / FreeTNBooks / Padasalai / another aggregator, mark the PDF `THIRD_PARTY_MIRROR` until its actual internal imprint and all key content pages are matched against the school-issued copy.
6. Never choose the PDF just because its host page says "New Edition 2026–27". Check the file downloaded behind the link.

### 21.6 Edition decision protocol — practical

A book can only receive `CURRENT_CONFIRMED_2026_27` when all relevant checks are satisfied:

- The class / subject / medium / term matches the 2026–27 official distribution.
- The actual PDF or school-issued book matches the title / imprint.
- Contents / chapter structure matches.
- Book Back / evaluation questions match.
- Any correction / errata notices have been applied.
- Evidence URL / photo / page references are recorded.

If only the imprint is known, mark `IMPRINT_DETECTED` and `CURRENT_VALIDITY_UNVERIFIED`.
If an official portal lists the book for the correct 2026–27 term, but the PDF file itself cannot be opened / matched, mark `OFFICIAL_LISTING_FOUND_PDF_UNVERIFIED`.
If a third-party mirror provides the candidate file, mark `THIRD_PARTY_MIRROR` separately from the validity status.

### 21.7 Class 10 Tamil present decision

- Existing Repo 2024 / 9-Iyal PDF: preserve as a pre-revision Legacy copy.
- 2025 Revised / 7-Iyal book: strongest revised candidate identified to date.
- 2026–27 current school-issued PDF / physical copy: exact official imprint and content match still pending.
- Do not treat the 2025 FlipHTML5 mirror as an official Government-hosted PDF.
- Do not assume every 2024 imprint in Classes 4–12 is obsolete. Confirm each current book using official distribution + school-issued content / Government e-book PDF.

**Operational priority:** In Chrome, try `https://tnschools.gov.in/scert-textbook` first. If it opens, download the exact Class 10 Tamil full-year PDF and share its URL or file. If it does not open, use the school-issued 2026–27 book / Corporation confirmation rather than guessing from a private site.


---

## 22. Latest Reconciliation — Official SCERT API vs 2025 7-Iyal Private Copy + All-Class Recheck (03-11-2026)

### 22.1 Correct conclusion for Class 10 Tamil

The latest evidence changes the earlier provisional conclusion. Do **not** continue to describe the 184-page / 7-Iyal copy as the strongest current State Board textbook candidate.

The most direct current government evidence is now:
- Official TNSchools page: [https://tnschools.gov.in/scert-textbook](https://tnschools.gov.in/scert-textbook)
- Official Angular application's SCERT Books API: [https://emis3.tnschools.gov.in/api/get_scert_books](https://emis3.tnschools.gov.in/api/get_scert_books)
- API-provided Government CDN PDF: [10th_Tamil_Text.pdf](https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/10th_Tamil_Text.pdf)

The Antigravity-generated proof report records that this API-listed PDF is 57,588,385 bytes / 248 pages and its ETag / MD5 value is identical to the local file `tn_school_books/10th/tamil/pdf/Class_10_Tamil_Full_Book.pdf`. The Government API entry and exact file match make the 248-page / 9-Iyal copy the strongest available **official current-portal State Board textbook reference for Class 10 Tamil as of 03-11-2026**.

This is stronger evidence than a third-party website title or a FlipHTML book listing. Preserve the current Local PDF and its question work. There is no reason to re-download or rebuild Class 10 Tamil from the 184-page file for the 2026–27 State Board workflow, unless a newer official API entry / school-issued copy is later found.

### 22.2 What is the 184-page / 7-Iyal PDF?

The 184-page copy discovered earlier is hosted / published by TAMILVITHAI, not linked as the current Class 10 Tamil PDF from the official SCERT API evidence reviewed in this report.

Evidence:
- [TAMILVITHAI's 2025–26 new-syllabus page](https://www.tamilvithai.com/2025/03/10th-tamil-new-syllabus-book-2025-26-pdf.html), published 15-03-2025, explicitly says that the 2025–26 Tamil syllabus / portion was reduced from 9 Iyals to 7 Iyals and that TAMILVITHAI uploaded the modified portion book on its own website.
- [TAMILVITHAI's Unit 1 change-portion page](https://www.tamilvithai.com/2025/03/10th-tamil-new-book-change-portion-2025.html) lists removed, changed and newly added questions.
- [FlipHTML5 copy](https://fliphtml5.com/bison/xbxt/10th_Tamil_new_book_2025_-_2026/) is attributed to uploader TAMILVITHAI and carries a printed Revised Edition 2025 imprint.

**Correction to a previous statement:** Do not label this 184-page file as "CBSE-only" unless an official source explicitly proves that. The currently available evidence supports describing it as a **third-party-hosted 2025–26 reduced / modified 7-Iyal candidate**. Its exact official authorization and its relationship to any CBSE / State Board exam portion remain unverified. A government imprint reproduced inside a third-party-hosted copy does not, by itself, prove the file's host, completeness, or prescribed status.

The distinction to preserve:
- 248-page / 9-Iyal PDF = exact match to the current SCERT API's Class 10 Tamil PDF, based on Antigravity's recorded byte-size / MD5 evidence.
- 184-page / 7-Iyal PDF = third-party-hosted reduced / modified 2025–26 copy; not shown by the current API proof to be the current full State Board book.

### 22.3 Important scope limit of the official proof

The existing `OFFICIAL_GOVERNMENT_CDN_VERIFICATION_PROOF.md` proves / records the exact match for **Class 10 Tamil only**. It does not yet prove that every Local PDF for Classes 1–12 matches the official API.

The earlier `MASTER_EDITION_AUDIT_REPORT.md` is an imprint / page-count inventory. Its old `CURRENT` and `LEGACY` conclusions must not be used as final Current-Year determinations. An API listing, a local imprint, and a hash match are different pieces of evidence.

For Classes 1–12, Antigravity must now perform a complete **Official API ↔ Local PDF file-level audit**. Do not merely inspect sample PDFs or report the API's list of classes. Compare every API entry with the corresponding Local file.

### 22.4 Required full API ↔ Local file comparison

For every official API record, extract:
- API class / standard
- Subject / textbook name
- Medium
- Term / Annual / Volume
- Official filename
- Direct CDN URL
- Any official metadata / issue status

For every local book:
- Local class / subject / medium / term folder
- Original PDF path
- File size in bytes
- Physical PDF page count
- Printed page numbering / contents
- Imprint / revised edition / reprint information
- Local MD5 and SHA-256

Then download the exact PDF at the official CDN URL (where feasible) and compare:
- Remote vs local byte size
- Remote vs local SHA-256 (preferred)
- ETag / MD5 where SHA-256 cannot be obtained
- PDF page count and contents

A file may be declared an exact official match only when the actual bytes / strong hash match. If only filename / page count / imprint appears similar, do not label it a match.

### 22.5 Required result statuses

Use these statuses, separately from academic-year validity:
- `OFFICIAL_API_SHA256_MATCH` — exact file match by SHA-256.
- `OFFICIAL_API_MD5_ETAG_MATCH` — strong practical match recorded by same MD5 and ETag, with method stated.
- `OFFICIAL_API_LISTED_LOCAL_MISMATCH` — official entry exists but local file differs.
- `OFFICIAL_API_LISTED_LOCAL_MISSING` — official file exists but no local copy.
- `LOCAL_NOT_FOUND_IN_CURRENT_API` — local file was not found in the latest API response; requires review, not automatic obsolete status.
- `API_ENTRY_NOT_UNDERSTOOD` — API data could not be confidently mapped.
- `CURRENT_SCHOOL_USE_UNVERIFIED` — exact online file exists, but its 2026–27 school-use status still needs a distribution / school-copy check.

**Important special override:** the Textbook Corporation explicitly marks 2025–26 Term-I books for Classes 1–3 as obsolete for current use. Even if an older copy still appears in a file index or local folder, do not mark it current. Match the 2026–27 Term-I / Term-II entries separately.

### 22.6 Full audit output files requested from Antigravity

Create:
1. `docs/OFFICIAL_API_VS_LOCAL_PDF_AUDIT.md` — readable class-wise summary and decisions.
2. `docs/official_api_local_match_manifest.csv` — one row per official API entry / local candidate, including URL, class, subject, medium, term, filenames, byte sizes, SHA-256 / ETag, page counts, match status and notes.
3. `docs/official_api_scert_books_raw.json` — raw API response snapshot and capture timestamp, if repository policy permits. If the raw response is too large / contains non-public technical data, store a sanitized public-book-only export instead.

The report must clearly separate:
- **API exact file match**
- **official 2026–27 distribution evidence**
- **edition / reprint imprint**
- **question-content match**

Do not collapse these into one "Current" label.

### 22.7 Antigravity execution prompt

Please perform a complete audit using the **live official TNSchools SCERT Books API**, not just the old imprint report.

Official API:
`https://emis3.tnschools.gov.in/api/get_scert_books`

Official PDF CDN base:
`https://d21mc000xink7q.cloudfront.net/scert/textbook/syllabuspdf/`

Tasks:
1. Fetch and save the API response with timestamp.
2. Parse every Class 1–12 entry, including all subjects, TM / EM and applicable terms.
3. Inventory every Local original PDF under `tn_school_books/` and the corresponding GitHub / Cloudflare page files.
4. Map each official API PDF entry to the local PDF.
5. Download official CDN files and compute SHA-256 for the remote / local file; if exact SHA-256 comparison is infeasible, record byte size and ETag / MD5 with limitations.
6. Identify all exact matches, mismatches, missing local copies and local files absent from the API.
7. For every mismatch, inspect the title, imprint, contents and Book Back pages. Do not decide Current / Old from the imprint year alone.
8. Apply the official 2026–27 distribution schedule. In particular, Classes 1–3 Term-I 2025–26 copies are officially obsolete; current 2026–27 Term-I / Term-II must be distinguished.
9. Reconcile Class 10 Tamil:
   - Confirm the 248-page / 9-Iyal local file against the API PDF.
   - Record the existing exact byte / hash match.
   - Record the TAMILVITHAI 184-page / 7-Iyal copy separately as a third-party-hosted 2025–26 reduced/modified candidate, not as the official current full book unless new official evidence is found.
   - Do not label it CBSE-only without a source proving that.
10. Produce the full Markdown report and CSV manifest. Do not modify or delete any existing PDF, questions.md, quiz.md or quiz.json.
11. Do not claim "100% all classes verified" unless every API entry has actually been compared. Report any failures or inaccessible files transparently.

### 22.8 Project decision after current evidence

- **Class 10 Tamil:** retain the 248-page / 9-Iyal Local PDF and the existing extracted question work as the current official-portal-matching base. Perform question-level QA, but do not rebuild from the third-party 184-page copy.
- **Other Classes:** do not assume they match because their imprint says 2024 / 2025, and do not assume they are old because the imprint says 2018 / 2019 / 2022. Wait for the complete official API ↔ local PDF manifest.
- **Old work preservation:** no destructive deletion; mismatches should be stored as separate versions after the report identifies them.


---


