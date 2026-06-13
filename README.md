# Has the U.S. value premium decayed?

A short, rigorous research note on the Fama-French HML (value-minus-growth) factor,
1963 to present. It asks how strong the value premium has been across the full history
and across market regimes, and how much of that strength carries into forward expectations.

How you read the result matters more than the result itself. Treating an in-sample factor
mean as a forward forecast is a classic error, and the note is built to expose that gap.

The notebook is committed with its outputs, so it renders in full (charts, tables, and
the printed results) right here on GitHub. You can read the whole thing without running it.

## What it does

- Downloads monthly Fama-French research factors directly from the **Ken French Data Library**, with a bundled snapshot (`ff_factors.csv`) as an automatic fallback.
- Estimates the full-sample premium with **Newey-West (HAC)** standard errors.
- Tests stability across subperiods and a 10-year rolling window.
- Measures the factor's maximum drawdown (the "value winter").
- Closes with an honest read on what the retrospective does and does not say about the future.

## Run it

```bash
cd value-premium-study
pip install -r requirements.txt
jupyter notebook value_premium_study.ipynb
```

It downloads live data from the Ken French library. If that library is unreachable, the
notebook falls back to the bundled `ff_factors.csv` snapshot automatically, with no other
change to the analysis.

## Sources

- Ken French Data Library, "F-F Research Data Factors" (monthly). https://mba.tuck.dartmouth.edu/pages/faculty/ken.french/data_library.html
- Fama & French (1992), "The Cross-Section of Expected Stock Returns," Journal of Finance 47(2), 427-465.
- Fama & French (1993), "Common Risk Factors in the Returns on Stocks and Bonds," Journal of Financial Economics 33(1), 3-56.
- McLean & Pontiff (2016), "Does Academic Research Destroy Stock Return Predictability?," Journal of Finance 71(1), 5-32. (Finds returns roughly 26% lower out-of-sample and 58% lower post-publication.)
- Arnott, Harvey, Kalesnik & Linnainmaa (2021), "Reports of Value's Death May Be Greatly Exaggerated," Financial Analysts Journal 77(1), 44-67.
- Israel, Laursen & Richardson (2020), "Is (Systematic) Value Investing Dead?," AQR Capital Management.
