<div align="center">

#  AmbitionBox Company Scraper

**Extract · Clean · Analyze**

*A practical data engineering pipeline that scrapes, structures, and prepares company data from AmbitionBox for downstream analysis and machine learning.*

<br/>

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup4-Parsing-59666C?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Wrangling-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-Educational-green?style=for-the-badge)

</div>

---

## 📌 What This Does

Scrapes structured company data across multiple pages of AmbitionBox, cleans and engineers features from raw HTML, and exports a machine-learning-ready CSV — all from a single Jupyter notebook.

---

##  Dataset Preview

| Company | Rating | Industry | HQ | Total Locations |
|:--------|:------:|:---------|:---|----------------:|
| TCS | ⭐ 3.3 | IT Services & Consulting | Bengaluru | 449 |
| Accenture | ⭐ 3.7 | IT Services & Consulting | Bengaluru | 262 |
| HDFC Bank | ⭐ 3.8 | Banking | Mumbai | 1,859 |

<details>
<summary> Full column reference</summary>

<br/>

| Column | Type | Description |
|:-------|:----:|:------------|
| `Company` | `str` | Company name |
| `Rating` | `float` | Overall employee rating |
| `Industry` | `str` | Company domain / sector |
| `HQ` | `str` | Headquarters city |
| `Total Locations` | `int` | Offices across all locations |
| `Good Review` | `str` | Frequently appreciated aspects |
| `Bad Review` | `str` | Frequently reported concerns |

</details>

---

##  Pipeline

```
 ╔══════════════════╗
 ║    AmbitionBox   ║  ← Source Website
 ╚════════╤═════════╝
          │  HTTP Requests (pagination-aware)
          ▼
 ╔══════════════════╗
 ║   HTML Parsing   ║  ← BeautifulSoup4 + lxml
 ╚════════╤═════════╝
          │  Raw structured extraction
          ▼
 ╔══════════════════╗
 ║   Raw Dataset    ║  → ambitionbox_2026_raw.csv
 ╚════════╤═════════╝
          │  Cleaning · Null handling · Type casting
          ▼
 ╔══════════════════╗
 ║ Feature Engineer ║  ← Split mixed fields into atomic columns
 ╚════════╤═════════╝
          │
          ▼
 ╔══════════════════╗
 ║  Clean Dataset   ║  → ambitionbox_2026_cleaned.csv 
 ╚══════════════════╝
```

---

## 🔧 Feature Engineering Spotlight

Raw text fields from the site are semi-structured. This step parses them into clean, typed columns.

**Before**
```
IT Services & Consulting | Bengaluru +448 other locations
```

**After**
```
Industry          →  "IT Services & Consulting"   (str)
HQ                →  "Bengaluru"                  (str)
Total Locations   →  449                          (int)
```

> This single transformation makes the dataset joinable, filterable, and ready for clustering or regression workflows.

---

##  Getting Started

**1. Clone**
```bash
git clone https://github.com/your-username/ambitionbox-company-scraper.git
cd ambitionbox-company-scraper
```

**2. Install dependencies**
```bash
pip install -r requirements.txt
```

**3. Run**
```bash
jupyter notebook ambitionbox_scraper.ipynb
```

---

## 📁 Repository Structure

```
ambitionbox-company-scraper/
│
├── 📓 ambitionbox_scraper.ipynb     # Full scraping + cleaning pipeline
├── 📄 ambitionbox_2026_raw.csv      # Unprocessed scraped data
├── ✅ ambitionbox_2026_cleaned.csv  # ML-ready cleaned dataset
├── 📦 requirements.txt
├── 🚫 .gitignore
└── 📖 README.md
```

---

##  Roadmap

| Status | Milestone |
|:------:|:----------|
| ✅ | Multi-page web scraping |
| ✅ | Data cleaning & null handling |
| ✅ | Feature engineering |
| ✅ | Clean CSV export |
| 🔲 | Exploratory Data Analysis |
| 🔲 | Interactive visualizations |
| 🔲 | Streamlit dashboard |
| 🔲 | Automated data refresh |

---

##  Skills Practiced

<details>
<summary>Expand</summary>

<br/>

- **Web Scraping** — navigating paginated HTML with `requests` + `BeautifulSoup4`
- **HTML Parsing** — targeting CSS selectors and tag hierarchies in real-world markup
- **Data Cleaning** — handling nulls, type coercion, inconsistent formatting
- **Feature Engineering** — splitting semi-structured strings into machine-usable columns
- **Dataset Construction** — building reproducible, analysis-ready CSVs
- **Pandas Workflows** — chaining transforms, applying functions, exporting artifacts

</details>

---

##  Disclaimer

This project is for **educational purposes only**. Please review and respect [AmbitionBox's Terms of Service](https://www.ambitionbox.com/terms-and-conditions) and `robots.txt` before running any automated data collection.

---

<div align="center">

Made with  curiosity and  Python

</div>