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
* `#` of input nodes
* type of technical indicators 
* # of layers
* # nodes in each layer 
* dropout setting
* Threshold values for output classes
* more...

### Results
#### Prediction
Mean Average Percent Error (MAPE):

#### Backtest
Buy&Hold
Naive
