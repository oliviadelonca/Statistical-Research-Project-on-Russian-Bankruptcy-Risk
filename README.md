## Overview

This academic project studies the determinants of corporate dissolution in Russia between 2012 and 2024, a period marked by five major economic shocks: the 2012 structural slowdown, the 2014 Crimea annexation and international sanctions, the 2014–2016 oil price collapse, the COVID-19 pandemic, and the 2022 invasion of Ukraine.

Using survival analysis methods (Kaplan-Meier estimator and Cox proportional hazards models), we identify how firm characteristics — sector, region, age, and size — shape the risk of dissolution, and how this risk evolves across macroeconomic regimes.

## Data

- **Source:** [Russian Financial Statements Database (RFSD)](https://github.com/irlcode/RFSD) — annual financial statements of Russian firms (2011–2024), combining data from Rosstat and the Federal Tax Service.
- **Sample:** ~7.9 million firms after filtering out companies dissolved within 3 years of creation.
- **Key variables:** `ogrn` (firm ID), `region`, `creation_date`, `dissolution_date`, `okved_section` (industry code), `line_2210` (revenue).

## Methodology

1. **Descriptive statistics** — dissolution rates over time, by sector, by region, by age
2. **Kaplan-Meier estimator** — non-parametric survival curves, stratified by sector, size, region, and historical period
3. **Cox proportional hazards model** — estimated in counting-process format (one observation per firm-year), with three specifications:
   - **M1**: sector, region, and year fixed effects
   - **M2**: adds a relative firm-size proxy (revenue quartiles within sector × region cells)
   - **M3**: adds sector × period interactions to relax the proportional hazards assumption over time
