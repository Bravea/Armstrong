## TODO

Backtrader

### Data
Get/create input data from stocks in CSV format, between dates from 20YY-MM-DD to 2018-MM-DD:
* GOOG
* IBM
* APPL
* ...

Create artificial close price data: 
* Sinus, no trend
* Sinus, up trend
* Sinus, down trend

### Comparison Strategies
Develop the following default comparison strategies:
* Random: 
  * at each time step _t_ randomly BUY, SELL or HOLD.
* Naive: 
  * if close price at time _t_ > close price at time _t-1_ then BUY.
  * elif close price at time _t_ < close price at time _t-1_ then SELL.
  * else HOLD.
* Buy&Hold

### Trading Strategies

* TS1
* TS2
* TS3
* TSn

### Metrics
Present the following metrics for each comparison and trading strategy:

* Calmar Ratio
* Sharpe Ratio
* Total Return, 
* Average Return, 
* Annualized Returns,
* Maximum Draw Down.

