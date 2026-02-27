# Statisitcal Arbitrage on Real Market Data:
By: Chabod M.

## Trading Strategy Development Steps
1. In-Sample Excellence
2. In-Sample Permutation Test
3. Walk Forward Test
5. Walk Forward Permutation Test

My thought process of how I access a trading strategy: 

I will use a moving average cross over as an example. I load in candle stick data, and compute a fast and slow moving average (FMA & SMA, respectively). At each bar we visually check to see if the FMA is above the SMA. I created a signal that denotes the strategy at each bar, 1 implicitly means we have a long position following that bar, and 0 represents no position. 

If we compute close to close returns, and shift them forward by one bar, we can mulitply the postion signal by the shifted return to get a return for each bar attributable to the strategy. 

The strategy returns at the same granularities of the bars are used to compute objective functions such as the profit factor or the sharp ratio. By having a return for each bar instead of each trade objective functions pass more data and the calculations and results are more stable. 

Higher granularities are Superior!
