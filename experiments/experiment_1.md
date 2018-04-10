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
* # of input nodes
  * weekdays: Yes/No
  * On Balance Volume (OBV)
  * Simple Moving Average (SMA)
  * BIAS 
  * Psychological Line (PSY)
* type of technical indicators 
* nr of layers
* nr nodes in each layer
* dropout setting
* threshold values for output classes
* weight initialisation
* batch size
<math xmlns:mml="http://www.w3.org/1998/Math/MathML" id="M15" overflow="scroll">
 <mrow><mi>A</mi><mi>S</mi><msub><mi>Y</mi><mn>4</mn></msub>
  <mo>=</mo>
  <mo stretchy="false">(</mo><mrow><msubsup>
  <mo stretchy="false">∑</mo><mrow><mi>i</mi>
  <mo>=</mo><mn>1</mn></mrow><mn>4</mn></msubsup><mi>S</mi><msub><mi>Y</mi><mrow><mi>t</mi>
  <mo>−</mo><mi>i</mi>
  <mo>+</mo><mn>1</mn></mrow></msub></mrow><mo stretchy="false">)</mo>
  <mo>/</mo><mn>4</mn></mrow></math>
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
