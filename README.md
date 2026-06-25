# AmbitionBox Company Scraper

Extract, clean, and structure company information from AmbitionBox into an analysis-ready dataset using **Python**, **BeautifulSoup**, and **Pandas**.

> Built as a practical data engineering exercise covering web scraping, data cleaning, and feature engineering.

---

## Preview

| Company   | Rating | Industry                 | HQ        | Total Locations |
| --------- | ------ | ------------------------ | --------- | --------------: |
| TCS       | 3.3    | IT Services & Consulting | Bengaluru |             449 |
| Accenture | 3.7    | IT Services & Consulting | Bengaluru |             262 |
| HDFC Bank | 3.8    | Banking                  | Mumbai    |            1859 |

---

## Tech Stack

* Python
* Requests
* BeautifulSoup4
* Pandas
* lxml
* Jupyter Notebook

---

## Pipeline

```text
Website
   │
   ▼
HTTP Requests
   │
   ▼
HTML Parsing
   │
   ▼
Data Extraction
   │
   ▼
Raw Dataset
   │
   ▼
Data Cleaning
   │
   ▼
Feature Engineering
   │
   ▼
Clean Dataset
```

---

## Features

* Scrapes company data across multiple pages
* Handles pagination automatically
* Extracts structured company information
* Cleans missing and inconsistent values
* Splits semi-structured fields into meaningful features
* Exports a machine learning–ready CSV dataset

---

## Dataset

| Column          | Description                       |
| --------------- | --------------------------------- |
| Company         | Company name                      |
| Rating          | Overall company rating            |
| Industry        | Company domain                    |
| HQ              | Headquarters                      |
| Total Locations | Company presence across locations |
| Good Review     | Frequently appreciated aspects    |
| Bad Review      | Frequently reported concerns      |

---

## Feature Engineering

One of the preprocessing steps converts mixed text fields into structured features.

### Before

```text
IT Services & Consulting | Bengaluru +448 other locations
```

### After

```text
Industry          → IT Services & Consulting
HQ                → Bengaluru
Total Locations   → 449
```

This transformation makes the dataset significantly easier to analyze and suitable for downstream machine learning workflows.

---

## Repository Structure

```text
.
├── ambitionbox_scraper.ipynb
├── ambitionbox_2026_raw.csv
├── ambitionbox_2026_cleaned.csv
├── requirements.txt
├── .gitignore
└── README.md
```

---

## Getting Started

Clone the repository

```bash
git clone https://github.com/your-username/ambitionbox-company-scraper.git
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run

```text
ambitionbox_scraper.ipynb
```

---

## Roadmap

* [x] Multi-page web scraping
* [x] Data cleaning
* [x] Feature engineering
* [x] Clean CSV export
* [ ] Exploratory Data Analysis
* [ ] Interactive visualizations
* [ ] Streamlit dashboard
* [ ] Automated data refresh

---

## Learning Outcomes

This project was built to strengthen practical experience with:

* Web scraping
* HTML parsing
* Data preprocessing
* Feature engineering
* Dataset construction
* Pandas workflows

---

## Disclaimer

This project is intended for educational purposes only. Please respect AmbitionBox's Terms of Service and robots.txt when performing automated data collection.
