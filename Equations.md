## Trend 
A Simple Moving Average (SMA) are used over the last 15 time steps (SMA15) for classifying the stock market movement as upward (Uptrend) or downward (downtrend) as follows:
* Trend = 'up': If closing price value is greater than SMA15 and SMA15 is rising for the last 5 days then there is an Uptrend, i.e. Trend = 'up'
Else if closing price value is lower than SMA15 and SMA15 is falling for the last 5 days then trend is Downtrend, i.e. Trend = 'down'
Else there is no trend, i.e. Trend = 'none' 

## Trading Signal
A Trading Signal (TS) is 

# close: close price at time t
# trend: trend  
# sma15: Simple Moving Average at time t over 15 last close prices

trendUp(t) = 1 
if close(t) > sma15(t) and sma15(t) > sma15(t-1) and sma15(t-1) > sma15(t-2) and sma15(t-2) > sma15(t-3) and sma15(t-3) > sma15(t-4) and sma15(t-5) > sma15(t-5)
               else 

trendDown(t) = 1 if close(t) < sma15(t) and sma15(t) < sma15(t-1) 
                                      and sma15(t-1) < sma15(t-2)
                                      and sma15(t-2) < sma15(t-3)
                                      and sma15(t-3) < sma15(t-4)
                                      and sma15(t-5) < sma15(t-5)

Trend(t) = up if  

(close - closeMin) / (closeMax – closeMin) × 0.5 + 0.5

(close - closeMin) / )closeMax – closeMin) × 0.5

```python
```
### NEXT
