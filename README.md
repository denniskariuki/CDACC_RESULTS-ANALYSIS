Project Overview
This project provides a Python workflow for extracting, parsing, and consolidating student competency assessment data from structured PDF files into a flat, analyzable CSV format using Pandas. The main logic is implemented in a Jupyter Notebook. The script is tailored to process assessment result PDFs similar to "July 2024.pdf" and output a unified .csv file containing all candidate performance records.

Contents
karis.ipynb — Jupyter notebook with all code for PDF parsing and data extraction.

Your PDF file (e.g., July 2024.pdf) — the assessment data to parse.

all_candidates.csv — output file with consolidated candidate/unit records.

Requirements
Python 3.9+

Jupyter Notebook

Libraries:

pdfplumber

pandas

re

warnings

pathlib

Install dependencies using:

bash
pip install pdfplumber pandas
How It Works
Import Dependencies:
Loads necessary Python modules for PDF extraction, data parsing, and handling file paths.

Parse the PDF:
Opens the provided PDF containing candidate results and processes each page.

Per-Page Extraction:

Extracts registration number and student name.

Reads logical sections (level, course, units, etc.).

Handles multi-line unit details and various formatting subtleties.

Unit Records:
For each candidate, every registered unit is extracted as a single row with fields:

Registration Number

Student Name

Level

Course Name

Unit Code

Unit Name

Category (Basic, Core, Common)

Competence (Competent, Not Yet Competent, Mastery, Proficient)

Export to CSV:
After all pages are processed, results are written to all_candidates.csv, with each row as one candidate/unit/competence record.

Usage Instructions
Place Your PDF:
Update the PDF_PATH variable in the notebook to point to your PDF (default is C:\Users\DELL\Desktop\Karis\July 2024.pdf).

Run All Cells:
Open karis.ipynb in Jupyter Notebook and run all cells.

Check Output:
After execution, the consolidated data appear in all_candidates.csv in your working directory.

Sample Output (CSV)
Registration Number	Student Name	Level	Course Name	Unit Code	Unit Name	Category	Competence
013001/EIN/5/2024/004	Njue Daniel Munene	5	Electrical Installation	ENG/OS/EI/BC/03/5	Demonstrate Digital Literacy	Basic Unit	Competent
013001/EIN/5/2024/004	Njue Daniel Munene	5	Electrical Installation	ENG/OS/EI/CR/02/5	Perform Electrical Installation	Core Unit	Not Yet Competent
...	...	...	...	...	...	...	...
Troubleshooting
If you see repeated warnings "CropBox missing from /Page, defaulting to MediaBox", these are expected with some PDFs and do not affect data extraction.

For unexpected PDF formats, parsing logic may need adjustment.

Customization
Multiple/Other PDFs: Update PDF_PATH at the top of the notebook for each file.

Output File Name: Change the OUTPUT_CSV variable to your preferred path.

