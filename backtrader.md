
# Strategy Performance Metrics
How to select relevant metrics in order to be able to a) determine if a strategy is good and b) compare different strategies.

Measuring performance only in profit percentages is likely to be misleading. It doesn't take into account the size and the duration of drawdowns and variability. I.e. Two strategies can have identical Annual ROI but differ in drawdown and variability. 

Ideally, a strategy :

* should give as high profit as possible.
* should have as low drawdown as possible.
* should have as low variability as possible, at least downwards variability. Volatility is a measure of the standard deviation (square root of the variance) over a certain time interval.


However at a steady rate (low risk) with minimum of drawdown
Target Ideal


The metric or combination of metrics should optimize the following parameters:
* __Profit__
* __Risk__
* __Drawdown__

* __Net Profit %__, higher is better.
* __Risk

+/- are given for:
+ Metrics in percentages are better than absolutes
+ Metrics that include risk is better
+ Metrics that are insensitive to 
+ Metrics that include 


|Metric| Description | Comment | +/- | Benchmark |
|------|-------------|--------------|----|-----------|
|__Net Profit__ | Ending Capital-Initial Capital |  | + | ? |
|  __Net Profit %__ | Net Profit expressed in % terms. For ex: if Initial Capital=100000, Ending Capital=200000, then, Net Profit %=(200000-100000)/100000 * 100 = 100%. | | | |
|  __Exposure %__.   | It is the net average exposure of your trading system for the period of backtesting. It is calculated as the sum of individual bar exposures divided by total number of bars. Individual bar exposure is calculated as the ratio of open positions value to the overall portfolio equity for that particular bar. Let’s suppose you are backtesting your strategy on daily timeframe, if at the end of Day 1 your open position value is 10000 and portfolio equity is 100000 then bar exposure for that particular day is 10.  | | | |
|  __Net Risk Adjusted Return %__. | It is the ratio of Net Profit % and Exposure %. For ex: If net profit %=100 and Exposure %=10, then Net Risk Adjusted Return %=100/0.1=1000  | | | |
|  __Annual Return %__.  |  It is the compounded annual return %. It is the annualized rate at which capital has compounded over the backtest period.  | | | |
|  __Risk Adjusted Return %__. |  It is the ratio of Annual return % and Exposure %. For ex: If Annual return %=20 and Exposure %=10, then Net Risk Adjusted Return %=20/0.1=200 | | | |
|  __All Trades__. |  Total number of trades executed as per the backtested strategy in specified period. | | | |
|  __Winners__. |Total number of winning trades. | | | |
|  __Losers__. |  Total Number of losing trades. | | | |
|  __Total Transaction costs__. |  Total Transaction costs based on brokerage per trade settings. For Ex: If Total number of Trades=100, and Brokerage per Trade=50, then Total Transaction costs=100 * 50 = 5000 | | | |
|  __Average Profit__.  | It’s the ratio of total profit and number of winners. For Ex: if total profit=200000, number of winners=50, then Average Profit=200000/50=4000  | | | |
|  __Average Loss__.  | It’s the ratio of total loss and number of losers. For Ex: if total loss=-100000, number of losers=50, then Average Loss=-100000/50=-2000  | | | |
|  __Average Profit/Loss__. |  Also known as Expectancy, It’s calculated as (Total Profit+ Total Loss)/(Number of trades). It represents expected gain/loss per trade. For Ex: If Total Profit=200000, Total Loss=-100000, Number of trades=100, then Expectancy=(200000-100000)/100=1000 | | | |
|  __Average Bars Held__.  |  Average holding period per trade. If you are backtesting on Daily timeframe, then this represents the average number of days a Trade is held. | | | |
|  __Max. Consecutive Winners__. |  This represents the maximum number of consecutive wins in the whole backtest period. High value is better  | | | |
|  __Max. Consecutive Loses__. |  This represents the maximum number of consecutive losses in the whole backtest period. Low value is better.
|  __Maximum trade drawdown__.  | The largest peak to valley decline experienced in any single trade. The lower the better. | | | |
|  __Maximum trade % drawdown__.  |  The largest peak to valley percentage decline experienced in any single trade. The lower the better. | | | |
| __Maximum system drawdown__.  |  The largest peak to valley decline experienced in portfolio equity. The lower the better. | | | |
|  __Maximum system % drawdown__.  | The largest peak to valley percentage decline experienced in portfolio equity. The lower the better. | | | |
|  __Recovery Factor__.   | The ratio of net Profit and maximum system drawdown. Higher the better.For Ex: If net Profit=100000, maximum system drwadoen=50000, the Recovery Factor=100000/50000=2 | | | |
|  __CAR/MaxDD__.  | Compound Annual % Return divided by Maximum system % drawdown. Good if bigger than 2. For Ex: If Annual Return %=30, and Maximum system % drawdown=10, then CAR/MaxDD=30/10=3 | | | |
| __RAR/MaxDD__.  | Risk adjusted return divided by Maximum system % drawdown. Good if bigger than 2. For Ex: If Risk adjusted Return %=50, and Maximum system % drawdown=10, then CAR/MaxDD=50/10=5 | | | |
|  __Profit Factor__.  |  Ratio of Total profit and Total Loss. Higher the better. For ex: if Total profit=200000, Total loss=100000, then Profit Factor=200000/100000=2 | | | |
|  __Payoff Ratio__.  | Ratio of Average profit and Average loss. Higher the better. For ex: if Average Profit=10000, Average loss=4000, then Payoff Ratio=10000/4000=2.5 | | | |
| __Standard Error__.  | Standard error measures choppiness of equity curve. The lower the better. | | | |
|  __Risk-Reward Ratio__.  | Ratio of potential risk and potential reward of Trading system. Higher is better. Calculated as the slope of equity line (expected annual return) divided by its standard error. | | | |
| __Ulcer Index__.  | A technical indicator that measures downside risk, in terms of both depth and duration of price declines. The Ulcer Index (UI) increases in value as the price moves farther away from a recent high, and falls as the price rises to new highs. Detailed calculation example for UI [here](http://www.tangotools.com/ui/ui.htm). |  UI tries to improve on __Standard Deviation__ as a measure of risk by only considering the volatility of an asset in the downward direction | ++ | Lower is better, e.g. < 10% |
|  __Sharpe Ratio of trades__.  | Measure of risk adjusted return of investment. |  | + | Higher is better. Above 1.0 is good, more than 2.0 is very good.|
|  __K-Ratio__.  | Detects inconsistency in returns. Should be 1.0 or more. The higher K ratio is the more consistent return you may expect from the system. | | | |


List taken from [Understanding Amibroker backtest report](http://tradingtuitions.com/understanding-amibroker-backtest-report/)
According to [DESIGN AND IMPLEMENTATION OF AUTOMATED TRADING SYSTEMS](https://diplomovka.sme.sk/zdroj/3633.pdf) Michal Kecera, 2010.
The following metrics are ___useful___ for the purpose of comparing and evaluating different strategies:

* __Modified Recovery factor__ = (Annualized Net Profit($) - Annual Required Profit($)) / Maximum Drawdown($)
* __Modified Compounded Annual Return/Maximum Drawdown__ = (Compounded Annual Return - Annual Required Return) / Maximum Drawdown(%)

Compounded Annual Return = ((Initial Equity/Final Equity)^(1/# of years))-1


## Links
* https://diplomovka.sme.sk/zdroj/3633.pdf
* https://ntguardian.wordpress.com/2017/06/19/walk-forward-analysis-demonstration-backtrader/
* https://optimusfutures.com/tradeblog/archives/ratios-used-in-evaluating-automated-trading-systems/

