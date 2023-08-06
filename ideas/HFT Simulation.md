# HFT Simulation

Implement an end to end high-frequency trading simulation

## Design

Exchange <-> MarketData / OrderFlow <-> Strategy

> Basics

* Exchange Simulator
    * FIX like protocol
    * Matching logic
    * OrderBook

* Strategy

* Plot security data?

> Complexity

* Where will the tick/quote/price data come from? random?
* What asset classes do we trade?
* What venues?

> Where will Tower specific components fit into the picture?

* Atom, SecurityMaster data?
* GTI, HistoryServer, PositionServer, PriceServer
* AlertsProxy, AlertsAggregator
* Risk checks, Surveillance Server
* TDM, TRM, RestrictionsUI, RiskDashboard, RiskLimitsUI
* TradeDash

* Dependencies like MSCI, PnLApp

> Do we also implement components like LDAP, MongoDB, Slack

* ldap could be a json file?
* mongodb could be another json file? or a directory containing json files?

> Do we only focus on Core Engg? or also go into other Divisions like Enterprise etc?

eh. doesn't make a lot of sense / not as exciting.

## Resources

* Trading
    * [Strategies/Agents](https://github.com/huseinzol05/Stock-Prediction-Models/tree/master/agent)
    * [OrderBook, Trader, MarketMaker, Spoofer](https://github.com/TCtobychen/HFT_simulation/blob/main/utils.py)
    * [Bid/Ask OrderBook Simulation](https://github.com/dougkna/order-book/blob/master/client/src/App.js)
    * [Simple exchange matching engine](https://github.com/robswc/market-agent-sim/tree/master/engines)
    * [Algoticks](https://github.com/jkotra/algoticks), [Algorithms](https://stdin.top/posts/write-algo-for-algoticks/)
    * [Robinhood Clone](https://github.com/ronilbhatia/EasyTrade)
    * [Zipline trading library](https://github.com/quantopian/zipline#quickstart)
    * https://github.com/chenhaotian/High-Frequency-Trading-Simulation-System

* MarketData
    * [Simulator & Processor](https://github.com/cdtait/simulation)

* Risk
    * [Value at Risk](https://risk-engineering.org/notebook/stock-market.html)
    * [Model portfolio risk](https://digitalcommons.usu.edu/cgi/viewcontent.cgi?article=2566&context=gradreports)
