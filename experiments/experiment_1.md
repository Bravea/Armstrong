## Experiment 1

Input: Technical Indicators 
 Output: []
### Main
Experimental settings that are constant throughout the experiment:  
* Objective: Predict future return 1-10 days ahead
* Task type: Classification
* Architecture: Feedforward

### Variations
* Output: 
* One hot t+1 [large pos, pos, no change, neg, large neg], [pos, no change, neg]
* One hot t+2 [large pos, pos, no change, neg, large neg], [pos, no change, neg]
* One hot t+3 [large pos, pos, no change, neg, large neg], [pos, no change, neg]
* One hot t+5 [large pos, pos, no change, neg, large neg], [pos, no change, neg]
* One hot t+8 [large pos, pos, no change, neg, large neg], [pos, no change, neg]
* One hot t+8 [large pos, pos, no change, neg, large neg], [pos, no change, neg]
* One hot t+8 [large pos, pos, no change, neg, large neg], [pos, no change, neg]



* nr of input nodes
* type of technical indicators 
* nr of layers
* nr nodes in each layer ++
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
