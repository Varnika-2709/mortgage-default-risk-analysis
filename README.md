# Visual Drivers of Mortgage Default Risk

An analysis of Fannie Mae loan-level data comparing two non-consecutive cohorts — **2007Q4**
(pre-financial crisis) and **2019Q4** (post-crisis) — to see how borrower risk profiles and
default behaviour changed, and which loan characteristics predict default.

Built in R with `ggplot2`, `plotly` and `gganimate`.

**[View the rendered report →](mortgage_default_risk.html)**
(download the file and open it locally — GitHub does not render HTML in-browser)

## Findings

**Credit score is the strongest single predictor.** Borrowers scoring below 660 default at
3–5x the rate of those above 780. The relationship holds in both cohorts, but the 2019 cohort
defaults 30–50% less than the 2007 cohort *in every score band* — evidence of both better
screening and better risk-based pricing after the crisis.

**Leverage compounds it.** Loans with original LTV above 90% default at 2–3x the rate of
those at or below 60%. The gradient is visibly steeper in 2007 than in 2019.

**The borrower pool itself shifted.** An animated histogram of the credit-score distribution
shows the 2019 cohort displaced toward higher scores — so portfolio improvement comes from
*selection* (who got lent to) as well as *performance* (how they behaved).

**Interest rate works as a forward-looking risk signal.** Defaulted loans carry higher median
original rates and a wider interquartile range in both cohorts, suggesting lenders were
already pricing the risk they later realised.

**Occupancy matters.** Investor and second-home loans default at higher rates than primary
residences — borrowers prioritise the home they live in.

**Recent default rates are stable.** A quarterly time series over 2020–2023 stays within
roughly 0.1%–0.2%, with quarter-to-quarter movement under 0.05%.

## Charts

| Chart | Type |
|---|---|
| Default rate trend, 2020–2023 | Interactive Plotly time series |
| Default rate by credit score band, 2007 vs 2019 | Grouped bar |
| Default rate by LTV band, 2007 vs 2019 | Grouped bar |
| Credit score distribution over time | Animated histogram (`gganimate`) |
| Original interest rate by loan status | Faceted boxplot |
| Default rate by occupancy status | Heatmap |

## Repository contents

```
mortgage_default_risk.Rmd    source
mortgage_default_risk.html   rendered report with interactive and animated charts
```

## Reproducing it

The Rmd expects three data files alongside it, which are not redistributed here:

- `default_rate_ts.csv` — quarterly portfolio default rates
- `data_sample_2007Q4.rds` — 2007Q4 loan-level sample
- `data_sample_2019Q4.rds` — 2019Q4 loan-level sample

Requires `tidyverse`, `plotly`, `scales`, `gganimate` and `bookdown`.

## Author

Varnika Bethireddy — sole author of this analysis.
