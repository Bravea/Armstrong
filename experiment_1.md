## Experiment 1

Input: Technical Indicators 
 Output: []
### Main
Experimental settings that are constant throughout the experiment:  
* Objective: Predict future return 1-10 days ahead
* Output: One hot [large pos, pos, no change, neg, large neg]
* Task type: Classification
* Architecture: Feedforward

### Variations
* nr of input nodes
* type of technical indicators 
* nr of layers
* nr nodes in each layer 
* dropout setting
* threshold values for output classes
* more...

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
* Sortino ratio

Comparision Strategies:
* Buy&Hold
* Naive
