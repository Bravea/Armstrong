# Development process
From the financial-hacker.com
## 1) Selecting the model. Confirming it with price data 
The three prerequisites for a financial model:
1) Has a rational basis in market structure / trader behavior
2) Can be expressed in a program flow or formula
3) Has statistical significance in real price curves

Find an algorithm that detects the inefficiency in price curves.
* Do a statistic. Plot a histogram.
* Compare with random walk curves or shuffled price curves. Difference should be significant.
* Do NOT rely on other people‘s research! Scam is ubiquitous (-> "Elliott Waves", Rich Swannell)

## 2) Developing the trade algorithm
Example: Cycle strategy
* Detect the dominant cycle and phase.
* Generate a forerunning sine curve.
* Enter short at a sine peak.
* Enter long at a sine valley.
* Exit on reversal or after a half-period.

## 3) Developing the filter algorithm
A market inefficiency normally does not exist all the time.
Therefore, we need a filter for determining if the inefficiency is
present or not. In most cases the filter is more important than the
algorithm.
Example: Cycle strategy
* Measure the amplitude of the dominant cycle.
* Trade only when the amplitude is above a threshold.

## 4) Parameter adaption ("optimizing" / "training")
If the model has "free parameters":
* Find out how the strategy reacts on parameter changes.
* Find the most robust parameter range ("sweet spot").
* Adapt the strategy to different assets.
* Adapt it to different market situations (even while live trading).

Bad ideas:
* Optimizing too many parameters.
* Optimizing for peaks (= brute force or genetic optimization).

[Training a strategy in Zorro](http://zorro-project.com/manual/en/training.htm)
[Optimize Strategies in Backtrader](https://backtest-rookies.com/2017/06/26/optimize-strategies-backtrader/)

## 5) Test
* Test should cover all significant market periods (5-10 years).
* Any parameter adaption introduce bias to the test result.
* The bias renders backtests completely useless.
* The solution: Testing the system with data not used for the adaption - Walk-Forward Analysis.

Walk-Forward Analysis
* Roll a window over the simulation period
* Separate the window in a training and test section.
* Good: The test is out-of-sample and still covers most of the data.
* Bad: The system depends on two more parameters.

Main performance parameters:
* Wins divided by losses (Profit Factor)
* Annual profit in relation to drawdown (Calmar ratio)
(Drawdown must be normalized -> square root rule!)
* Annual return in relation to sigma (Sharpe ratio)
* Linearity of returns (R2 coefficient)

## 6) Reality check

## 7) Implementing risk and money management
* Use a stop loss for eliminating negative outliers.
* Do not use profit targets. (If you really want to, use a profit-lock mechanism instead).
* Use an algorithm for calculating the optimal investment per portfolio component (Kelly, OptimalF, Markowitz).
* Re-invest only the square root of your profits.
* Supervise your system permanently and compare live results with backtest results (-> „Cold Blood Index“).


# Performance metrics for strategy comparison



| __Metric__ | __Example__| __Description__ |
|--------------------|---------------|------------------------|
| Annual return (AR) |||
| Profit Factor (PF) | | The sum of all profits divided by the sum of all losses. A neutral strategy has a value of 1. A loosing strategy is < 1. Profitable strategies are usually between 1.1 and 1.8. 

Profit Factor: Gross profit divided by the absolute value of gross loss. Profit factors of 1.5 or
more suggest a strong system. A trading system or method with a low profit factor could
become unprofitable with just a slight change in market dynamics
|
| Sharpe ratio (SR) || Reward-to-variability ratio where increased variability is equated with higher risk. The higher SR the better its returns relative to the investment risk.   |
| R2 coefficient (R2) || Measures the linearity of the equity curve. It is compared with a line through its start and end points. An R2 of 1   |
| Ulcer index (UI) || Average depth in drawdown in percent. A good strategy should haven an UI < 10%. |
||||
|Pessimistic |||

[Better Sharpe ratio?](https://www.crystalbull.com/sharpe-ratio-better-with-log-returns/)
[R-SQUARED AS AN ESTIMATION OF QUALITY OF THE STRATEGY BALANCE CURVE](https://www.mql5.com/en/articles/2358)


| __Gross win/loss__ | 100$ / -100$ | All accumulated wins and losses at the end of the simulation period. |
| __Average profit__ | $/year, $/month, $/day  | Yearly, monthly and daily average profit. |

__Links__

http://viewpdxblue.com/2017/03/01/emini-trading-analysis-win/
http://viewpdxblue.com/2015/12/03/risk-of-ruin-calculations/
http://viewpdxblue.com/2017/05/16/make-a-monte-carlo-simulation-with-excel/
http://www.adaptrade.com/MSA/MSA3UsersGuide.pdf

