# AI Statistical Analysis

This folder contains an independent Python statistical analysis generated to answer:

> **How is statistical analysis in Python performed when several observations (samples) are described by multiple features or attributes?**

The work follows the SciPy-lectures style of combining **exploratory analysis**, **hypothesis testing**, **regression**, and **visualization** across multivariate datasets. It does **not** reuse notebooks or documentation from `manual/`.

## Files

| File | Description |
|------|-------------|
| `stats_python.ipynb` | Main walkthrough (Sections B.1–B.5) |
| `stats_extension.ipynb` | Extension analysis using bootstrap confidence intervals |
| `PROMPTS.md` | Log of the assignment prompts used to create this work |
| `README.md` | This file |

## Data Sources

All datasets are read from `../manual/notebooks/`:

| Dataset | Used in | Description |
|---------|---------|-------------|
| `brain_size.csv` | B.1, B.2, B.3.a | 40 subjects with Gender, FSIQ, VIQ, PIQ, Weight, Height, MRI_Count |
| `iris.csv` | B.3.b only | 150 iris flowers with sepal/petal measurements and species |
| `wages.txt` | B.4, B.5 only | 534 CPS wage observations with education, experience, sex, etc. |

## Environment

Activate the conda environment before running notebooks:

```bash
conda activate stats-env
jupyter lab
```

Open notebooks from the `ai/` directory so relative paths resolve correctly.

Dependencies (from `manual/environment.yml`): Python 3.10, numpy, scipy, pandas, matplotlib, statsmodels, seaborn, jupyterlab.

## Notebook Summary

### `stats_python.ipynb`

**B.1 — Exploratory data analysis (brain_size.csv)**  
Load data with pandas, expose NumPy arrays, summarize with `groupby`, create boxplots, compute population mean VIQ, male/female counts, and mean log10(MRI_Count) by gender. Scatter matrices cover physical measures and IQ metrics (all subjects, males only, females only). Point-biserial correlations assess IQ–gender relationships.

**B.2 — Hypothesis testing (brain_size.csv)**  
scipy tests include 1-sample, 2-sample, and paired t-tests; Friedman and pairwise repeated measures for PIQ/VIQ/FSIQ; Wilcoxon signed-rank; weight comparison by gender; Mann-Whitney U for VIQ by gender. A written conclusion synthesizes results.

**B.3.a — Regression and ANOVA (brain_size.csv)**  
Simple OLS (`VIQ ~ log_MRI_Count`), categorical gender model (`C(Gender)`), long-form IQ comparison with paired t-tests, and Type II ANOVA for `VIQ ~ Gender + Height + Weight + log_MRI_Count`.

**B.3.b — Multiple regression (iris.csv)**  
OLS model `petal_length ~ sepal_length + sepal_width` with ANOVA F-test for overall significance.

**B.4 — Seaborn visualization (wages.txt)**  
Table display, pairplot with gender hue, matplotlib rc settings, lmplot, and Huber robust regression compared to OLS.

**B.5 — Interaction model (wages.txt)**  
Additive vs. interaction models for `log_WAGE ~ EDUCATION * SEX`, with slope comparison and interpretation of whether education returns differ by gender.

### `stats_extension.ipynb`

**Bootstrap confidence intervals** for the male–female VIQ mean difference on brain_size data. Ten thousand resamples produce a 95% percentile CI and histogram, providing a distribution-free complement to the classical tests in B.2.

## Key Findings (brief)

- The study sample has **20 males and 20 females**; population mean **VIQ ≈ 112.4**.
- IQ sub-scales (PIQ, VIQ, FSIQ) are **highly correlated** within subjects but show **no significant gender association**.
- **Weight** differs significantly by gender; **VIQ does not** (parametric and non-parametric tests agree).
- Brain size (log MRI count) is modeled as a predictor of VIQ; ANOVA adjusts for body-size covariates.
- Wage data show strong education effects; the **education × sex interaction** tests whether males benefit more from additional schooling.

## Reproducibility

Both notebooks were executed successfully with `stats-env`. Run all cells from top to bottom in JupyterLab with the working directory set to `ai/`.
