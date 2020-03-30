# JPY vs USD: Time Series Analysis

The financial departments of large companies often deal with foreign currency transactions while doing international business. As a result, they're always looking for anything that can help them better understand the future direction and risk of various currencies. Hedge funds, too, are keenly interested in anything that will give them a consistent edge in predicting currency movements. 

This project tested time-series tools in order to predict future movements in the value of the Japanese yen versus the U.S. dollar. 

The following were the list of tasks:

1. Time-Series Return Forecasting
2. Volatility Forecasting
3. Out-of-Sample Predictions

- - -

#### Time-Series Return Forecasting

In this section, the project used the Quandl API to obtain daily futures data on the Japanese yen per U.S. dollar exchange rate and used the data to build various time-series models that predict near-term yen returns. 

The following were the steps taken:

1. Generated a Quandl API key.

     1. Used the API key to read historical daily yen futures data into a Pandas DataFrame.

3. Performed a time-series decomposition, using Hodrick-Prescott filter and various moving average (MA) and exponentially weighted moving average (EWMA) smoothers.

4. Estimated a Scikit-Learn time-series regression to identify seasonal effects in the yen.

5. Identified autocorrelation and used that to guide selection for the best fitting autoregressive moving average (ARMA) and autoregressive integrated moving average (ARIMA) models.


#### Volatility Forecasting

In this section, the project used the time-series GARCH (generalized autoregressive conditional heteroskedasticity) or EGARCH (exponential GARCH) models to forecast short-term volatility in the Japanese yen.
The following is a list of the steps taken:

1. Estimated either a GARCH or EGARCH model using the arch python package.

2. Identified patterns of clustered and/or high yen volatility.

3. Forecasted three-day volatility of the yen using a GARCH or EGARCH model.

#### Optional Challenge—Out-of-Sample Predictions

Last, the project applied Scikit-Learn regression model under a testing approach commonly used by data scientists and quantitative traders when dealing specifically with time-series data.

1. Used Pandas datetime indexing to slice the dataset into a training and test set, and compared model performance (root mean square error or RMSE) between the two (a one-shot approach).

2. Created a rolling-out-of sample approach that updates to a new model each week using the most recent data and evaluated performance on data over the following week.


#### Optional Challenge—Futures Spread Prediction

Futures spreads, as opposed to futures contracts, often exhibit more seasonal patterns and are generally easier to predict. 

1. Navigated the Quandl website, pulled futures data one-month and two-month continuous Japanese yen futures contracts.

2. Constructed a futures spread, by taking [(2 month contract return) - (1 month contract return * -1)]. This was effectively a bet that the yen will be stronger two months from now than it will be a month from now (regardless of what it is today).  

3. Used an ARMA model and the out-of-sample approaches to see if it is possible build a model with a low RMSE.

## Built With

* [Python](https://www.python.org/) - Programming language.
* [Pandas](https://pandas.pydata.org/) - Data analysis and manipulation tool.
* [Quandl](https://www.quandl.com/) - API used to access econonmic and financial data.

## Authors

* **Billie Thompson** - *Initial work* - [PurpleBooth](https://github.com/PurpleBooth)