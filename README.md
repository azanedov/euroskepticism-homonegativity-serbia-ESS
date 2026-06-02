# From *Evropa* to *Gayropa*: Euroskepticism and Homonegativity in Serbia

This project examines the relationship between skepticism toward the European Union and attitudes of rejection toward gay men and lesbian women in Serbia, using data from the European Social Survey Round 11 (2023). Submitted for **SIMM61 – Quantitative Data Analysis in R**, Graduate School, Lund University (Autumn 2025).

## Research Question

To what extent is Euroskepticism associated with the rejection of gay men and lesbian women in Serbia?

## Data

**Source:** European Social Survey Round 11 (2023), filtered to Serbian respondents.

**Key variables:**

-   **Euroskepticism Index** — Latent factor extracted from three reversed EU attitude items: emotional attachment to Europe (`atcherp`), trust in the European Parliament (`trstep`), and assessment of European unification (`euftf`).
-   **Homonegativity Index** — Latent factor extracted from three items measuring attitudes toward gay men and lesbian women: agreement that they should be free to live as they wish (`freehms`), whether they would feel ashamed if a family member were gay/lesbian (`hmsfmlsh`), and whether gay and lesbian couples should have the same rights to adopt children (`hmsacld`).
-   **Controls:** Gender, age, years of education, religiosity.

## Methods

| Step | Technique | Purpose |
|------------------|------------------------------|-------------------------|
| Index construction | Maximum Likelihood Factor Analysis | Extract latent variables from observed indicators |
| Reliability | Cronbach's Alpha | Assess internal consistency of each index |
| Modeling | OLS Linear Regression (bivariate + multivariate) | Estimate focal relationship and test for spuriousness |
| Diagnostics | Cook's Distance, VIF, residual plots | Identify outliers and check regression assumptions |
| Model comparison | ANOVA (F-test) | Compare fit of nested models |

## Visualizations

The analysis produces several figures:

-   Distribution plots of both latent factor scores
-   Scatter plot with regression overlay (bivariate relationship)
-   Marginal effects plot (predicted LG rejection across Euroskepticism levels, adjusted for controls)
-   Choropleth map of LG rejection scores across all ESS11 participating countries
-   Forest plot of coefficient estimates with confidence intervals

## Repository Structure

```         
.
├── README.md
├── analysis.Rmd              # Full analysis (code + narrative)
├── manuscript.typ            # Written paper (Typst)
└── outputs/                  # Generated tables and figures
```

## How to Reproduce

1.  Download ESS Round 11 (edition 4) as CSV from [europeansocialsurvey.org](https://www.europeansocialsurvey.org/data/download.html?r=11).
2.  Place the file (`ESS11e04_0.csv`) in the project root directory.
3.  Install required R packages:

``` r
install.packages(c(
  "tidyverse", "psych", "stargazer", "modelsummary",
  "gt", "gtsummary", "kableExtra", "car", "sjPlot",
  "rnaturalearth", "rnaturalearthdata", "sf",
  "webshot2", "broom", "skimr"
))
```

4.  Open `analysis.Rmd` in RStudio and knit.

## Tools

R · tidyverse · psych · stargazer · sjPlot · modelsummary · rnaturalearth · sf

## Author

Vanessa Azañedo — MSc Social Scientific Data Analysis, Lund University.

## License

This project is shared for academic and portfolio purposes. The ESS data is subject to its own [terms of use](https://www.europeansocialsurvey.org/data/conditions_of_use.html).
