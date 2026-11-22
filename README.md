# Ad Conversion Analysis: Facebook vs. AdWords

Which ad platform converts better, and can daily conversions be predicted from clicks? This project analyzes a full year of campaign data (365 days, 2023) using descriptive statistics, hypothesis testing and regression in **Excel** and **Tableau**.

## Key findings

| Metric | Facebook | AdWords |
|---|---|---|
| Mean conversions per day | **11.7** | 6.0 |
| Std. dev. of daily conversions | 2.9 | 1.6 |
| Click-to-conversion rate (total) | **26.7%** | 9.9% |
| Cost per conversion* | **$7.48** | $22.59 |

- **Facebook converts significantly better.** A two-sample t-test on daily conversions gives t ≈ 32.9 and p far below α = 0.05, so the null hypothesis of "no difference between platforms" is rejected.
- **Clicks predict conversions well on Facebook.** A simple linear regression (conversions ~ clicks) fits with R² ≈ 0.76. The model expects about **13 conversions on a day with 50 clicks**.

\*Cost per conversion = total ad cost / total conversions, assuming the cost column is daily spend. Currency is not specified in the source data.

## Business question

> Should we advertise on Facebook or AdWords, and how many Facebook conversions can we expect for a given number of clicks?

## Dataset

- **Period:** Jan 1 – Dec 31, 2023 (365 daily rows)
- **Fields per platform:** campaign, ad views, ad clicks, ad conversions, cost, plus derived click-through rate, conversion rate and cost per click

## Methodology

1. **Descriptive statistics** (Excel): mean, median, mode and standard deviation of daily clicks and conversions for each platform, plus conversion-count groupings (1–5, 6–10, 11–15, 16+).
2. **Distribution checks** (Excel): histograms of clicks and conversions for each platform to assess normality.
3. **Hypothesis testing** (Excel):
   - H0: no difference in mean daily conversions between Facebook and AdWords
   - H1: there is a difference
   - Two-sample t-test, α = 0.05
4. **Predictive modeling** (Tableau): simple linear regression of Facebook conversions on Facebook clicks. Model choice is documented in the workbook, with the assumptions checked (sample size, linearity, homogeneity of variance, normality, independence).

## Tools

Excel, Tableau, statistics (descriptive statistics, t-test, simple linear regression)


## Limitations and next steps

- The analysis compares conversion *counts* per day. Spend differs by platform, so a cost-adjusted comparison (cost per conversion) is a natural follow-up.
- Daily observations may show seasonality or day-of-week effects that are not modeled here.
- The regression covers Facebook only. Fitting the same model for AdWords would allow a side-by-side comparison.
