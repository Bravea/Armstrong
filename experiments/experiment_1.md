## Experiment 1
### Main
Experimental settings that are constant throughout the experiment:  
* Objective: Predict future return 1, 2, 3, 5, 8, 13, 21 days ahead
* Task type: Classification
* Architecture: Feedforward

### Variations
* Output: One hot categorical prediction t+_n_ time steps in the future.
  * _n_ = [1, 2, 3, 5, 8, 13, 21]
  * categories = [[large pos, pos, no change, neg, large neg], [pos, no change, neg]]
* nr of input nodes
* type of technical indicators 
* nr of layers
* nr nodes in each layer
* dropout setting
* threshold values for output classes
* weight initialisation
* batch size

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
