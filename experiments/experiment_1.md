## Experiment 1
Based on:
* [Predicting the Direction of Stock Market Index Movement Using an Optimized Artificial Neural Network Model](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4873195/)
Technical Indicators from Table 2.

### Main
Experimental settings that are constant throughout the experiment:  
* Objective: Predict future change in stock price _n_ days ahead.
* Task type: Classification.
* Architecture: Feedforward.

### Variations
* Input data: 3 stocks. [GOOG, IBM, AAPL]
* Output: One hot categorical prediction t+_n_ time steps in the future.
  * _n_ = [1, 2, 3, 5, 8, 13, 21]
  * categories = [[large pos, pos, no change, neg, large neg], [pos, no change, neg]]  
* nr of input nodes
  * weekdays: Yes/No
  * On Balance Volume (OBV)
  * Simple Moving Average (SMA)
  * BIAS 
  * Psychological Line (PSY)
  * ASY 

![Technical Indicators from table 2](https://github.com/Bravea/Armstrong/tree/master/pics/table2_technical_indicators.png) 
  
* type of technical indicators 
* nr of layers
* nr nodes in each layer
* dropout setting
* threshold values for output classes
* weight initialisation
* batch size

### Notes
* Make sure to balance the number of outputs / category. Ideally they are equal.


### Results
#### Prediction
Mean Average Percent Error (MAPE):

#### Backtest
Backtest on Out-Of-Sample data only. 

Performance metrics are:
* Total Returns
* Average Annual Return
* Maximum drawdown
* Sharpe ratio
 sharpe = (returns/std)*sqrt(365.25)
 std = std_dev(returns) 
* [Sortino ratio](https://github.com/PacktPublishing/PythonDataAnalysisCookbook/blob/master/Chapter%207/calmar_sortino.ipynb)

Comparision Strategies:
* Buy&Hold
* Naive
* Trend following


https://github.com/Crypto-toolbox/pandas-technical-indicators/blob/master/technical_indicators.py
