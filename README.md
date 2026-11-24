# AeroMitra — Family & Community Smog Navigator

**AeroMitra** is a GenAI-powered web application designed to help families, vulnerable household members, and local communities navigate severe winter smog and urban air pollution episodes. Built as a zero-build, single-page application powered by **Google Gemini (`gemini-3-flash-preview`)**, it transforms local Air Quality Index (AQI) levels, diurnal meteorology, and household lifestyle factors into concrete, science-backed daily actions.

---

## Core Modules & Capabilities

### 1. Location, Smog Severity & Household Lifestyle Profiler
- **Microclimate & AQI Calibration:** Supports custom city/neighborhood entry alongside regional presets (*Kalyan MMR*, *Delhi NCR*, *Mumbai Suburbs*, *Lahore*, *London*) and an interactive **50–500 AQI** slider with real-time PM2.5 estimation and boundary-layer inversion notes.
- **Household Vulnerability Mapping:** Tailors guidance for **Kids / Toddlers**, **Elderly / Seniors**, **Asthma / Respiratory Sensitivity**, and **Pets**.
- **Home & Commute Context:** Accounts for dwelling type (*Apartment* vs. *Independent House*), cooking fuel (*Gas Stove*, *Electric / Induction*, *Space Heater / Fireplace*), and daily transit mode (*Car*, *Two-Wheeler*, *Public Transit*, *Work From Home*).
- **Structured GenAI Action Plan:** Uses Gemini's structured JSON output schema to generate personalized recommendations across three pillars—**Low-Emission Daily Routine**, **Indoor Air Quality (IAQ) Hacks**, and **Sustainable Alternatives & Community Actions**—each paired with a **Direct Impact & Why It Works** breakdown.

### 2. Safe Ventilation Window Predictor
- **24-Hour Diurnal Inversion & Indoor CO2 Engine:** Models hourly outdoor AQI, surface wind speed (km/h), and indoor CO2 accumulation (ppm) based on household occupancy and stove type.
- **Interactive 24-Hour SVG Chart & Scrubber:** Inspect any hour of the day to receive real-time **GREEN** (*Optimal Cross-Ventilation*), **AMBER** (*Brief Kitchen Exhaust Only*), or **RED** (*Seal Windows & Recirculate*) directives.
- **20-Minute Purge Countdown Timer & Protocol:** Built-in timer and four-step checklist reminding households to pause HEPA purifiers during brief afternoon window openings and run them on High immediately after resealing.

### 3. Family Symptom & Exposure Correlation Tracker
- **Daily Check-In Logger:** Tracks family member, date, daily AQI exposure, multi-select symptom chips, severity level, rescue inhaler/nebulizer usage, and clinical notes with browser `localStorage` persistence.
- **Personal AQI Trigger Threshold Detection:** Automatically calculates each member's personal AQI symptom threshold and compares clear-day vs. symptomatic-day AQI averages.
- **Timeline Visualization & Doctor Export:** Renders a color-coded daily exposure bar chart, provides one-click **Copy Doctor / Pediatrician Summary**, and integrates **Gemini AI Pattern Analysis** to highlight exposure-symptom correlations.

### 4. Interactive Daily Impact Simulator & Habit Tracker
Toggle seven high-impact daily habits (HEPA recirculation, range-hood exhaust, wet mopping, transit shifts, clean heating, N95 fit-checks, and community anti-burning advocacy) to simulate real-time changes in:
- **Family Lung Protection Score (0–100)**
- **Estimated Indoor PM2.5 Reduction (%)**
- **Weekly CO2 & Particulates Avoided**
- **30-Day Winter Month Projection**

### 5. GenAI Family & Community Advisor Chat
- Context-aware conversational assistant automatically synced with your active location, AQI reading, and household profile.
- Includes one-click prompts for school-commute protection, kitchen emission control, and drafting polite Resident Welfare Association (RWA) anti-burning notices.

### 6. Full-Interface Dark Mode & Responsive Design
- Persistent Light/Dark theme switcher (`localStorage` + `prefers-color-scheme` detection) with theme-aware SVG charts and gauges.

---

## Tech Stack & Architecture
- **Frontend:** Vanilla HTML5, ES6+ JavaScript, Tailwind CSS (CDN), Lucide Icons
- **Visualization:** Custom theme-aware inline SVG charts and circular gauges (zero external charting dependencies)
- **AI Engine:** Google Gemini REST API (`gemini-3-flash-preview`) with structured `responseSchema` generation and multi-turn conversational context
- **Persistence:** Client-side `localStorage` for symptom logs and UI theme preferences

---

## Local Setup & Running the App
1. **Clone the repository:**
   ```bash
   git clone https://github.com/<your-username>/aeromitra.git
   cd aeromitra
   ```
2. **Configure your Gemini API Key:**
   - Obtain a free API key from [Google AI Studio](https://aistudio.google.com/).
   - Open `index.html` and set your key in the `apiKey` variable inside the `<script>` block when running locally.
   - **Security Note:** Never commit a hardcoded personal API key to a public GitHub repository. If deploying publicly on GitHub Pages, restrict your API key's HTTP referrers in Google Cloud Console or prompt the user for a key in `localStorage`.
3. **Launch locally:** Open `index.html` directly in any modern browser, or serve it locally with `npx serve .`.

---

## Deploying Live with GitHub Pages
1. Push this repository to GitHub.
2. Go to **Settings → Pages** in your GitHub repository.
3. Under **Build and deployment**, set **Source** to `Deploy from a branch`, select `main` and `/ (root)`, and click **Save**.
4. Your live app will be available at `https://<your-username>.github.io/aeromitra/`.

---

## Roadmap
- [ ] Live station AQI & pollutant breakdown (PM2.5, PM10, NO2) via OpenAQ / WAQI APIs
- [ ] Room CADR & DIY Corsi-Rosenthal box sizing calculator
- [ ] Multilingual RWA & school smog bulletin poster generator (Hindi, Marathi, Punjabi, Bengali)

## License
Distributed under the MIT License. See `LICENSE` for more information.
