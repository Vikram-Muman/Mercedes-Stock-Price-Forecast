Building a Price Series ARIMA Model for Mercedes Stock Price Prediction 

 

Project Brief: 

The aim of this Python project is to build and train an ARIMA model, to forecast and predict future stock prices for the German automotive company Mercedes-Benz. With the help of Python libraries such as NumPy, Pandas and Matplotlib, the forecasting process involves several key steps, including dataframe cleansing and preparation, tuning optimal parameters, training, and testing the model's performance. A critical aspect of time series forecasting is ensuring stationarity, meaning the statistical properties of the series does not change over time. In this project’s Jupyter Notebook you can follow the code of me carrying out the Augmented Dickey-Fuller (ADF) test, used to statistically verify stationarity. I then transform my series from non-stationary to stationary by differencing. With my stationary series I pick my models parameters to test and train my model with, and finally fit my model to the prepared data to generate accurate forecast values of future closing stock prices. 

 

ARIMA Background 

Auto Regressive Integrated Moving Average (ARIMA) model is a forecasting algorithm that takes into account past values to predict future values. 

As shown in Fig. 1, the ARIMA bases its predicted values off the lags and lagged forecast errors. 

![Figure 1 - ARIMA Model Formula](ARIMA%20Formula.png)

 

Stationarity 

In order to produce and fit an ARIMA model, our time series must be stationary. 

Stationarity refers to the time series being mean reverting, in other words exhibits a consistent distribution over time. 

Due to ARIMA being an auto regressive model, the model is a linear regression that uses its AR lags as predictors. A stationary time series is necessary as linear regression works best when predictors are not dependent on each other, otherwise we may run into multicollinearity. 

In order to check if our time/price series is stationary we use the Augmented Dickey Fuller (ADF) test. If our p value > 0.05, then the series is non-stationary and we must find the order of differencing. 

To find the order of differencing we either can manually carry out an acf plot, or run the acf test to get our term d (order of differencing). 

 

ARIMA Parameters 

ARIMA models are characterised by 3 terms; p, d and q. 

p refers to the order of the Auto Regressive (AR) term. 

d refers to the number of differencing required to make the time series stationary. 

q refers to the order of the Moving Average (MA) term. 

In the above section you can see how we compute our d term. 

To get our p term we inspect the Partial Autocorrelation (PACF) plot.  Our p term would be characterised by the number of lags which is above the significance line. 

To get our q term we inspect the Autocorrelation (ACF) plot. Our q term would be characterised by the number which is above the significance line. 

 

Conclusion 

ARIMA time series forecasting was used as the forecast model due in this project due to it being a widely used and established model, relatively simple, and effective in short-term forecasting. 

ARIMA time series modelling is not the best for forecasting stock prices, as past close prices are not fully indicative of future prices, there are many other factors such as seasonality that ARIMA does not account for, however ARIMA can give a general trend prediction. 
