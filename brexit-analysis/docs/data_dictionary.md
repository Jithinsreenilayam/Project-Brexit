# Data Dictionary — Brexit Student Enrolment Analysis

All data sourced from HESA (Higher Education Statistics Agency), the official UK statutory body for higher education statistics. Data is publicly available and covers all UK Higher Education Institutions (HEIs).

---

## File Overview

| File | Records | Coverage | Primary Use |
|---|---|---|---|
| `ALL_EU.xlsx` | All UK HEIs | EU student enrolment, 2012/13–2022/23 | National EU trend analysis |
| `ALL_non_EU.xlsx` | All UK HEIs | Non-EU international enrolment, 2012/13–2022/23 | EU vs non-EU comparison |
| `eng_20 uni.xlsx` | Top 20 English HEIs | EU + non-EU breakdown by institution | Institution-level analysis |
| `NI_scot_wales uni.xlsx` | HEIs in NI, Scotland, Wales | Regional enrolment by institution | Regional impact analysis |

---

## Field Definitions

### `ALL_EU.xlsx` and `ALL_non_EU.xlsx`

| Column | Type | Description | Notes |
|---|---|---|---|
| `Institution` / `HEI Name` | String | Full name of the Higher Education Institution | Includes universities, colleges, and specialist HEIs |
| `UKPRN` | Integer | UK Provider Reference Number — unique HEI identifier | Assigned by UKRLP (UK Register of Learning Providers) |
| `Region` | String | UK region of the institution | England, Scotland, Wales, Northern Ireland |
| `2012/13` … `2022/23` | Integer | Student enrolment headcount for that academic year | Suppressed values shown as `..` (HESA convention for <5 students) |

### `eng_20 uni.xlsx`

| Column | Type | Description |
|---|---|---|
| `University` | String | Institution name |
| `EU [year]` | Integer | EU student headcount for that academic year |
| `Non-EU [year]` | Integer | Non-EU international student headcount |
| `Total [year]` | Integer | Total international student headcount |

### `NI_scot_wales uni.xlsx`

| Column | Type | Description |
|---|---|---|
| `Institution` | String | Institution name |
| `Country` | String | Scotland / Wales / Northern Ireland |
| `[year]` columns | Integer | EU student enrolment per academic year |

---

## Key Definitions

### EU Students
Students whose country of domicile is a European Union member state. Includes students from all 27 current EU member states. Historically also included students from countries that later left the EU (where applicable to pre-Brexit data).

- **Pre-2021:** EU students paid home fees (~£9,250/year in England) and could access student loans
- **Post-2021:** EU students classified as international — fees typically £15,000–£35,000+/year; no student loan access

### Non-EU International Students
Students whose country of domicile is outside the UK and EU. Largest sending countries in recent years: India, China, Nigeria, Pakistan, USA.

### Academic Year Format
All years use the UK academic year convention: `YYYY/YY` (e.g., `2021/22` = September 2021 to July 2022). The year column headers in the Excel files follow this format.

### Suppressed Values (`..`)
HESA suppresses enrolment figures below 5 students to protect individual privacy. In the analysis, suppressed values are treated as `NaN` and excluded from aggregations or imputed as 0 where appropriate.

---

## Data Limitations

1. **Headcount vs FTE:** HESA data uses headcount (number of individual students), not full-time equivalent (FTE). A part-time EU student counts the same as a full-time student.

2. **Domicile vs nationality:** The EU/non-EU classification is based on country of domicile (where the student was living before starting their course), not citizenship. A UK citizen living in France would be classified as EU-domiciled.

3. **Suppressed small values:** Institutions with fewer than 5 EU students in a given year have their figures suppressed. This primarily affects smaller and specialist HEIs.

4. **Institutional changes:** Some HEIs merged, closed, or changed names during 2012–2023. The datasets reflect these changes inconsistently; institutional-level trend analysis should be treated with caution for affected institutions.

5. **2022/23 completeness:** The most recent year's data may be provisional at the time of analysis. HESA typically revises figures in subsequent releases.

---

## Source & Licence

- **Publisher:** HESA (Higher Education Statistics Agency)
- **Website:** [https://www.hesa.ac.uk/data-and-analysis/students](https://www.hesa.ac.uk/data-and-analysis/students)
- **Licence:** Open Government Licence (OGL) — free to use with attribution
- **Citation format:** HESA, *Students by HE provider, country of HE provider and domicile*, [year], available from hesa.ac.uk

---

*For methodology and full findings, see `docs/findings_summary.md` and `reports/Impact_Of_Brexit.pdf`*
