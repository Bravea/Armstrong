[A hybrid stock trading framework integrating technical analysis with machine learning techniques](https://www.sciencedirect.com/science/article/pii/S2405918815300179)

ANN is trained to predict a Trading Signal, i.e. when to buy an sell.
Input to the ANN is 

## Trend 
A Simple Moving Average (SMA) is used over the last 15 time steps (SMA15) for classifying the stock market movement as upward (Uptrend) or downward (downtrend) as follows:
* Trend = 'up': If closing price > SMA15 and SMA15 is rising for the last 5 days.
* Trend = 'down': if closing price < SMA15 and SMA15 is falling for the last 5 days.
* Trend = 'no': Otherwise.
The Trend is only used in order to be able to calculate the Trading Signal (TS).

## Trading Signal
A Trading Signal (TS) is calculated. TS is used as training target output to the ANN. Depending on if the last occurance of the Trend was 'up' or 'down' different calculations are used. Instances of 'no'-trend are ignored, i.e.:
* TS = TSup: if last occurance of the Trend was 'up'
* TS = TSdown: if last occurance of the Trend was 'down'

TSup and TSdown are given by:
* TSup = (close(t) - closeMin) / (closeMax – closeMin) × 0.5 + 0.5
* TSdown = (close(t) - closeMin) / (closeMax – closeMin) × 0.5

Where: 
* closeMin = Min(close(t), close(t+1), close(t+2))  
* closeMax = Max(close(t), close(t+1), close(t+2))

**close**|**closeMin**|**closeMax**|**TSup**|**TSdown**|**Trend**|**TS**
:-----:|:-----:|:-----:|:-----:|:-----:|:-----:|:-----:
1877.7|1877.7|1904.01|0.5|0|down|0
1886.76|1886.76|1941.28|0.5|0|down|0
1904.01|1904.01|1941.28|0.5|0|down|0
1941.28|1927.11|1950.82|0.7988|0.2988|no|0.2988
1927.11|1927.11|1964.58|0.5|0|no|0
1950.82|1950.82|1964.58|0.5|0|no|0
1964.58|1961.63|1985.05|0.563|0.0629|no|0.0629
1961.63|1961.63|1985.05|0.5|0|no|0
1985.05|1982.3|1994.65|0.6113|0.1113|up|0.6113
1982.3|1982.3|2039.68|0.5|0|up|0.5
1994.65|1994.65|2039.68|0.5|0|up|0.5
2039.68|2038.25|2039.68|1|0.5|up|1
2038.25|2038.25|2039.82|0.5|0|up|0.5
2039.33|2039.33|2041.32|0.5|0|up|0.5
2039.82|2039.82|2063.5|0.5|0|up|0.5
2041.32|2041.32|2063.5|0.5|0|up|0.5
2063.5|2059.82|2063.5|1|0.5|up|1
2060.31|2026.14|2060.31|1|0.5|no|1
2059.82|2026.14|2059.82|1|0.5|no|1


```python
```
## Technical Indicators
The input to the NN are the following technical indicators:
* SMA
* MACD
* K%
* D%
* RSI
* R%

### Simple Moving Average (SMA)
SMA(n) = (close(t) + close(t-1) + close(t-2) + . . . close(t-n)) / n

Where:
* n is the number of periods in the SMA
* close(t) is the closing price

### Moving Average Convergence and Divergence (MACD): 
The MACD shows the relationship between two exponential moving averages of prices.

MACD = EMA12 - EMA36

EMA(t) = (close(t)-EMA(t-1)) x m + EMA(t-1)

where:
* m = 2 / (no of days to be considered + 1)

### Stochastic KD
Stochastic provides a mean of measuring price movement velocity. K% measures the relative position of current closing price in a certain time range, whereas D% specifies the three day moving average of K%.

K%(t) = [ close(t) - L(i) ] / [ (H(i) - L(i)] x 100

D%(t) = [K%(t) + K%(t-1) + K%(t-2)] / 3

where:
* close(t) is the closing price
* L(i) is the lowest price of the last i days.
* H(i) is the highest price of the last i days.

### Relative Strength Index (RSI):
RSI is a momentum indicator calculated as follows:

RSI(t) = 100 - 100 / (1+RS(t))

where
* RS(t) = Average of t days where closing price was up / Average of t days where closing price was down 

### Larry William's R%:
William's R% is a stochastic oscillator, calculated as follows:

R%(t) = [ H(i) - close(t) ] / [ H(i) - L(i)] x 100

where:
* close(t) is the closing price
* L(i) is the lowest price of the last i days.
* H(i) is the highest price of the last i days.

## Neural Network

Model:
* input i 6 technical indicators.
* output is one (1) node.
* training is of type regression.

## Trading decision
Determine predicted trend (Trendpred) based on predicted trading signal (TSpred):
* Trendpred = 'up': if TSpred > 0.5.
* Trendpred = 'down': if TSpred <= 0.5.

Dtermine Buy, hold or Sell according to:
* BUY: if next day trend = 'up'
* SELL: if next day trend = 'down'
* HOLD: if BUY or SELL decisiom exist




