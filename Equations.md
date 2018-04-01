## Trend 
A Simple Moving Average (SMA) are used over the last 15 time steps (SMA15) for classifying the stock market movement as upward (Uptrend) or downward (downtrend) as follows:
* Trend = 'up': If closing price > SMA15 and SMA15 is rising for the last 5 days there is an Uptrend.
* Trend = 'down': if closing price < SMA15 and SMA15 is falling for the last 5 days there is a Downtrend.
* Trend = 'no': Otherwise there is no trend.

## Trading Signal
A Trading Signal (TS) is calculated depending on if the last occurance of the Trend was 'up' or 'down'. Instances of 'no'-trend are ignored.

* TS = TSup: if last occurance of the Trend = 'up'
* TS = TSdown: if last occurance of the Trend = 'down'

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



# close: close price at time t
# trend: trend  
# sma15: Simple Moving Average at time t over 15 last close prices


(close - closeMin) / (closeMax – closeMin) × 0.5 + 0.5

(close - closeMin) / )closeMax – closeMin) × 0.5

```python
```
### NEXT
