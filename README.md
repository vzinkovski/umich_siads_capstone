## FORECASTING DAILY RETURNS FOR S&P 500 CONSTITUENTS & IMPLEMENTING A TRADING STRATEGY
*Authors: Takehisa Kanayama & Vladimir Zinkovski*

### Introduction

This project seeks to forecast daily returns for S&P 500 constituent companies. The forecast period is one-day ahead and approached as a binary classification task where we label positive returns as the positive class, and negative or zero returns as the negative class. We use two datasets to extract features that may be predictive of future returns. First, the open, high, low and closing prices, and trading volume data from Yahoo! Finance. Second, various macroeconomic indicators pertaining to the US economy from the Federal Reserve Economic Data (FRED). We use data from 2000 up to and including 2023, which is split approximately 75%/12.5%/12.5% or 18/3/3 years for training/validation/testing. We train, tune and evaluate multiple individual models (RandomForest, LightGBM, deep neural net) which are then also combined into ensemble models (VotingClassifier, StackingClassifier). The best performing model is chosen upon which to build a simple trading strategy where if we predict the next day’s returns as positive, we buy for a holding period of one day. Finally, we evaluate the equity curve and Sharpe ratio achieved by our strategy versus a benchmark buy-and-hold approach.

### Data access statement

All data used in this project can be freely accessed from the below two sources in order to allow for reproducibility of results.

**yfinance**: An open-source tool that uses Yahoo's publicly available APIs and is intended for research and educational purposes. Please refer to Yahoo!'s terms of use ([here](https://legal.yahoo.com/us/en/yahoo/terms/product-atos/apiforydn/index.html), [here](https://legal.yahoo.com/us/en/yahoo/terms/otos/index.html), and [here](https://policies.yahoo.com/us/en/yahoo/terms/index.htm)) for details on your rights to use the actual data downloaded. Note that the Yahoo! Finance API is intended for personal use only. Links to [PyPi](https://pypi.org/project/yfinance/) and [GitHub](https://github.com/ranaroussi/yfinance).

**fredapi**: A Python API for the [FRED](https://fred.stlouisfed.org/) data provided by the Federal Reserve Bank of St. Louis. In order to use the API you can use the following API key: *a74d505e6731a2b5b06fdcf6ca20f6f5*, or [apply for one](https://fred.stlouisfed.org/docs/api/api_key.html) for free on the FRED website. This API is made available under a permissive, open-source Apache-2.0 license. Links to [PyPi](https://pypi.org/project/fredapi/) and [GitHub](https://github.com/mortada/fredapi).
