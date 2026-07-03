# Crude Oil Risk Forecasting Using Bayesian Networks

## Project Overview

This project applies a Bayesian Network approach to crude oil risk forecasting. It uses macroeconomic, financial, and oil-market indicators to classify future crude oil market conditions into different states, such as weak, neutral, or strong market conditions.

The project was developed as part of a risk management analysis and focuses on understanding how variables such as WTI crude oil price, Brent crude oil price, interest rates, inflation, demand, production, inventories, the U.S. dollar index, volatility, and energy market indicators interact in crude oil forecasting.

## Project Objectives

The main objectives of this project are to:

- Build a structured crude oil forecasting framework using macro-financial and oil-market data.
- Split the dataset chronologically into training, validation, and testing periods.
- Apply a Bayesian Network model using hill-climbing structure learning.
- Evaluate the model using validation and testing accuracy.
- Compare the forecasting model against a naive majority-state baseline.
- Interpret the practical usefulness of the model for risk management and portfolio decision-making.

## Dataset Summary

The final dataset contains 72 monthly observations from January 2019 to December 2024 across 14 variables.

The dataset was divided as follows:

| Dataset | Period | Observations | Purpose |
|---|---|---:|---|
| Training Set | January 2019 – September 2023 | 57 | Model learning, parameter estimation, regime detection, and network structure learning |
| Validation Set | October 2023 – April 2024 | 7 | Model selection, tuning, and generalization checks |
| Testing Set | May 2024 – December 2024 | 8 | Final out-of-sample forecasting evaluation |

## Key Variables

The analysis includes variables such as:

- WTI crude oil price
- Brent crude oil price
- WTI return
- Volatility
- Brent-WTI spread
- Oil inventory
- Oil demand
- Oil production
- Interest rate
- Consumer Price Index
- Industrial production
- U.S. dollar index
- VIX
- Energy ETF

## Methodology

The project follows these main steps:

1. Data collection and cleaning
2. Dataset allocation into training, validation, and testing sets
3. Validation-testing comparison and drift analysis
4. Bayesian Network structure learning using hill climbing
5. Model evaluation using actual versus predicted market states
6. Forecasting accuracy assessment
7. Practical interpretation for risk management

The Bayesian Network was learned using a hill-climbing algorithm with a BIC scoring approach. Mutual information was also used to identify important predictors where the learned structure did not provide a direct forecasting path.

## Model Results

The model produced the following results:

| Metric | Result |
|---|---:|
| Validation Accuracy | 28.57% |
| Validation Error | 71.43% |
| Testing Accuracy | 42.86% |
| Testing Error | 57.14% |
| Naive Majority-State Baseline Accuracy | 42.86% |

The testing result shows that the model performed at the same level as the naive majority-state baseline. This suggests that while the model contains useful structure, it is not yet strong enough to be used as a standalone forecasting or trading system.

## Key Findings

The model was better at identifying neutral or stagnant market conditions than extreme market movements. During the testing period, it predicted the "Stagnant/Middle" state for most observations. As a result, it captured stable market periods but missed major bearish and bullish movements.

This finding is important for risk management because crude oil forecasting is most valuable when the model can detect turning points. The current model should therefore be treated as an early-warning and decision-support tool rather than an automated trading model.

## Practical Application

This project can support portfolio managers, traders, and risk analysts by providing an additional screening tool for crude oil market conditions.

Possible applications include:

- Checking whether crude oil market signals are consistent with physical market fundamentals.
- Supporting defensive positioning when volatility and downside risk increase.
- Helping analysts avoid overconfidence during neutral market periods.
- Providing a framework for future improvement in commodity risk forecasting.

## Limitations

The model has some important limitations:

- The testing sample is small.
- The model struggled to detect strong bearish and bullish market shifts.
- The model tied with a simple majority-state baseline.
- It should not be used as an automated trading bot.
- Future work should improve state calibration and turning-point detection.

## Tools and Libraries Used

- Python
- Jupyter Notebook / Google Colab
- Pandas
- NumPy
- Matplotlib
- yFinance
- Bayesian Network structure learning logic
- Data visualization and model evaluation tools

## Repository Structure

```text
crude-oil-risk-forecasting-bayesian-network/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── risk_management_project_3.ipynb
│
├── reports/
│   └── risk_management_project_report.pdf
│
└── outputs/
    └── README.md
