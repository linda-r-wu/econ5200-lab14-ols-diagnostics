[README.md](https://github.com/user-attachments/files/34996587/README.md)
# OLS Diagnostics: Robust and Clustered Standard Errors

## Objective

I compared how different standard errors affect confidence interval coverage and checked how individual observations can change an OLS estimate.

## Methodology

- Simulated data with unequal error variance and measured how often classical and HC3 confidence intervals contained the true slope.
- Repeated the coverage check with errors shared within 40 firms and compared HC3 with standard errors clustered by firm.
- Used leverage, studentised residuals and Cook’s distance to examine three planted observations and see which one moved the slope.
- Wrote a prompt asking AI for a standard error table and checked all 18 values against statsmodels on the original data and again after renaming the columns.

## Key Findings

With unequal error variance, the nominal 95% interval covered the true slope **92.4%** of the time using classical standard errors and **94.4%** using HC3. When employees shared firm shocks, HC3 coverage dropped to **50.3%**, while clustering by firm brought it back up to **93.7%**.

Of the three planted rows, C pulled the estimated slope down from **1.4927** to **1.4468**. Its `x` value was far from the center and its `y` value was well below the fitted line.

I stopped after **one round** with AI because all **18 standard errors** matched statsmodels, even after I renamed the columns.
