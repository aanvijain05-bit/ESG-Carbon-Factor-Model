# ESG-Carbon-Factor-Model
Quantitative ESG factor model testing whether carbon intensity generates risk-adjusted alpha after Fama-French five-factor controls. Python, S&amp;P 500, 2019-2024.
# ESG Carbon Intensity Factor Model

Quantitative ESG factor model testing whether carbon intensity generates risk-adjusted alpha after Fama-French five-factor controls. Python, S&P 500, 2019-2024.

## Overview
This project constructs a carbon intensity factor from sector-level emissions data and tests whether it generates risk-adjusted alpha after controlling for the Fama-French five-factor model. The analysis covers 145 S&P 500 constituents over February 2019 to December 2024 (71 months).

## Methodology
Stocks are ranked monthly by carbon intensity and sorted into quintiles. A long-short portfolio goes long the lowest-carbon quintile (Q1 Green) and short the highest-carbon quintile (Q5 Dirty). Excess returns are then regressed against the Fama-French five factors to isolate unexplained alpha.

**Note on data:** Firm-level carbon emissions data requires institutional subscriptions (Bloomberg, Refinitiv). This project uses sector-level carbon intensity scores calibrated to published MSCI and CDP research, consistent with peer-reviewed ESG factor studies (Gorgen et al. 2020, Pastor et al. 2022).

## Results

| Model | Annualised Alpha | t-stat | R² |
|-------|-----------------|--------|-----|
| CAPM  | 5.40%           | 1.02   | 0.003 |
| FF3   | 3.90%           | 0.87   | 0.328 |
| FF5   | 5.86%           | 1.37   | 0.429 |

The carbon factor generates economically meaningful alpha of 5.86% per annum after FF5 controls. Two findings stand out:

- **CMA loading: -0.563 (t=-3.20, p=0.002).** Green stocks load negatively on the Conservative Minus Aggressive factor, confirming that low-carbon firms tend to be high-investment growth companies, consistent with the ESG-growth nexus in Pastor, Stambaugh & Taylor (2022).
- **SMB loading: -0.292 (t=-2.02, p=0.048).** The green portfolio tilts toward large caps, consistent with larger firms having more resources to manage and disclose environmental performance.
- **2022 drawdown.** Rolling alpha turns sharply negative in 2022, coinciding with the energy price shock following Russia's invasion of Ukraine, a known regime risk for ESG strategies.

## Skills Demonstrated
- Factor construction and cross-sectional z-scoring
- Quintile portfolio sorts and long-short backtesting
- Fama-French 5-factor regression with alpha decomposition
- Rolling performance analysis and regime identification
- ESG and sustainable finance research methodology

## Data Sources
- Price data: Yahoo Finance via yfinance
- Carbon intensity: MSCI/CDP sector-level research
- Risk factors: Ken French Data Library (FF5)

## Libraries
`pandas` `numpy` `statsmodels` `matplotlib` `yfinance` `scipy` `requests`
