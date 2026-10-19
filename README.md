# Energy Consumption and Economic Development Across Countries

This project studies how per-capita energy use relates to economic development across countries. It combines a country-level comparison of changes over time with a cross-sectional regression analysis for 2021.

## Research questions and findings

1. **Did energy-use changes from 2010 to 2021 differ by initial development level?** Countries are split into lower- and higher-development groups using the median 2010 GDP per capita (PPP). Welch’s two-sample *t*-test and a permutation test find a difference in mean change: the higher-development group decreased by about **446 kg of oil equivalent per person**, on average, while the lower-development group increased by about **122 kg**. A 2010–2019 sensitivity analysis gives the same conclusion, so the pattern is not driven only by 2020–2021.
2. **How are energy use and GDP per capita related across countries in 2021?** After diagnostics, the project uses a log–log linear regression. Its estimated slope is **0.9479** (about a 0.95% higher GDP per capita for each 1% higher energy use per capita), with **R² = 0.7871**. This is an association and does not establish causation.

## Repository contents

| File | Description |
| --- | --- |
| `DATA602_Project_RQ1,RQ2.Rmd` | Reproducible R Markdown source for the analyses, plots, tests, and conclusions. |
| `df_602.csv` | Analysis data: 1,704 country-year rows for 142 countries from 2010 through 2021. Includes country, year, energy use per capita, and GDP per capita (PPP, constant 2021 international dollars). |
| `DATA602_Project_RQ1,RQ2.pdf` | PDF output of the R Markdown analysis. |
| `DATA602_Report.docx`, `DATA602_Report.pdf` | Formatted project report. |
| `DATA602_Presentation.pptx`, `DATA602_Presentation.pdf` | Project presentation and its PDF export. |

The presentation credits the **World Bank’s World Development Indicators** as the data source. The analysis uses complete observations; the CSV contains no missing values for the included records.

## Reproduce the analysis

Install R and the packages used by the source (`rmarkdown`, `ggplot2`, `mosaic`, and `dplyr`). Run the render command from the repository root so the relative path to `df_602.csv` resolves:

```r
install.packages(c("rmarkdown", "ggplot2", "mosaic", "dplyr"))
rmarkdown::render("DATA602_Project_RQ1,RQ2.Rmd", output_format = "html_document")
```

To render the PDF version, use `output_format = "pdf_document"`; PDF output also requires a LaTeX installation available to R Markdown.
