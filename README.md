
# NGWATA Results — KJSEA 2025 Scraper ✅

## Overview

Ngwata Primary has a total of **484 students**. Fetching each student's KJSEA 2025 results manually is time-consuming, so this repository automates the process using Python, **Selenium**, and **pandas**. The automation reads student assessment numbers and names from an Excel file, visits the KJSEA results site, submits the required details for each student, scrapes their subject points, and saves the combined results to a new Excel file.

Website used: https://kjsea.knec.ac.ke

## Key Features

- Reads student data from `students.xlsx` into a `pandas` DataFrame
- Automates Firefox with `selenium.webdriver` to load the results page
- Inputs assessment number and name, checks the consent box, and searches
- Scrapes points for each subject (e.g., English, Kiswahili, Mathematics, Integrated Science, Agriculture, SST, CRE, Creative Arts & Sports, Pre-technical Studies)
- Loops through all students and writes results to `students_results.xlsx`

## Files of Interest

- `students.ipynb` — the Jupyter Notebook that contains the full scraping workflow
- `students.xlsx` — input spreadsheet with columns `ASS. NO:` and `NAME` (kept out of the repo via `.gitignore`) ⚠️
- `students_results.xlsx` — generated output spreadsheet (also ignored via `.gitignore`)
- `.gitignore` — includes `students.xlsx` and `students_results.xlsx` to protect student data/privacy

## Prerequisites

- Python 3.10 (or compatible)
- Firefox browser installed
- `geckodriver` available on PATH (for `webdriver.Firefox()` to work)
- Recommended Python packages:

```bash
python -m venv ngwatavenv
source ngwatavenv/bin/activate
pip install selenium pandas openpyxl
```

(Optional: add `webdriver-manager` if you prefer automatic driver management.)

## Usage

1. Clone the repository:

```bash
git clone https://github.com/Erickpython/NGWATA-RESULTS.git
cd NGWATA-RESULTS
```

2. Prepare your `students.xlsx` file with the columns `ASS. NO:` and `NAME` (this file is ignored by `.gitignore` for privacy).

3. Open `students.ipynb` with Jupyter and run the notebook cells, or run the equivalent script that uses the same logic. The notebook does the following:

	- Launches Firefox via Selenium
	- Navigates to `https://kjsea.knec.ac.ke`
	- For each student: inputs assessment number and name, checks the consent box, clicks the search button (uses JavaScript click to avoid interception), waits for the results table, extracts subject points and saves them to the output DataFrame
	- Writes final results to `students_results.xlsx`

4. After completion, `students_results.xlsx` will contain the scraped points for every student.

## Privacy & Data Handling 🔒

Student data files (e.g., `students.xlsx` and generated outputs) are included in `.gitignore` to keep sensitive data out of the repository. Do not commit personal or sensitive data into this repo.

## Video Walkthrough 🎥

I will upload a demonstration video soon. Inserting link here:

`Video walkthrough:` [Insert video link here]

## Troubleshooting & Notes

- If Selenium cannot find elements, try increasing the explicit wait timeout in `WebDriverWait`.
- Ensure `geckodriver` is compatible with your installed Firefox version.
- If the site layout changes, you may need to update the XPaths used in `students.ipynb`.

## License

This repository is free to clone and use. Please respect privacy and do not publish sensitive student data.

---
