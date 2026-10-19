# Faculty Salary and College Graduation Rates

An analysis of whether colleges that pay their faculty more tend to have higher graduation rates, using the U.S. Department of Education's [College Scorecard](https://collegescorecard.ed.gov/data/) dataset.

Completed as the final project for CDS 101 (Introduction to Computational and Data Sciences) at George Mason University, Fall 2025.

## Research question

Is a college's average faculty salary associated with its graduation rate, and does that relationship look different across campus settings (city, suburb, town, rural)?

## Data

- **Source:** U.S. Department of Education College Scorecard
- **Response variable:** `C150_4`, the completion rate for first-time, full-time students at four-year institutions (converted to a percentage)
- **Explanatory variable:** `AVGFACSAL`, average monthly faculty salary
- **Grouping variable:** `LOCALE`, recoded from numeric codes into readable categories such as "City: Large" and "Rural: Remote"

## Methods

1. **Preprocessing:** selected and renamed the relevant columns, converted graduation rate to a percentage, and recoded locale codes into labeled categories
2. **Exploratory analysis:** histograms of each variable, a scatter plot of salary vs. graduation rate, and a faceted scatter plot by locale
3. **Summary statistics:** mean, median, range, standard deviation, and IQR of both variables, grouped by locale
4. **Modeling:** simple linear regression (`GRAD_RATE ~ AVGFACSAL`)
5. **Diagnostics:** observed vs. predicted plot, residuals vs. predicted plot, and a normal Q-Q plot

## Key findings

- There is a clear **positive relationship**: colleges with higher average faculty salaries tend to have higher graduation rates.
- The relationship is **statistically significant** (p < 0.001). Each additional $1,000 in average monthly faculty salary is associated with roughly a 4.3 percentage point higher graduation rate.
- Faculty salary explains about **25% of the variation** in graduation rates (R² ≈ 0.25), so other factors such as funding, student preparation, and institutional resources likely matter as much or more.
- The pattern appears across most locale types, but it is tighter at urban and suburban schools and more spread out at rural ones.
- Regression assumptions were reasonably met, with only minor deviations from normality at the tails.

This is an observational analysis, so it shows association, not causation.

## Tools

R, tidyverse (dplyr, ggplot2), broom, knitr, R Markdown

## Repository contents

| File | Description |
|---|---|
| `final_project.Rmd` | Full analysis: code, plots, and written interpretation |
| `Makefile` | Builds the report from the R Markdown file |

## How to run

1. Download the College Scorecard data and place it where `final_project.Rmd` expects it.
2. Open the project in RStudio.
3. Knit `final_project.Rmd`.

