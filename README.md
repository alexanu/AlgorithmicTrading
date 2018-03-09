# Algorithmic Trading Program
### Contributors: Jack Pham, Moritz Droste, Lauren Wong, Ajay Bhatia
# Abstract
<p> Trading the financial markets no longer embodies in the form of trading floor in NYSE, packed with suits and sweats, but rather automated through computers. Tycoon firms like Goldman Sachs is the number one High Frequency Trading firm, with the majority of its revenue come from automated trading aka algorithmic trading, at high frequency (fractions of a second)</p>
<p> We are trying to build an easily accessible algorithmic trading program that allows users to backtest and live trade their trading strategies on any desired market. For the current system, we are using even-driven programming to develop our backtesting engine. This is so that the codes can be re-use to not just backtest, but live trade as well. In addition, by using event-driven backtests, we simulate a much more realistic scenerio of trading and preserve non-bias decisions making.</p>

# Blueprint
<ul>
<li><strong>Event:</strong> This is the key component in our engine. Due to the nature of event-driven programming, we require a fundamental class that could identify what action to proceed taking in an event loop</li>
</ul>
<ul>
<li><strong>DataFrame:</strong> We need a dataframe that contains all data needed for portfolio and strategy to use. Why don&#39;t we just incorporate it in those scripts? This is for future purposes to implement the same dataframe for live trading as well. We don&#39;t want to re-use codes or write a completely different scrips of data feed. We want to construct a dataframe that is applicable for multiple purposes.</li>
</ul>
<ul>
<li><strong>Strategy:</strong> This is for applying strategy to your trading purposes. This component will take market data, perform calculations and generate a signal event for portfolio to use. The signal will essentially tell portfolio on what to buy, the direction and the time stamp</li>
</ul>
<ul>
<li><strong>Portfolio:</strong> Essential for all trading purposes. We need a portfolio management class that handles the order and logic of positions being placed, current and subsequents. In addition, it can also perform risk management, position sizing, etc if we need it to be more complex. This takes the signal event, generated by strategy and create an order event.</li>
</ul>
<ul>
</ul>
<ul>
<li><strong>DataFrame:</strong> We need a dataframe that contains all data needed for portfolio and strategy to use. Why don&#39;t we just incorporate it in those scripts? This is for future purposes to implement the same dataframe for live trading as well. We don&#39;t want to re-use codes or write a completely different scrips of data feed. We want to construct a dataframe that is applicable for multiple purposes.</li>
</ul>
<ul>
<li><strong>Strategy:</strong> This is for applying strategy to your trading purposes. This component will take market data, perform calculations and generate a signal event for portfolio to use. The signal will essentially tell portfolio on what to buy, the direction and the time stamp</li>
</ul>
<ul>
<li><strong>Portfolio:</strong> Essential for all trading purposes. We need a portfolio management class that handles the order and logic of positions being placed, current and subsequents. In addition, it can also perform risk management, position sizing, etc if we need it to be more complex. This takes the signal event, generated by strategy and create an order event.</li>
</ul>
<ul>
<li><strong>Execution:</strong> Following up from above, after the order event is generated by Portfolio, it will then be passed to execution. This component is responsible for simply carrying out order placements, either simulated or live trade. It will also then use event to generate a description of its execution.</li>
</ul>

# Progress Log
<div>
<strong>Started date:</strong> February 2nd 2018</div>
<div>
<strong>Last Updated: </strong>March 1st 2018</div>
<h3 style="font-style: italic;">Week 1-4</h3>
<p>For the first 4 weeks, we worked on how to obtain financial data without having to manually download them online and place them in our database folder. For this to happen, we explored various API sources and decided on using <a href="http://bit.ly/2DXVpKM">Alpha Vantage API</a> to pull stocks data and their technical indicators in different time frames. In addition, we also use <a href="http://bit.ly/2E7srZP">OANDA API</a> to capture FOREX data (for later implications, right now we are focusing on stocks) with much more flexibility and availability compared to Alpha Vantage's stocks data.</p>

<h3 style="font-style: italic;">Week 5- PRESENT</h3>
<p> After obtaining data to apply to our program, we devised a blue print shown above, breaking down components of a basic trading engine. Now we will start working on different components, building them from scratch through Python and focusing on utilities applicable to backtesting purposes. Therefore, when we try constructing portfolio management or execution, it will most likely be very basic, to test out and ensure that the blueprint flows smoothly. Later on, we will start developing a more indepth and sample strategies, thus update our blueprint to dissect the inter-functionalities between different components.</p>
