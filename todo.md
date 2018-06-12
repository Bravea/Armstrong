# TODO

Backtrader
# todo 
* [ ] Add multiple stocks
* [ ] Easily compare/view the different strategy result

### Data
Get/create input data from stocks in CSV format, between dates from 20YY-MM-DD to 2018-MM-DD:
* GOOG
* IBM
* APPL
* ...

Create artificial close price data: 
* Sinus + no trend
* Sinus + up trend
* Sinus + down trend

### Comparison Strategies
Develop the following default comparison strategies:
~~
* [x] Random: 
 * at each time step _t_ randomly BUY, SELL or HOLD.
* [x] Naive: 
  * if close price at time _t_ > close price at time _t-1_ then BUY.
  * elif close price at time _t_ < close price at time _t-1_ then SELL.
  * else HOLD. 
* [x] Buy&Hold
~~

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

## TO BE ABLE TO RUN ML-ALGO
### Comparison with expert recommendations
Avanza, Nordnet, Google Finance, Bloomberg etc. all give buy/sell advice about future investments.
### Get and save recommendation data from different sites
### Use saved data as input to ML-algo in order to determine if and to what extent the recommendations are good. 



### Input data 
Saved data to be used as input data for ML algo.
* save indicators and all other input data (i.e. stock data feed(s), forex, oil, etc.) to one single csv-file.

### Input data 



