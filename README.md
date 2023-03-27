# Module 20 - Capstone Project - Draft
First version of the capstone project | Machine Learning and AI | Berkeley

### IBOVESPA Forecast

**Nathalia Moreira**

#### Executive summary

The objective of my project will be to predict the value of the Ibovespa index. 
This index is followed by the main financial institutions in the country and is the thermometer of the Brazilian economy. 
It is composed of around 90 companies, to be part of the index companies must meet certain criteria, thus the index composition is periodically reviewed by the stock exchange (B3). Each company has a weight in the index related to its market cap, according to data released by B3 in March/2023, the companies with the greatest weight in the index are Vale, Itaú and Petrobras. The combination of the price of the shares that make up the index and the respective weight of each company, results in a value in points for the Ibovespa. 

#### Rationale

The projection of some indices (Nasdaq, Dow Jones, S&P 500, etc) created by the stock exchanges, it is important for investment analysts to decide on the investment in a country and for the stock exchanges themselves for the purpose of budgetary projections and planning.

#### Research Question

The main objective of the project is to predict the IBOVESPA index, of the stock exchange (B3) in the short and long term: to know how many "points" the index will have at the close of the next day (short term) and how many points the index will have in a period of approximately one year ahead

#### Data Sources

To obtain historical data, it was initially planned to consult B3's own website, but historical information is better structured on the Yahoo Finance website. The period from Jan/11 to Feb/2023 was used.

Ibovespa Historical Data:

https://finance.yahoo.com/quote/%5EBVSP/history?period1=1294012800&period2=1677542400&interval=1d&filter=history&frequency=1d&includeAdjustedClose=true

To complement the analysis, GDP, foreign investment and interest rate data obtained from The World Bank were used.
These data were extracted by API and correspond to the period from 2011 to 2021 (last year available for the indicators).

Annual macroeconomic data for Brazil:

https://databank.worldbank.org/reports.aspx?source=2&series=NY.GDP.MKTP.KD.ZG&country=BRA#

#### Methodology

As the dataset used is a time series, some techniques will be applied to project Ibovespa:
- Model 1 - Forecast with Decomposition Models: using STLForecast with ARIMA Model.
- Model 2 - ARIMA Model (using autoARIMA)
- Model 3 - Decision Tree
- Model 4 - LSTM
- Model 5 - LSTM (Multivariate time series)

#### Results

For long-term projections, the ARIMA model and Decision Tree were used.
For short-term projections, RNN models were developed using LSTM.
All models performed well with MAPE below 10%.
In the long-term projections, the models have a worse performance, as expected, given that stock indexes
are sensitive to factors that are difficult to predict. The decision tree model, despite presenting the best result,
has some points of attention, because it would be necessary to have a greater history to evaluate the model in a 100% out sample
of training.

##### MODEL: STL Forecast with ARIMA
MAE: 9804.081939810932
RMSE: 12380.873424658113
MAPE: 0.09084429616081456

##### MODEL: ARIMA WITH AUTO ARIMA
MAE: 6307.398857594435
RMSE: 7229.783306517954
MAPE: 0.0565395046286158

##### MODEL: DECISION TREE REGRESSOR
MAE: 1078.4567474048442
RMSE: 2991.333232921505
MAPE: 0.00989777241129776

##### MODEL: LSTM Univariate
MAE: 2346.120825
RMSE: 2929.357216
MAPE: 0.02120828616074523

##### MODEL: LSTM Univariate
MAE: 1508.4106382366485
RMSE: 2209.833155397609
MAPE: 0.015041793320616864

#### Outline of project

- https://github.com/nathaliafmoreira/Module-20---Capstone-Project/blob/main/Module%2020%20-%20Capstone%20Project%20-%20Ibovespa%20Forecast.ipynb

##### Contact and Further Information

nathaliafmoreira@gmail.com
