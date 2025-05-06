# Repeated Measures ANOVA in R with ezANOVA

## 📦 Packages Used

- tidyverse
- readxl
- ez
- knitr
- ggplot2

## 📊 Analysis Overview

The analysis assumes that each subject has multiple measurements across different time points (or conditions), making it suitable for within-subject experimental designs.

The core steps include:

1. Loading and preparing the data
2. Reshaping it to long format for ANOVA
3. Running `ezANOVA()` with Type 3 sums of squares
4. Summarizing and plotting results

## 🖼 Example Plot

The script produces a line plot showing individual subject trends and the overall mean with standard error bars across test times.

## 📁 File Structure

- `tekrarli_olcum_ornek_no_id.xlsx`: Example dataset
- `anova_script.R`: Main analysis script
- `README.md`: Project overview

## 🔍 Future Improvements

- Exporting results to formatted tables (e.g., Word/HTML)
- Adding post-hoc comparisons
- Supporting between-subjects factors

---

Feel free to clone, modify, and use this workflow in your own repeated measures analysis!

**NOTE :** This is my school project.
