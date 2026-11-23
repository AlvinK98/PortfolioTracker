# Portfolio Tracker

A single-file, browser-based investment portfolio tracker for monitoring stocks, ETFs, cryptocurrency and selected Malaysia mutual funds across international markets. It brings portfolio valuation, performance indicators, trade records, allocation analysis and multi-currency reporting into one browser page.

Built with HTML, CSS and vanilla JavaScript. No build process, package installation, user account or application server is required.

![HTML5](https://img.shields.io/badge/HTML5-Single--file-orange?style=flat-square)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow?style=flat-square)
![Storage](https://img.shields.io/badge/Storage-Browser%20localStorage-blue?style=flat-square)

---

## Features

### Portfolio overview

- **Total portfolio value (AUM):** View current value, cost basis, total profit/loss, daily movement and realized profit/loss.
- **Multi-currency display:** Display consolidated AUM and profit/loss in CNY, GBP, HKD, JPY, KRW, MYR, SGD, TWD or USD.
- **Market and currency summaries:** Compare holdings, portfolio value, allocation and profit/loss by market or quote currency.
- **Interactive allocation chart:** Explore portfolio allocation by market with hover details and a legend.
- **Light and dark themes:** Switch the interface appearance.

### Holdings and performance

- **Ticker search:** Search for listed instruments with Yahoo Finance suggestions, or choose a market and enter a supported ticker. Binance provides cryptocurrency pair suggestions.
- **Automatic quotes:** Listed-stock prices are retrieved from Yahoo Finance; cryptocurrency prices are retrieved from Binance spot markets using USDT pairs.
- **Adjustable refresh:** Choose a stock refresh interval of 5, 10, 15, 30 or 60 seconds. Stock refreshes are throttled outside the relevant market session.
- **Performance indicators:** View daily movement, five-year all-time high (ATH), distance from ATH, month-over-month (MoM), quarter-over-quarter (QoQ), year-over-year (YoY) and year-to-date (YTD) performance where data is available.
- **Market hours:** When holdings are grouped by market, display session hours in Malaysia Time (MYT) and highlight markets that are currently open.
- **Filters and sorting:** Filter holdings by market, show or hide performance columns, group by market or currency, and sort the holdings and summary tables.

Historical metrics depend on provider coverage. Manually priced mutual funds do not have the same automatic market history as quoted instruments.

### Trade management

The holding form supports:

- **Buy / add:** Add a holding or add units to an existing position. Additional purchases update the weighted average cost (WAC).
- **Sell:** Record a sale, calculate realized profit/loss and reduce the remaining units. A fully sold position is removed from the holdings table.
- **Stock split / reverse split:** Adjust unit quantity and WAC using a split ratio.
- **Edit and delete:** Correct an existing holding or remove it from the portfolio.
- **Undo:** Undo up to 20 supported recent add, edit and trade actions.
- **Transaction history:** Review recorded buys, sells and splits in a paginated list. The history can be shown or hidden.

### Target allocation and portfolio history

- **Target allocation:** Set target percentages for each market. The tracker compares actual weights with the targets and estimates the value to buy or sell to rebalance based on current portfolio value.
- **Portfolio value chart:** Compare portfolio value with cost basis across 4H, 1D, 5D, 1M, 3M, 6M, YTD, 1Y and 5Y ranges.
- **Locally collected history:** Intraday snapshots and daily portfolio snapshots are saved while the tracker is in use. The chart does not reconstruct portfolio history from before tracking began.

### Backup and portability

- **Export:** Download a timestamped JSON backup containing holdings, FX settings, display currency, history, target allocations, realized profit/loss and transaction records.
- **Import:** Restore a JSON backup. Legacy JSON arrays containing holdings only are also accepted.
- **Browser storage:** Holdings, transactions, targets, settings and chart history are persisted in the browser's local storage.

---

## Supported markets and data sources

| Market | Tag | Currency | Ticker convention / source |
| :--- | :--- | :--- | :--- |
| United States | US | USD | Yahoo Finance |
| Taiwan | TW | TWD | Yahoo Finance; .TW / .TWO |
| Singapore | SG | SGD | Yahoo Finance; .SI |
| Malaysia stocks and ETFs | MYF | MYR | Yahoo Finance; .KL |
| Malaysia mutual funds | MYF | MYR | Manual price entry, or supported Principal Malaysia NAV CSV |
| China | CN | CNY | Yahoo Finance; .SS / .SZ |
| Japan | JP | JPY | Yahoo Finance; .T |
| United Kingdom | UK | GBP | Yahoo Finance; .L |
| South Korea | KR | KRW | Yahoo Finance; .KS / .KQ |
| Hong Kong | HK | HKD | Yahoo Finance; .HK |
| Cryptocurrency | CRYPTO | USDT | Binance spot API; USDT trading pairs |

For a Principal Malaysia mutual fund, the optional NAV URL must be a Principal Malaysia download CSV link in the supported /en/nav/…_format=csv format. Other mutual funds can be tracked by entering prices manually.

### Currency conversion

- Automatic exchange rates are retrieved from [open.er-api.com](https://open.er-api.com/).
- Exchange rates can be overridden manually in the footer or restored with **Auto rates**.
- USDT follows USD by default, with an option to override its rate separately.
- Portfolio values are converted for consolidated reporting. Currency-related gains and losses are not separately attributed.

---

## Getting started

1. Download or clone this repository.
2. Open [portfolio-tracker.html](portfolio-tracker.html) in a modern browser.
3. Enable JavaScript and internet access for live quotes, exchange rates and remote NAV data.
4. Search for or enter an instrument, select its market, and record the units and purchase price.
5. Use **Export** regularly to keep a backup of your portfolio data.

No build step, package manager, database or local server is needed.

---

## Refresh and data behaviour

- Stock quote refresh intervals are configurable from 5 to 60 seconds. Outside a market's trading session, stock refreshes are throttled.
- Cryptocurrency prices are retrieved from Binance while the page is active.
- Five-year highs and related historical reference prices are refreshed periodically from Yahoo Finance or Binance.
- Principal NAV data is retrieved from the CSV URL supplied for the fund.
- **Test connection** checks the FX, Binance and Yahoo Finance sources.
- Provider or relay failures can leave quotes stale or unavailable. Prices and historical figures may be delayed, incomplete or inaccurate; verify important values with your broker or fund provider.

The tracker needs internet access for live market data, FX rates and remote NAV data. Previously saved portfolio data remains in the browser unless its site data is cleared.

---

## Privacy and local data

The tracker has no user accounts, analytics tracker or advertising tracker. Portfolio holdings, units, costs, transactions, target allocations and settings are saved in browser local storage; these portfolio details are not sent to the developer.

The page does make external requests to retrieve market information. Yahoo Finance and Binance receive requested ticker symbols; open.er-api.com provides exchange rates. Yahoo Finance requests may pass through a configured price relay or public CORS proxy. These services may receive your IP address, browser information and the ticker symbols requested, under their own privacy policies. The tracker does not include your holding quantities, cost basis or portfolio balances in these market-data requests.

Clearing browser site data permanently removes locally stored tracker information. Use **Export** to keep your own backup.

---

## Important information

This application is a portfolio tracking tool only. It does not provide investment or trading advice, connect to brokerage accounts, place orders or execute trades. Market prices and calculated figures may be delayed or inaccurate. Verify important information with your broker or fund provider before making investment decisions.

## Copyright

© 2026 Alvin Koh. All rights reserved. The text, design and code of this tracker may not be copied or redistributed without permission. All third-party trademarks and product names belong to their respective owners.
