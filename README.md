# Nutrition BMINDS Food Insecurity Survey

## Overview

This repository contains my survey analysis work on food insecurity, resilience, stress mindset, and psychological distress. The main analysis is done in `data_visualization_v3.ipynb`, with the cleaned Excel output, written reports, and presentation included in the same folder.

The project is mainly a research and data-analysis deliverable, not a full software application.

## Repository Contents

```text
.
|-- Analytical Report.docx
|-- cleaned.xlsx
|-- data_visualization_v3.ipynb
|-- pres.pptx
`-- technical report.docx
```

## Main Files

### `data_visualization_v3.ipynb`

This notebook contains the main data cleaning, processing, visualization, and statistical analysis steps. It includes:

- loading the survey data from an Excel file
- checking missing values and unique values
- removing duplicate rows
- cleaning text values by converting them to lowercase and removing extra spaces
- removing columns with more than 5% missing values
- removing any remaining rows with missing values
- creating new calculated measures for food insecurity, resilience, stress mindset, and psychological distress
- encoding selected categorical columns for analysis
- applying statistical tests such as Shapiro-Wilk, Spearman correlation, and Mann-Whitney U
- creating visualizations such as pie charts, histograms, bar charts, and violin plots
- exporting the cleaned dataset as `cleaned.xlsx`

### `cleaned.xlsx`

This file is the cleaned dataset generated from the notebook. It contains:

- one worksheet: `Sheet1`
- 863 rows
- 103 columns

It includes the original survey fields along with calculated columns such as:

- `FIES_score`
- `FIES_level`
- `Resilience_Total`
- `Resilience_Level`
- `StressMindset_Total`
- `StressMindset_Level`
- `K10_total`
- `K10_category`
- encoded helper columns such as `gender_enc`, `gpa_enc`, and `income_enc`

### Reports and Presentation

- `technical report.docx` explains the methodology, data-cleaning steps, statistical tests, and findings.
- `Analytical Report.docx` summarizes the analysis, observations, and recommendations.
- `pres.pptx` contains the presentation prepared for the project.

## Tools and Libraries Used

The notebook uses:

- Python
- Jupyter Notebook
- Google Colab file upload workflow
- `pandas`
- `numpy`
- `scipy`
- `seaborn`
- `matplotlib`

## How to Run the Notebook

Open `data_visualization_v3.ipynb` in Google Colab or a similar notebook environment.

When running the notebook, upload the Excel file during runtime, and the notebook reads the first worksheet from that file.

The notebook then processes the data and exports the cleaned result as:

`cleaned.xlsx`

## Analysis Scope

The analysis focuses on the following measures:

- food insecurity using `FIES_score` and `FIES_level`
- resilience using `Resilience_Total` and `Resilience_Level`
- stress mindset using `StressMindset_Total` and `StressMindset_Level`
- psychological distress using `K10_total` and `K10_category`

The included reports also discuss relationships involving:

- food security and psychological distress
- stress mindset and gender
- food security and household income
- gender and GPA
