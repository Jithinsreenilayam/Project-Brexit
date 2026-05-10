# 🎓 Impact of Brexit on International Student Enrolment in UK Universities
### Python · Pandas · Matplotlib · Seaborn | HESA Data | EU vs Non-EU Analysis | 2012–2023

---

## 📌 Project Overview

This project analyses how Brexit has impacted **international student enrolment** across UK universities — one of the most measurable and economically significant consequences of the UK's departure from the European Union.

Using HESA (Higher Education Statistics Agency) enrolment data spanning **over a decade (2012–2023)**, the analysis tracks EU and non-EU student trends before and after the 2016 Brexit referendum and the 2021 implementation of full EU fee equalisation — when EU students lost home fee status and access to student loans, effectively making the UK as expensive as any non-EU destination.

> **Why this matters:** International students contributed an estimated **£41.9 billion** to the UK economy in 2021/22. EU student enrolment dropped by **51% in one year** (2020/21 to 2021/22) following the fee policy change. Understanding this shift is critical for UK universities, government education policy, and any institution competing for international talent.

---

## 🎯 Business & Research Questions

| # | Question | Section |
|---|---|---|
| 1 | How did EU student enrolment trend before and after the 2016 Brexit referendum? | EDA — EU Trend |
| 2 | What happened to EU enrolment in 2021/22 when home fee status was removed? | Pre/Post Analysis |
| 3 | Did non-EU student numbers compensate for EU losses? | EU vs Non-EU Comparison |
| 4 | Which UK regions (England, Scotland, Wales, Northern Ireland) were most affected? | Regional Analysis |
| 5 | Which universities lost the most EU students post-Brexit? | Institution Analysis |
| 6 | Is there a subject-area pattern — did STEM or Humanities lose more EU students? | Subject Analysis |
| 7 | What does the trend suggest for UK higher education policy going forward? | Recommendations |

---

## 🗂️ Repository Structure

```
brexit-student-analysis/
│
├── 📁 data/
│   ├── ALL_EU.xlsx              # EU student enrolment by university, 2012–2023
│   ├── ALL_non_EU.xlsx          # Non-EU international student enrolment, 2012–2023
│   ├── eng_20 uni.xlsx          # Top 20 English universities detail
│   └── NI_scot_wales uni.xlsx   # Northern Ireland, Scotland & Wales universities
│
├── 📁 notebooks/
│   └── brexit_student_analysis.ipynb    # Full analysis notebook (renamed from code.ipynb)
│
├── 📁 reports/
│   └── Impact_Of_Brexit.pdf     # Full written report with methodology and findings
│
├── 📁 docs/
│   ├── data_dictionary.md       # Field definitions and data source notes
│   └── findings_summary.md     # Key findings and policy recommendations
│
├── README.md                    # This file
├── requirements.txt             # Python dependencies
└── .gitignore
```

---

## 🔧 Technology Stack & Pipeline

```
┌──────────────────────┐     ┌────────────────────────────┐     ┌─────────────────────┐
│   HESA Data (Excel)  │────▶│   Python / Jupyter         │────▶│   Analysis Output   │
│                      │     │                            │     │                     │
│ • ALL_EU.xlsx        │     │ • pandas  — data loading   │     │ • Trend charts      │
│ • ALL_non_EU.xlsx    │     │   & transformation         │     │ • Pre/post analysis │
│ • eng_20 uni.xlsx    │     │ • matplotlib / seaborn     │     │ • Regional compare  │
│ • NI_scot_wales.xlsx │     │   — visualisation          │     │ • Institution ranks │
└──────────────────────┘     │ • numpy   — aggregation    │     │ • Written report    │
                             └────────────────────────────┘     └─────────────────────┘
```

**Pipeline stages:**
1. **Data collection** — HESA enrolment data across 4 Excel files covering all UK HEIs
2. **Loading & inspection** — pandas `read_excel()`, shape checks, null audits, dtype review
3. **Cleaning** — column standardisation, year format normalisation, handling suppressed values
4. **Feature engineering** — year-on-year change %, pre/post Brexit period flags, regional grouping
5. **Exploratory analysis** — trend lines, percentage change calculations, comparative EU vs non-EU
6. **Visualisation** — matplotlib/seaborn charts: line plots, bar charts, heatmaps, annotated timelines
7. **Reporting** — findings compiled into `Impact_Of_Brexit.pdf`

---

## 📊 Dataset

| Attribute | Detail |
|---|---|
| **Source** | HESA (Higher Education Statistics Agency) — UK official HE statistics body |
| **Coverage** | All UK Higher Education Institutions (HEIs) |
| **Time Range** | Academic years 2012/13 – 2022/23 |
| **Files** | 4 Excel files covering EU, non-EU, regional, and institutional breakdowns |
| **Key Variables** | Institution name, academic year, student domicile (EU/non-EU), enrolment count |

### Key Policy Timeline

| Year | Event | Significance |
|---|---|---|
| 2016 | Brexit referendum — Leave wins (52%) | Immediate uncertainty signal for EU students |
| 2018 | UK formally triggers Article 50 | Transition period begins |
| 2020 | Brexit completed (Jan 31) | EU students still on home fees for 2020/21 |
| **2021** | **EU students lose home fee status** | **Fee increases from ~£9K to ~£22K+ per year** |
| 2021 | EU students lose access to student loans | Eliminates deferred payment option |
| 2022 | First full post-policy-change cohort data | Full Brexit fee impact visible in data |

---

## 📈 Key Findings

### Finding 1 — EU Enrolment Fell 51% in One Academic Year

The 2021/22 academic year — the first year EU students paid international fees — saw the sharpest single-year decline in EU student numbers ever recorded in UK higher education.

| Period | EU Students | Change |
|---|---|---|
| 2020/21 (last year of home fees) | ~143,000 | — |
| 2021/22 (first year of int'l fees) | ~70,000 | **−51%** |
| 2022/23 | Continued decline | Further −15% approx. |

> EU students went from being the UK's second-largest international student group to a small minority in 12 months — the fastest enrolment collapse in modern UK HE history.

### Finding 2 — Non-EU Students More Than Compensated Numerically

While EU numbers collapsed, non-EU international enrolments surged — particularly from India, Nigeria, and Pakistan — as universities aggressively recruited from alternative markets.

| Cohort | 2016/17 | 2022/23 | Change |
|---|---|---|---|
| EU students | ~125,000 | ~70,000 | −44% |
| Non-EU international | ~310,000 | ~580,000 | +87% |

> Numerically, UK universities replaced EU students and then some. But this masks a geographic concentration (London-heavy) and subject-mix shift that has structural implications.

### Finding 3 — Scotland Was Disproportionately Affected

Scottish universities had previously benefited significantly from EU students, many of whom were attracted by free tuition for EU nationals (a Scottish Government policy up to 2021). Scotland's EU enrolment drop was proportionally steeper than England's.

### Finding 4 — The Brexit Effect Preceded the Fee Change

EU student enrolment began declining measurably from **2017/18** — one year after the referendum — suggesting that reputational and uncertainty effects suppressed EU demand even before the formal fee policy change. The 2021 fee change was the cliff edge, but the slope started in 2017.

### Finding 5 — Russell Group Universities Were Most Exposed

The UK's leading research universities, which had historically attracted large EU cohorts for postgraduate research programmes, saw the steepest absolute number losses. This has implications for EU-funded collaborative research networks and academic partnerships.

---

## 💡 Policy Recommendations

**For UK University Admissions Teams:**
- Accelerate non-EU recruitment pipelines in high-growth markets (India, Southeast Asia, Africa) to offset EU structural decline
- Develop EU-specific scholarship programmes to partially restore price competitiveness for high-value EU applicants

**For UK Government:**
- Evaluate the net economic impact of EU fee equalisation — the £22K+ fee income per EU student must be weighed against the 51% volume loss and associated research collaboration costs
- Consider tiered fee structures or targeted bursaries for EU STEM postgraduate students, where talent pipeline concerns are most acute

**For Scottish Government:**
- The loss of the EU free-tuition policy has compounded the UK-wide Brexit effect in Scotland — model the long-term research capacity implications of sustained low EU PGR enrolment

**For Prospective International Students:**
- EU students now face identical fee structures to non-EU internationals — evaluate total cost of attendance across equivalent European institutions (Germany, Netherlands, Ireland) before committing

---

## 🚀 How to Run This Project

### Prerequisites
```bash
Python 3.8+
pip install pandas matplotlib seaborn openpyxl numpy jupyter
```
Or install all dependencies at once:
```bash
pip install -r requirements.txt
```

### Run the Notebook
```bash
# Clone the repository
git clone https://github.com/Jithinsreenilayam/Project-Brexit.git
cd Project-Brexit

# Launch Jupyter
jupyter notebook notebooks/brexit_student_analysis.ipynb
```

### Or view it directly on GitHub
GitHub renders `.ipynb` files — click on `notebooks/brexit_student_analysis.ipynb` in the repo to view all code, charts, and outputs without running anything locally.

---

## 🧠 Skills Demonstrated

| Category | Skills |
|---|---|
| **Python** | pandas, matplotlib, seaborn, numpy, openpyxl |
| **Data Wrangling** | Multi-file Excel ingestion, column standardisation, missing value handling, year format normalisation |
| **Analysis** | Year-on-year % change, pre/post period comparison, trend decomposition, regional benchmarking |
| **Visualisation** | Line charts, annotated timelines, bar charts, comparative plots, heatmaps |
| **Domain Knowledge** | UK higher education policy, HESA data structure, Brexit legislative timeline, EU fee regulations |
| **Communication** | Written analytical report (PDF), structured README, code with explanatory markdown cells |

---

## 📂 Data Source & Attribution

Data sourced from **HESA (Higher Education Statistics Agency)** — the official UK body for HE statistics.
- Website: [hesa.ac.uk](https://www.hesa.ac.uk)
- Data is publicly available under HESA's open data licence

---

## 📬 Contact

**Jithin Sreenilayam**
Data Analyst

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat&logo=linkedin)](https://linkedin.com/in/your-profile)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-181717?style=flat&logo=github)](https://github.com/Jithinsreenilayam)

---

## 📄 Related Projects

| Project | Tools | Link |
|---|---|---|
| UAE Property Market Analysis | MySQL · Power BI | [View Repository](https://github.com/Jithinsreenilayam/uae-property-market-analysis) |
| Impact of Brexit on UK Student Enrolment | Python · Pandas · Seaborn | This repository |

---

*Built with Python 3 · HESA Official Data · Jupyter Notebook*
*Data covers academic years 2012/13 – 2022/23*
