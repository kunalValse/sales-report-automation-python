# Monthly Sales Report Automation Pipeline

An automated data engineering script built to standardize, clean, and validate messy corporate sales invoice spreadsheets. 

## The Problem
Monthly sales workbooks often arrive with structural anomalies that break downstream databases and business intelligence (BI) tools. Common issues include accidental whitespace padding in columns, unformatted dates, and trailing metadata rows.

## Features & Automated Solutions
- **Header Normalization**: Strips trailing whitespaces and transforms column headers to standard lowercase `snake_case` (e.g., converts `"INVOICE VALUE "` to `"invoice_value"`).
- **Temporal Enforcement**: Validates and casts transaction dates into reliable `YYYY-MM-DD` datetime formats.
- **Payload Selection**: Filters out noise to isolate the 11 core data attributes needed for business reporting.
- **Anomalous Sign Correction**: Enforces mathematical absolute values (`.abs()`) on invoice calculations to fix negative sign data entry bugs.
- **Data Pruning**: Automatically drops trailing empty rows and missing invoice records created by Excel sheet cell formatting.

## Repository Layout
- `sales_cleaner.py`: The core automated extraction and cleaning script.
- `data/`: Directory housing raw, anonymized monthly sales workbooks used for testing.

## Tech Stack
- **Language**: Python 3.12+
- **Libraries**: Pandas, OpenPyXL
- **Environment**: Google Colab / Local IDE
