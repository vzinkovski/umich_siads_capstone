# FORECASTING DAILY RETURNS FOR S&P 500 CONSTITUENTS
## *Team 21 - Data Edge - Takehisa Kanayama & Vladimir Zinkovski*

This project seeks to forecast daily returns for S&P 500 constituent companies. The forecast period is one-day ahead and approached as a binary classification task where we label positive returns as the positive class, and negative or zero returns as the negative class. We use two datasets to extract features that may be predictive of future returns. First, the open, high, low and closing prices, and trading volume data from Yahoo! Finance. Second, various macroeconomic indicators pertaining to the US economy from the Federal Reserve Economic Data (FRED). We use data from 2000 until 2023, which is split approximately 75%/12.5%/12.5% for training/validation/testing. Using such a long time horizon allows us to cover multiple black swan events, such as, for example, the dotcom bubble in 2000-2002, GFC in 2008-9, and COVID-related crash in 2020 and subsequent V-shaped recovery in 2021-22. Incorporating these outlier events into our data will hopefully permit training more robust machine learning models. We train and tune three individual models using different underlying algorithms, which are then combined into an ensemble model. Finally, we employ the ensemble forecasts into a simple trading strategy where if we predict the next day’s returns as positive, we buy for a holding period of one day.
