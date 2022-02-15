# Stock-Prediction-using-ARIMA<br>
ARIMA (Auto Regressive Integrated Moving Average) is a forecasting algorithm based on the idea that the information in the past values of the time series can alone be used to predict the future values.<br>
ARIMA models explain a time series based on its own past values, basically its own lags and the lagged forecast errors. <br> An ARIMA model is characterized by 3 terms p, d, q:<br> 
- p is the order of the AR term <br>
- d is the number of differencing required to make the time series stationary<br>
- q is the order of the MA term  <br>
-  As we see in the parameters required by the model, any stationary time series can be modeled with ARIMA models.  Let's explain the term Auto Regressive in ARIMA. It means the model is a linear regression that uses its own lags as predictors. Linear regression models, as we know, work best when the predictors are independent of each other. Otherwise we run into multicollinearity issues where the regression becomes unstable due to correlation. <br>
-   Now most price series are non stationary otherwise we would all be rich by just buying low and selling high, waiting for the prices to mean revert. So in order to make ARIMA models work we need to difference it, in this case to compute the returns as they usually randomly distribute around a 0 mean.  <br>
-  So we need to simply subtract the previous value from the current value. Now if we just difference once, we might not get a stationary series so we might need to do that multiple times.   And the minimum number of differencing operations needed to make the series stationary needs to be imputed into our ARIMA model. If the time series is already stationary, then d is 0. But in stock price forecasting it's almost never 0. <br>
-   p is the order of the Auto Regressive (AR) term. It refers to the number of lags to be used as predictors. <br> q is the order of the Moving Average (MA) term. It refers to the number of lagged forecast errors that should go into the ARIMA Model.  We'll use the Augmented Dickey Fuller (ADF) test to check if the price series is stationary.  The null hypothesis of the ADF test is that the time series is non-stationary. So, if the p-value of the test is less than the significance level (0.05) then we can reject the null hypothesis and infer that the time series is indeed stationary.  So, in our case, if the p-value is greater than 0.05 we'll need to find the order of differencing.

1223

