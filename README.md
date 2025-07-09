# Ontario_Covid_19-Cases_Analysis

This report analyzes COVID-19 case data, vaccination uptake, and demographic patterns across Ontario to identify key trends and assess the impact of public health measures at both provincial and municipal levels.

---

## Folder Snapshot

| Item                                  | Purpose                                                               |
| ------------------------------------- | --------------------------------------------------------------------- |
| `Ontario_Covid_19_Cases_Analysis.pdf` | Short report with key charts and findings                             |
| `R_code/`                             | Reproducible R scripts & R Markdown (`Ontario_Covid_19_Analysis.Rmd`) |
| `source_image/`                       | Exported figures (e.g., `varImpPlot2021.png`, `varImpPlot2022.png`)   |
| `README.md`                           | You’re reading it                                                     |

> **Raw CSVs are not stored here (they’re large).**  
> Download them from the Ontario Data Catalogue and place them in a local `csv/` folder before you run anything.

- **Case data (2021-2024)** – <https://data.ontario.ca/dataset/confirmed-positive-cases-of-covid-19-in-ontario>
- **Vaccine & PHU data** (`covid19_vaccine_data.csv`, `cases_phu.csv`) – <https://data.ontario.ca/dataset/covid-19-vaccine-data-in-ontario>

---

## Requirements

- **R:** Version 4.3 or higher  
- **R Packages:** tidyverse, ggplot2, dplyr, lubridate, randomForest, caret, boot, knitr, rmarkdown, patchwork

---

## Quick Re-Run

```r
# 0) In R ≥ 4.3, install the required packages (run once)
install.packages(c(
  "tidyverse", "ggplot2", "dplyr", "lubridate",
  "randomForest", "caret", "boot",
  "knitr", "rmarkdown", "patchwork"
))

# 1) Ensure raw CSVs are saved in **csv/**
#    ├─ Cases2021.csv … Cases2024.csv
#    ├─ COVID-Vaccine.csv
#    └─ cases_phu.csv

# 2) Re-generate the report and all figures
rmarkdown::render("R_code/Ontario_Covid_19_Analysis.Rmd")
