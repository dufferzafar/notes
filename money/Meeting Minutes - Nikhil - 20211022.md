# Meeting with Nikhil

* Catchup regarding current investments

    * Any new assets?
        * Gold!

    * Mutual funds

        * **Shadab**
        ```
        Large cap 56.77% Mid cap 5.14% Small cap 7.42%

            Qty. 	Buy avg. 	Buy value 	Prev. close 	Present value 	P&L 	P&L chg.
        EDELWEISS BALANCED ADVANTAGE FUND - DIRECT PLAN
            371.949 	37.64 	13,999.29 	39.64 	14,744.06 	744.77 	+5.32%
        ICICI PRUDENTIAL TECHNOLOGY FUND - DIRECT PLAN
            528.473 	145.7 	76,996.29 	178.51 	94,337.72 	17,341.43 	+22.52%
        MOTILAL OSWAL S&P 500 INDEX FUND - DIRECT PLAN
            1,323.026 	15.12 	19999 	15.33 	20,281.33 	282.33 	+1.41%
        PARAG PARIKH FLEXI CAP FUND - DIRECT PLAN
            3,265.216 	45.94 	1,49,992.38 	54.88 	1,79,180.69 	29,188.3 	+19.46%
        UTI NIFTY INDEX FUND - DIRECT PLAN
            1,443.423 	103.91 	1,49,992.6 	122.61 	1,76,980.26 	26,987.66 	+17.99%
        UTI NIFTY NEXT 50 INDEX FUND - DIRECT PLAN
            6,608.872 	13.62 	89,995.49 	15.69 	1,03,676.68 	13,681.19 	+15.2%
        ```

        * **Nikhil**
        ```
            Qty. 	Buy avg. 	Buy value 	Prev. close 	Present value 	P&L 	P&L chg.
        ICICI PRUDENTIAL TECHNOLOGY FUND - DIRECT PLAN
            113.086  168  18,998.97  178.51  20,186.98  1,188.01  +6.25%
        MOTILAL OSWAL NASDAQ 100 FUND OF FUND - DIRECT PLAN
            1,028.016  22.86  23,498.86  24.24  24,921.78  1,422.92  +6.06%
        MOTILAL OSWAL S&P 500 INDEX FUND - DIRECT PLAN
            1,561.944  14.4  22,498.97  15.33  23,943.82  1,444.85  +6.42%
        PARAG PARIKH FLEXI CAP FUND - DIRECT PLAN
            2,327.886  45.32  1,05,494.68  54.88  1,27,744.14  22,249.46  +21.09%
        UTI NIFTY INDEX FUND - DIRECT PLAN
            1,245.114  105.61  1,31,493.27  122.61  1,52,665.3  21,172.03  +16.1%
        UTI NIFTY NEXT 50 INDEX FUND - DIRECT PLAN
            7,376.578  13.62  1,00,495.12  15.69  1,15,720.07  15,224.95  +15.15%
        GOLDBEES-E
            1008  40.38  40,701.92  41.18  41,509.44  807.52  +1.98%
        ```

* Problem 0: Where do we go from here?

    * Do we need other MFs?
        * Any active ones?

        * Sectoral?
            * Medical
            * Technology
            * FMCG

        * Debt?

* Problem 1: Historical analysis

    * How are NIFTY indexes categorized?
        * [Nifty 50 details](https://www1.nseindia.com/products/content/equities/indices/nifty_50.htm)

        * sort by mcap desc
        * 1-50, 50-100, 100-250, 250-500
        * weight = mcap / sum(mcap)

    * What %age of Nifty 50 / Nifty Next 50 etc has given the "best" returns?

        * Mutual funds (market cap based)
            * L: 70, M: 20, S: 10
            * N: 70, NN: 20, M: 10
            * N: 70, NN: 20, M: 7, S: 3
            * `r = f(l, m, s)`
            * `r = f'(n, nn, sp)`

        * Asset class based
            * E: 70, D: 15, G: 10, Bank: 5
            * `r = g(e, d, g, b)`

        * Include Active funds?

        * Perform a grid search over the parameters

    * What data do we need?
        * NAV history

    * Challenges

        * Data sources
            * Scrape MF factsheets

            * Scrape API of groww / coin / k____

            * Paid source?
                * Tickertape / Trading view
                * No API for MF data?

            * Metrics
                * http://passivefunds.in/indian-etfs-index-funds-data/

            * AMFI
                * [GitHub search for decent code](https://github.com/search?o=desc&q=amfi&s=updated&type=Repositories)

* Problem 2: Lumpsump investment
    * What if you had 50 lakh in hand right now?

    * Diversification

        * Across asset classes
            * `E`quity, `D`ebt, `G`old, `R`eal Estate, `C`rypto, `B`ank

        * Across products in a particular class
            * E: Stocks, ETF, Active MFs, Index MFs
            * D: Bonds, Debt Funds (Gilt, PSU...)
            * G: Physical gold (ornaments/coins), SGB, Gold ETF, Gold MF
            * R: Plot, Appartment+rent, ReITs
            * C: BTC, ETH, ADA, SOL
            * B: Cash, FD

* Problem 3: Should you buy a house or rent it?
    * How to do the analysis?

* Problem 4: When are lumpsum investments better than SIP? STP?

## Definitions

* Goal based investing
    * [freefincal](https://freefincal.com/)

    * g: dur, min_tAmt
        * min_t: 20L -> fv(20, 18, ir, irr)
        * curve / extrapolation
        * Present Value, Future Value
        * XIRR

    * example:
        * g(son): 18yrs, SIP

## Misc. Questions

* What if market sees a "correction" of 4-5%?
    * or 15% - a _crash_
    * Do you buy lumpsum?
    * Continue your SIPs?
    * Increase your SIPs?
    * Stop your SIPs?

    * Dollar Cost Averaging (DCA)

* Risk Scenarios

    * 2008
    * 2020_COVID
    * Black Friday
