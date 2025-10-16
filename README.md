# Hospital-Experience-Dashboard-From-Patient-Survey-Star-Rating-Regression-1-5-
# HCAHPS Patient Experience Dashboard (Tableau)

An interactive Tableau dashboard exploring **Patient Survey Star Rating (1–5)** by **state**, **hospital ownership**, and **emergency service availability** using CMS Hospital General Information and HCAHPS data.

> **Compliance:** No PHI/PII. Raw files are not committed. This repo hosts the Tableau workbook, Prep flow, documentation, and screenshots.

---

## 🎯 Objectives
- Visualize geographic and ownership patterns in HCAHPS patient-experience ratings.
- Enable decision makers to segment hospitals by **state/region**, **ownership**, and **emergency services**.
- Provide “what-if” comparisons (e.g., ownership mix) via interactive filters and parameters.

## 🧰 Tools
- **Tableau Desktop** (dashboard authoring)
- **Tableau Prep** (data cleaning, joins, calculated fields)
- (Optional) Excel/CSV as source files
  
> Save your **Tableau workbook as `.twbx`** so the visualizations open with embedded extracts (no local paths required). Keep real/raw CMS exports **outside** Git.

## 📊 Data Sources
- CMS Hospital General Information
- HCAHPS (Hospital Consumer Assessment of Healthcare Providers and Systems)
- Join keys used in Prep: hospital identifier(s) as available in the public files (documented in the Prep flow).

## 🧹 Data Cleaning (Tableau Prep Summary)
- **Standardized fields:** state, ownership type, emergency services (Yes/No).
- **Joins:** HCAHPS ↔ Hospital General Info (inner join on hospital ID).
- **Filters:** removed closed/duplicate facilities and obviously invalid ratings.
- **Derived fields:** region (from state), ownership groupings, rating bins.
- **Output:** clean extract published to the packaged workbook.

## 📈 Dashboard Contents
- **Overview:** KPI tiles (avg star rating, # hospitals), trend/summary.
- **Map by State/Region:** choropleth with tooltip details and drill-through.
- **Ownership Comparison:** bars/box plots comparing ratings by ownership.
- **Emergency Services Lens:** split by emergency service availability.
- **“What-if” panel:** parameters/filters to simulate ownership mix views.

### Interactions
- Global filters: State/Region, Ownership, Emergency Services, Rating range
- Click-to-highlight between views; tooltips with definitions and counts

## 🔍 Calculated Fields (examples you can adapt)
- **Region (US)**  
  `IF [State] IN ("ME","NH","VT","MA","RI","CT","NY","NJ","PA") THEN "Northeast"
   ELSEIF [State] IN ("IL","IN","MI","OH","WI","IA","KS","MN","MO","NE","ND","SD") THEN "Midwest"
   ELSEIF [State] IN ("DE","FL","GA","MD","NC","SC","VA","DC","WV","AL","KY","MS","TN") THEN "South"
   ELSE "West" END`
- **Emergency Services (Bool)**  
  `IF LOWER([Emergency Services]) = "yes" THEN TRUE ELSE FALSE END`

## ✅ How to Open
1. Download `workbook/hcahps_patient_experience.twbx`.
2. Double-click to open in **Tableau Desktop**.
3. If extracts are stale, click **Data → Refresh All Extracts**.

## 🧭 Usage Notes for Stakeholders
- Use **filters** to focus on target states or ownership types.
- Hover over points/bars for detail; select bars or map areas to cross-filter.
- The **What-if** panel helps compare ownership categories side-by-side.

## 📜 Data Dictionary 
- Field names, definitions, allowed values, and any transformations applied.

## 🔐 Governance
- No PHI/PII or credentials in the repo.
- Raw CMS dumps are kept off-repo (secure storage).
- GitHub issues track enhancements/bugs; versions tagged by release.

## 📄 License
MIT (for this workbook and documentation; data remains property of CMS/public sources)

## 🙌 Acknowledgments
Thanks to CMS for public datasets and reviewers for dashboard feedback.

## References

Centers for Medicare & Medicaid Services. (n.d.). *Hospital General Information* [Data set]. U.S. Department of Health & Human Services. https://<exact-link-you-used>

Centers for Medicare & Medicaid Services. (2025). *HCAHPS – Patient Survey Star Ratings* [Data set]. U.S. Department of Health & Human Services. https://<exact-link-you-used>

Boyce, D. (n.d.). *Typography and dashboards in Tableau* [Class handout]. ADTA 5250, University of North Texas.

Centers for Medicare & Medicaid Services. (Year). *Centers for Medicare and Medicaid Services logo* [Logo]. Wikimedia Commons. https://<logo-page-url>
License: <CC BY/CC BY-SA/etc.> — provide the license name, link, original author/uploader, and note if you made any changes.

