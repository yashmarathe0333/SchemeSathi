# SchemeSathi — AI-Driven Scheme Matching for Marginalized Entrepreneurs

> **Academic Project Prototype**  
> An open, trustworthy, and privacy-preserving web application designed to help underserved, rural, women, SC/ST, and OBC micro-entrepreneurs in India discover and evaluate relevant central and state government schemes.

---

## 🌟 Key Highlights & Architecture

- **Transparent Rule-Based Matching Algorithm**: Instead of an opaque black-box AI API, SchemeSathi executes a deterministic, weighted scoring algorithm (0 to 100 points) evaluating demographic suitability, sector limits, business stage, financial scale, and location.
- **Zero Sensitive Personal Data Collection**: Protects user privacy by never requesting Aadhaar numbers, biometric data, bank account numbers, or OTPs. All data persists strictly in the user's browser `localStorage`.
- **Working Trilingual Interface**: Full translation dictionaries for **English**, **Hindi (हिन्दी)**, and **Marathi (मराठी)**.
- **Realistic & Verified Sample Data**: Includes verified government initiatives (MUDRA, PMEGP, Stand-Up India, PM Vishwakarma, NSFDC, NSKFDC, DAY-NRLM, PMFME, and Maharashtra CMEGP) with safe links to verified official government portals (`.gov.in`, `.nic.in`, `.org.in`).
- **Interactive Local Application Tracker**: Tracks application milestones (*Not Started*, *Preparing Documents*, *Submitted*, *Completed*) with personal notes and interactive document checklists.
- **Demo Management Console**: A client-side prototype admin page allowing educators and evaluators to view, add, edit, delete, or reset sample schemes.

---

## 🚀 Tech Stack

- **Frontend Framework**: React 18 with Vite
- **Styling**: Tailwind CSS with custom Indian governance palette (deep navy `#0F172A`, teal `#0D9488`, and emerald `#059669`)
- **Routing**: React Router DOM (v6)
- **Icons**: Lucide React
- **Data Visualizations**: Recharts (PieChart for match suitability distribution & BarChart for application pipeline)
- **Persistence**: Browser `localStorage` (no external database or paid API keys required)

---

## 📁 Project Structure

```text
SchemeSathi/
├── index.html                   # HTML entry point with Inter & Noto Sans Devanagari fonts
├── package.json                 # Dependencies and npm build/dev scripts
├── vite.config.js               # Vite configuration
├── tailwind.config.js           # Tailwind theme, color scales, and typography
├── postcss.config.js            # PostCSS plugins
├── src/
│   ├── main.jsx                 # React root mount
│   ├── App.jsx                  # Main routes and context providers
│   ├── index.css                # Global Tailwind directives & scrollbar styling
│   ├── context/
│   │   ├── LanguageContext.jsx  # English / Hindi / Marathi state & translation hook
│   │   ├── ProfileContext.jsx   # Entrepreneur profile, saved schemes & tracker state
│   │   └── SchemeContext.jsx    # Scheme records with localStorage override & reset
│   ├── data/
│   │   ├── schemesData.js       # 8+ verified central and state government scheme records
│   │   ├── samplePersonas.js    # 4 realistic test profiles (Anita Devi, Rajesh, Sunita, Manoj)
│   │   ├── statesDistricts.js   # Indian states and key districts mapping
│   │   └── translations.js      # Authentic UI strings for EN, HI, MR
│   ├── utils/
│   │   └── matchingEngine.js    # 0-100 weighted rule-based matching engine
│   ├── components/
│   │   ├── common/
│   │   │   ├── Navbar.jsx       # Responsive header, language switcher & profile pill
│   │   │   ├── Footer.jsx       # Helplines, verified links & academic disclaimer
│   │   │   ├── SuitabilityBadge.jsx # High / Medium / Low suitability pills
│   │   │   └── DisclaimerBanner.jsx # Transparency & prototype advisory banner
│   │   ├── wizard/
│   │   │   ├── Step1Personal.jsx      # Demographics, age, state/district, rural/urban
│   │   │   ├── Step2Business.jsx      # Occupation, sector, stage, registration
│   │   │   ├── Step3FinanceSupport.jsx# Requested finance, support type, SHG status
│   │   │   └── Step4Review.jsx        # Review, instant persona loader & submit
│   │   ├── discovery/
│   │   │   ├── SchemeCard.jsx         # Scheme card with score, why matched & portal link
│   │   │   └── FilterSidebar.jsx      # Multi-dimensional filter controls
│   │   └── dashboard/
│   │       ├── ApplicationTracker.jsx # Local milestone status changer & notes
│   │       └── MetricsCharts.jsx      # Recharts visualizations
│   └── pages/
│       ├── LandingPage.jsx      # Hero, features, demo personas & preview cards
│       ├── WizardPage.jsx       # 4-step interactive profile wizard with validations
│       ├── DiscoveryPage.jsx    # Ranked recommendations, search, filter & sort
│       ├── SchemeDetailPage.jsx # Full criteria, interactive doc checklist & next steps
│       ├── DashboardPage.jsx    # Profile summary, charts & local tracker
│       ├── AdminPage.jsx        # Unauthenticated demo scheme editor for evaluators
│       └── HelpGuidancePage.jsx # FAQs, document prep guide & scam avoidance advice
└── dist/                        # Production build artifacts
```

---

## 🛠️ Installation & Setup Instructions

### Prerequisites
- Node.js version 18.x or 20.x or 24.x
- npm version 9.x or above

### 1. Clone or Open Workspace
```bash
cd SchemeSathi
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Run Development Server
```bash
npm run dev
```
Open your browser and navigate to `http://localhost:5173`.

### 4. Build for Production
```bash
npm run build
```

### 5. Preview Production Build
```bash
npm run preview
```

---

## 🧪 Demo Scenarios & Quick Testing

To quickly test diverse marginalized entrepreneur profiles, use the **1-Click Demo Personas** available on the Landing Page, Wizard, or Dashboard:

1. **Anita Devi (Rural Woman Artisan & SHG Leader)**:
   - *Profile*: OBC, Female, Rural Gaya (Bihar), Handicraft artisan, SHG member, needs ₹50,000 – ₹2,00,000.
   - *Expected Matches*: Scores high on **DAY-NRLM (SVEP)** (bonus SHG points), **PM Vishwakarma** (artisan trade), and **MUDRA Shishu/Kishore**.

2. **Rajesh Solanki (Scheduled Caste Youth in Agro-Processing)**:
   - *Profile*: SC, Male, Rural Nagpur (Maharashtra), Planning stage for food processing, needs ₹10 – ₹25 Lakhs.
   - *Expected Matches*: Scores high on **CMEGP Maharashtra**, **Stand-Up India** (SC quota), **PMEGP**, and **NSFDC**.

3. **Sunita Patil (Urban Woman Entrepreneur - Bakery Expansion)**:
   - *Profile*: General, Female, Urban Pune (Maharashtra), Existing food processing expansion, needs ₹5 – ₹10 Lakhs.
   - *Expected Matches*: Scores high on **MUDRA Tarun**, **PMFME Food Processing**, and **Stand-Up India**.

4. **Manoj Valmiki (Sanitation Community Youth - Green Cleaning)**:
   - *Profile*: SC, Male, Urban Kanpur (UP), Idea stage services, needs ₹2 – ₹5 Lakhs.
   - *Expected Matches*: Scores high on **NSKFDC Assistance** and **PMEGP**.

---

## ⚖️ Transparent Rule-Based Scoring Formula

| Evaluation Factor | Weight | Criteria Evaluated |
| :--- | :---: | :--- |
| **Demographic Alignment** | 25% | Category (SC/ST/OBC/Minority/General) & Gender quotas |
| **Business Sector Match** | 20% | Direct activity match (manufacturing, food processing, crafts, services) |
| **Business Stage Alignment**| 15% | Greenfield (idea/planning) vs. brownfield (existing/expansion) |
| **Preferred Support Type** | 15% | Bank loan, capital subsidy, credit guarantee, training, market access |
| **Geographic Scope** | 10% | State-specific mandate (e.g. Maharashtra only) & Rural vs. Urban eligibility |
| **Financial Scale Alignment** | 10% | Requested funding fits within scheme min & max limits |
| **Special Factors** | 5% | Active Self Help Group (SHG) membership & age eligibility |

**Suitability Tiers:**
- **Potentially Suitable**: Score ≥ 75%
- **Needs Eligibility Verification**: Score between 50% and 74%
- **Likely Not Suitable**: Score < 50%

---

## ⚠️ Academic Prototype Limitations & Disclaimers

1. **Local Demo Only**: This is a frontend academic prototype. Application tracking is saved in the browser's `localStorage` and does not submit applications to real bank branches or government databases.
2. **Official Verification Required**: Scheme guidelines, interest subventions, and subsidy percentages change periodically based on state and union budgets. Users must verify current terms at official portals (`mudra.org.in`, `kviconline.gov.in`, `pmvishwakarma.gov.in`, etc.).
3. **No Financial Transactions**: SchemeSathi never charges money, guarantees loan approval, or acts as an agent.
#   S c h e m e S a t h i  
 