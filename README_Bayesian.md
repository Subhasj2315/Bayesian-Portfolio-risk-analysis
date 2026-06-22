# Bayesian Portfolio Risk Analysis using HMC (PyMC)

## Overview

This project applies Bayesian statistical methods to model stock returns and volatility for five Indian equities. Using historical market data, the project estimates posterior distributions of expected return and volatility through Hamiltonian Monte Carlo (NUTS) sampling, enabling uncertainty quantification beyond traditional point-estimate approaches.

---

## Objective

Develop a Bayesian framework to estimate stock returns and volatility while quantifying uncertainty in financial risk analysis.

---

## Dataset

Historical daily stock prices were collected using Yahoo Finance for:

- TCS
- Infosys
- Reliance Industries
- HDFC Bank
- ITC

Data Period: ~5 Years

---

## Methodology

### 1. Data Collection
- Downloaded historical stock price data using Yahoo Finance.
- Extracted adjusted closing prices.

### 2. Return Calculation
Daily returns were computed as:

\[
R_t = \frac{P_t - P_{t-1}}{P_{t-1}}
\]

### 3. Exploratory Data Analysis
- Return distributions
- Volatility analysis
- Correlation analysis

- Rolling volatility

### 4. Likelihood Modeling

Assumed daily returns follow:

\[
R_i \sim N(\mu,\sigma^2)
\]

Estimated:
- Expected Return (μ)
- Volatility (σ)

using Maximum Likelihood Estimation (MLE).

### 5. Bayesian Inference

Defined priors:

\[
\mu \sim N(0,0.02)
\]

\[
\sigma \sim HalfNormal(0.02)
\]

Posterior distributions were estimated using Hamiltonian Monte Carlo (NUTS) implemented in PyMC.

---

## Project Workflow

```text
Historical Prices
        ↓
Return Calculation
        ↓
Exploratory Data Analysis
        ↓
Likelihood Modeling
        ↓
Bayesian Inference
        ↓
Posterior Analysis
```

## Key Results

- Estimated posterior distributions of expected return (μ) and volatility (σ).
- Generated 95% credible intervals for model parameters.
- Compared Bayesian estimates with classical MLE estimates.
- Quantified uncertainty through probabilistic inference.


## Repository Structure

```text
Bayesian-Portfolio-Risk-Analysis/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   ├── 01_data_collection.ipynb
│   ├── 02_return_calculation.ipynb
│   ├── 03_exploratory_data_analysis.ipynb
│   ├── 04_likelihood_modeling.ipynb
│   └── 05_bayesian_inference.ipynb
│
├── figures/
│
├── results/
│   ├── likelihood_results.csv
│   └── posterior_results.csv
│
├── requirements.txt
└── README.md
```

## Sample Outputs

### Exploratory Analysis
- Return Distribution Histograms
- Correlation Heatmaps
- Rolling Volatility Plots

### Bayesian Analysis
- Posterior Distributions
- Trace Plots
- Credible Intervals
- Parameter Summaries

---

### Results 
```python

import pandas as pd

df = pd.read_csv("posterior_results.csv")

print(df.to_markdown(index=False))

```

## Future Improvements

- Student-t Bayesian Models
- Value at Risk (VaR)
- Expected Shortfall
- Posterior Predictive Simulation
- Bayesian Portfolio Optimization

---

## Author

**Subhajit Khan**  
BS Physics, IIT Kanpur
