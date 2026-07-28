# public-utility-regression-model
Target Corporation (TGT) — Quarterly Revenue Trend Analysis

A time-series regression analysis of Target Corporation's quarterly revenue, built for AFM 244. The model estimates a linear growth trend combined with holiday-season seasonality effects, and translates the results into an investment-relevant memo.

Overview

Using quarterly financial data (qSales_2024.csv), this notebook isolates Target's revenue records and fits an OLS regression that captures:


Underlying growth trend — revenue's change over time
Holiday quarter effect (Q4) — the seasonal spike from holiday retail sales
Post-holiday quarter effect (Q1) — whether revenue pulls back immediately after the holidays


Method


Load and filter the dataset to Target Corporation (tic == 'TGT')
Plot raw quarterly revenue to visualize the seasonal pattern
Construct a time index and two dummy variables (holiday_q4, post_holiday_q1)
Fit an OLS model: Revenue ~ time + holiday_q4 + post_holiday_q1
Generate predicted values and plot actual vs. predicted revenue


Results

Fitted model:

Revenue = 8,490.51 + 168.79 × Time + 4,675.92 × Holiday_Q4 − 386.32 × Post_Holiday_Q1


R² ≈ 0.89 — the model explains about 89% of quarter-to-quarter revenue variation
Time trend: statistically significant; revenue grows ~$169M per quarter, holding seasonality constant
Q4 (holiday) dummy: statistically significant; revenue is ~$4.68B higher in Q4 due to holiday shopping
Q1 (post-holiday) dummy: small negative effect, not statistically significant — no evidence of a post-holiday revenue cliff beyond normal seasonal variation


Investment Memo

The notebook includes a client-facing memo (To: Chapman Wealth Management, From: QuantFolio Solutions) summarizing findings for an investment decision:


Target's revenue growth is steady and highly predictable quarter to quarter
Holiday-quarter strength is a normal, expected seasonal pattern for a general-merchandise retailer, not a red flag
No evidence that holiday sales are simply pulled forward from the following quarter
The model's strong historical fit supports near-term revenue forecasting for valuation purposes, though it should be revisited if Target's business mix or seasonality shifts materially


Requirements


Python 3
pandas
numpy
matplotlib
statsmodels
