## Trend 

## Trading Signal
```python
# close: close price at time t
# trend: trend  
# sma15: Simple Moving Average at time t over 15 last close prices

trendUp(t) = 1 
if close(t) > sma15(t) and sma15(t) > sma15(t-1) 
                       and sma15(t-1) > sma15(t-2)
                       and sma15(t-2) > sma15(t-3)
                       and sma15(t-3) > sma15(t-4)
                       and sma15(t-5) > sma15(t-5)
               else 

trendDown(t) = 1 if close(t) < sma15(t) and sma15(t) < sma15(t-1) 
                                      and sma15(t-1) < sma15(t-2)
                                      and sma15(t-2) < sma15(t-3)
                                      and sma15(t-3) < sma15(t-4)
                                      and sma15(t-5) < sma15(t-5)

Trend(t) = up if  

(close - closeMin) / (closeMax – closeMin) × 0.5 + 0.5

(close - closeMin) / )closeMax – closeMin) × 0.5


```
### NEXT
