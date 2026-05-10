# GitHub Repository Update Guide
## How to Rework Project-Brexit into a Professional Repository

This guide walks you through every step needed to transform your existing
`Project-Brexit` repository into a professional data analyst portfolio piece.

---

## WHAT NEEDS TO CHANGE

### Current state (problems):
- ❌ No README.md — the repo homepage is completely blank
- ❌ Files dumped in root with no folder structure
- ❌ Notebook named `code.ipynb` — generic, unprofessional
- ❌ Excel files have inconsistent naming (`NI_scot_wales uni.xlsx` has a space)
- ❌ No requirements.txt — nobody can reproduce your environment
- ❌ No documentation explaining the data, findings, or methodology
- ❌ Repository name `Project-Brexit` looks like a student submission

### Target state (professional):
- ✅ Rich README with pipeline diagram, findings table, badges
- ✅ Clean folder structure: data/ notebooks/ reports/ docs/
- ✅ Notebook renamed: `brexit_student_analysis.ipynb`
- ✅ Data files in `data/` folder with consistent naming
- ✅ `requirements.txt` for environment reproducibility
- ✅ Full documentation: data dictionary + findings summary
- ✅ Repository renamed to `brexit-student-analysis`

---

## STEP-BY-STEP INSTRUCTIONS

---

### STEP 1 — Rename the Repository

A professional repo name uses lowercase with hyphens, not `Project-Brexit`.

1. Go to your repo: https://github.com/Jithinsreenilayam/Project-Brexit
2. Click **Settings** tab (top of the repo, next to Insights)
3. Under **General → Repository name**, change from:
   `Project-Brexit` → `brexit-student-analysis`
4. Click **Rename**

GitHub automatically redirects old links to the new name — nothing breaks.

---

### STEP 2 — Update the Repository Description & Topics

Still in **Settings → General**:

**Description field**, replace with:
```
Analysis of Brexit's impact on EU international student enrolment in UK universities | Python · Pandas · Matplotlib · HESA Data | 2012–2023
```

**Topics** (click the ⚙️ gear on the main repo page, not Settings):
```
python  data-analysis  brexit  uk-education  pandas  matplotlib  seaborn
jupyter-notebook  hesa  higher-education  international-students  data-visualization
```

**Website field**: Leave blank for now (add your LinkedIn or portfolio URL later)

---

### STEP 3 — Create the New Folder Structure

You need to reorganise files into folders. GitHub's web interface can do this.

#### Create the `data/` folder and move Excel files:

1. On your repo homepage, click **Add file → Create new file**
2. In the filename box, type: `data/.gitkeep`
   (This creates the `data/` folder — GitHub requires at least one file per folder)
3. Scroll down, write commit message: `Add data folder structure`
4. Click **Commit new file**

Repeat for the other folders:
- `notebooks/.gitkeep`
- `reports/.gitkeep`
- `docs/.gitkeep`

#### Move the Excel files into `data/`:

For each Excel file (`ALL_EU.xlsx`, `ALL_non_EU.xlsx`, `eng_20 uni.xlsx`, `NI_scot_wales uni.xlsx`):

1. Click the file in your repo
2. Click the **pencil edit icon** (top right of file view) → then click the **three dots (…)** → **Move file**
   *OR*: Click the file → click **...** → **Move to folder**
3. Change the path from `ALL_EU.xlsx` to `data/ALL_EU.xlsx`
4. Commit with message: `Move data files into data/ folder`

> **Easier alternative:** Do Steps 3 and 4 together using Git on your computer (see Step 7 below for the Git command-line approach).

---

### STEP 4 — Rename the Notebook

1. In your repo, click on `code.ipynb`
2. Click **…** (three dots, top right) → **Rename file**
3. Change to: `notebooks/brexit_student_analysis.ipynb`
   (This both renames AND moves it into the notebooks folder)
4. Commit: `Rename and move notebook to notebooks/`

---

### STEP 5 — Upload the New Files

You need to upload these files that are provided in your download package:

#### Upload README.md (replaces existing or creates new):
1. On repo homepage → **Add file → Upload files**
2. Drag `README.md` from your download
3. Commit message: `Add professional README with pipeline, findings, and documentation`
4. Click **Commit changes**

#### Upload docs/ files:
1. **Add file → Upload files**
2. Before dropping files, click into the `docs/` folder first
3. Upload:
   - `data_dictionary.md`
   - `findings_summary.md`
4. Commit: `Add data dictionary and findings summary documentation`

#### Upload requirements.txt:
1. Back at root → **Add file → Upload files**
2. Upload `requirements.txt`
3. Commit: `Add Python requirements file`

#### Upload .gitignore:
1. Same process — upload `.gitignore` to root
2. Commit: `Add gitignore for Python/Jupyter project`

---

### STEP 6 — Add Notebook Section Headers (Important!)

Open `brexit_student_analysis.ipynb` in Jupyter on your computer. Add proper markdown headers between your code cells. A professional notebook reads like a structured report, not a raw script.

Add these markdown cells at the start and between sections:

```markdown
# Impact of Brexit on International Student Enrolment in UK Universities
## Python Analysis | HESA Data | 2012–2023

**Author:** Jithin Sreenilayam
**Date:** [Your date]
**Data Source:** HESA (Higher Education Statistics Agency)

---

### Research Questions
This analysis addresses the following questions:
1. How did EU student enrolment change before and after Brexit?
2. What happened when EU students lost home fee status in 2021?
3. Did non-EU numbers compensate for EU losses?
4. Which regions and universities were most affected?
```

Then between each section of analysis, add a markdown cell like:

```markdown
---
## Section 1 — Data Loading & Inspection
Loading all four HESA datasets and performing initial data quality checks.
```

```markdown
---
## Section 2 — EU Enrolment Trend Analysis (2012–2023)
Visualising the long-run EU student trajectory with key policy events annotated.
```

```markdown
---
## Section 3 — Pre vs Post Brexit: The 2021 Fee Change Impact
Comparing EU enrolment before and after the removal of home fee status.
```

```markdown
---
## Section 4 — EU vs Non-EU Comparison
Did non-EU growth compensate for EU losses numerically and structurally?
```

```markdown
---
## Section 5 — Regional Analysis
How differently did England, Scotland, Wales, and Northern Ireland experience the Brexit effect?
```

```markdown
---
## Section 6 — Institutional Analysis
Which universities lost the most EU students? Top 20 English universities breakdown.
```

```markdown
---
## Section 7 — Key Findings & Conclusions
Summary of findings with policy implications.
```

After adding these headers, re-upload the notebook to GitHub.

---

### STEP 7 — Alternative: Do Everything via Git (Faster)

If you're comfortable with Git, this is faster than the web interface:

```bash
# Clone your repo
git clone https://github.com/Jithinsreenilayam/Project-Brexit.git
cd Project-Brexit

# Create folder structure
mkdir data notebooks reports docs

# Move files into correct folders
mv ALL_EU.xlsx data/
mv ALL_non_EU.xlsx data/
mv "eng_20 uni.xlsx" data/eng_20_uni.xlsx        # Also fix the space in filename
mv "NI_scot_wales uni.xlsx" data/NI_scot_wales_uni.xlsx
mv code.ipynb notebooks/brexit_student_analysis.ipynb
mv Impact_Of_Brexit.pdf reports/

# Add new files (copy from your download package)
cp /path/to/download/README.md .
cp /path/to/download/requirements.txt .
cp /path/to/download/.gitignore .
cp /path/to/download/docs/data_dictionary.md docs/
cp /path/to/download/docs/findings_summary.md docs/

# Stage and commit all changes
git add .
git commit -m "Restructure repository: add README, docs, organised folder layout, rename notebook"
git push origin main
```

---

### STEP 8 — Pin the Repository to Your GitHub Profile

1. Go to your GitHub profile: https://github.com/Jithinsreenilayam
2. Click **Customize your profile** (pencil icon)
3. Click **Pin a repository**
4. Select both:
   - `brexit-student-analysis`
   - `uae-property-market-analysis` (if you've uploaded it)
5. Save

Now when any recruiter or hiring manager visits your GitHub profile, these two projects are the first things they see.

---

## LINKEDIN POST FOR THIS PROJECT

```
📊 Project: Quantifying Brexit's impact on UK university enrolment — with data.

EU students lost home fee status in 2021. The result:

📉 51% collapse in EU student enrolment in a single academic year
📈 87% growth in non-EU international enrolment to compensate
📍 Scotland hit hardest — lost both the UK-wide EU fee structure AND
   Scotland's unique free-tuition policy for EU nationals
🎓 Russell Group PGR pipeline at risk — EU PhD students most sensitive
   to the fee tripling (3–4 year programmes = highest total cost impact)

I analysed HESA (Higher Education Statistics Agency) data across all UK
universities from 2012 to 2023 to trace exactly when and how the Brexit
effect manifested — and the data shows the EU decline started in 2017
(the year after the referendum), not in 2021 when fees changed.

The 2021 fee change was the cliff edge. The slope started in 2017.

Tools: Python · Pandas · Matplotlib · Seaborn · Jupyter
Data: HESA official UK HE statistics

📂 Full analysis on GitHub: [link]

#Brexit #DataAnalysis #Python #HigherEducation #UKUniversities
#DataVisualization #Pandas #HESA #EUStudents
```

---

## FINAL CHECKLIST

Before considering this repo complete, verify:

- [ ] Repository renamed to `brexit-student-analysis`
- [ ] README.md is visible on the repo homepage (rendered, not raw)
- [ ] All Excel files are in the `data/` folder
- [ ] Notebook is in `notebooks/` folder and named `brexit_student_analysis.ipynb`
- [ ] PDF report is in `reports/` folder
- [ ] `docs/data_dictionary.md` is present
- [ ] `docs/findings_summary.md` is present
- [ ] `requirements.txt` is in the root
- [ ] `.gitignore` is in the root
- [ ] Notebook has proper markdown section headers (not just bare code cells)
- [ ] Repository topics/tags are set (python, brexit, pandas, etc.)
- [ ] Repository description is updated
- [ ] Repo is pinned to your GitHub profile

---

## CV LINE FOR THIS PROJECT

```
Brexit Impact on UK International Student Enrolment          [GitHub Link]
Data Analysis | Python · Pandas · Matplotlib · Seaborn

• Analysed HESA data across all UK HEIs (2012–2023) to quantify Brexit's impact
  on EU and non-EU student enrolment patterns

• Identified a 51% single-year collapse in EU enrolment following 2021 home-fee
  removal, and a pre-referendum shadow effect beginning in 2017/18

• Conducted regional analysis across England, Scotland, Wales, and Northern Ireland,
  finding Scottish universities disproportionately affected due to the dual loss of
  home fees and Scotland's free-tuition policy for EU nationals

Skills: Python · Pandas · Matplotlib · Seaborn · Jupyter · HESA data · Higher Education policy
```
