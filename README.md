# Nutrition BMINDS Food Insecurity Survey

## Overview

This repository is a survey-analysis workspace centered on food insecurity, resilience, stress mindset, and psychological distress. The main executable artifact is the notebook `data_visualization_v3.ipynb`, supported by a cleaned Excel export, two Word reports, and a presentation file.

Based on the files present in this folder, this repository is a research deliverable rather than a conventional software application.

## Repository Contents

```text
.
|-- Analytical Report.docx
|-- cleaned.xlsx
|-- data_visualization_v3.ipynb
|-- pres.pptx
`-- technical report.docx
```

## Verified Components

### `data_visualization_v3.ipynb`

The notebook contains the analysis workflow. From the code in the notebook, it:

- imports `pandas`, `numpy`, `scipy.stats`, `seaborn`, `matplotlib`, and `google.colab.files`
- uploads an Excel dataset interactively
- inspects missing values and unique values
- removes duplicate rows
- standardizes text values by lowercasing and trimming
- drops columns with more than 5% missing values
- drops remaining rows with missing values
- creates derived metrics for food insecurity, resilience, stress mindset, and psychological distress
- encodes selected categorical variables for analysis
- runs Shapiro-Wilk, Spearman correlation, and Mann-Whitney U analyses
- creates charts including pie charts, histograms, bar charts, and violin plots
- exports the processed dataset to `cleaned.xlsx`

### `cleaned.xlsx`

This file appears to be the cleaned output produced by the notebook. The inspected workbook contains:

- one sheet: `Sheet1`
- 863 rows
- 103 columns

The sheet includes both survey fields and derived columns such as:

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

- `technical report.docx` describes the methodology, cleaning decisions, statistical tests, and reported findings.
- `Analytical Report.docx` summarizes the analysis, observations, and recommendations.
- `pres.pptx` is a presentation artifact included in the repository.

## Tech Stack

Identified directly from `data_visualization_v3.ipynb`:

- Python
- Jupyter Notebook
- Google Colab-style file upload and download workflow
- `pandas`
- `numpy`
- `scipy`
- `seaborn`
- `matplotlib`

## Running the Notebook

The notebook contains this upload flow:

```python
from google.colab import files
uploaded = files.upload()
df = pd.read_excel(list(uploaded.keys())[0], sheet_name=0)
```

This indicates that the notebook expects an Excel file to be uploaded at runtime and reads the first worksheet from that file. The notebook later writes the processed result to:

```python
research_df.to_excel("cleaned.xlsx", index=False)
```

Because the notebook imports `google.colab.files`, it appears to have been authored for Google Colab or a similar notebook environment.

## Analysis Scope

The notebook derives and analyzes several composite measures:

- food insecurity using `FIES_score` and `FIES_level`
- resilience using `Resilience_Total` and `Resilience_Level`
- stress mindset using `StressMindset_Total` and `StressMindset_Level`
- psychological distress using `K10_total` and `K10_category`

The reports in this repository also reference analysis of relationships involving:

- food security and psychological distress
- stress mindset and gender
- food security and household income
- gender and GPA

## Notes

- No package manifest or dependency file is present in this folder.
- No raw source dataset is included here; the repository contains the cleaned export `cleaned.xlsx`.
- The repository does not provide formal setup automation or a reproducibility guide beyond what can be inferred from the notebook itself.
