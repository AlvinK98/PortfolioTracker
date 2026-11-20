# 📈 Multi-Asset Portfolio Tracker

A feature-rich, single-file web app for tracking investments across ten markets and crypto, with live prices, automatic 5-year highs, multi-currency totals, trade logging and a portfolio value history. No build step, no server, no account.

[![HTML5](https://img.shields.io/badge/HTML5-Single_File-orange?style=flat-square)](#)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

---

## 🌟 Key Features

- **🌏 10 markets + crypto:** United States, Taiwan, Singapore, Malaysia, China, Japan, United Kingdom, South Korea, Hong Kong, and crypto via Binance (USDT pairs).
- **🔍 Ticker search:** Type a ticker or company name and pick from a "Ticker - Company" list (built-in popular tickers plus live Yahoo Finance and Binance search). You only enter units and your cost; price, ATH and P/L are filled in automatically.
- **⚡ Live prices:** Stock quotes refresh every 5 to 60 seconds (your choice), crypto via Binance. Prices turn yellow while that market is open.
- **🏔️ 5-year ATH:** The 5-year high and its date are built from daily highs and rechecked every 6 hours. Hover an ATH value to see its date.
- **📊 Performance columns:** Day %, vs ATH, MoM, QoQ, YoY and YTD, each switchable from the Holdings "Performance" filter.
- **💱 Multi-currency totals:** View Total AUM and P/L in CNY, GBP, HKD, JPY, KRW, MYR, SGD, TWD or USD. FX rates auto-update (open.er-api.com) and can be overridden per currency.
- **🎨 Interactive doughnut chart:** Allocation by market with pattern fills, hover tooltips and a legend.
- **📈 Portfolio value over time:** Cost (yellow), profit (green) and loss (red) on one chart, with ranges 4H, 1D, 5D, 1M, 3M, 6M, YTD, 1Y and 5Y and a hover readout.
- **⚖️ Target allocation:** Set a target % per market and see drift (highlighted at 5 points or more) and the amount to buy or sell to rebalance.
- **🔄 Trades in one form:** Buy (auto-blended WAC), sell (realized P/L), stock split / reverse split, and edit holding.
- **🧾 Transaction history:** Paged list (10 per page) of every buy, sell and split, with show/hide.
- **↩️ Undo:** 20-step undo for holding and trade changes.
- **🇲🇾 Malaysia mutual funds:** Enter the price manually, or paste a Principal fund NAV CSV link to pull NAV, ATH and performance automatically. For manual funds, the highest NAV you enter is used as the ATH.
- **🗂️ Holdings table:** Sortable columns, frozen ticker column, group by market or currency, multi-select market filter, and market hours (in Malaysia time) beside each market name.
- **🌗 Light / dark mode** and a sticky header, with a back-to-top button.
- **🔒 Private by design:** Everything is stored in your browser's `localStorage`. Nothing is sent to a server. Back up and restore with timestamped JSON export and import (holdings, FX, history, targets, realized P/L and transactions).

---

## 🌍 Markets and Data Sources

| Market | Tag | Currency | Ticker format | Price source |
| --- | --- | --- | --- | --- |
| United States | `US` | USD | `AAPL` | Yahoo Finance |
| Taiwan | `TW` | TWD | `2330.TW`, `.TWO` | Yahoo Finance |
| Singapore | `SG` | SGD | `D05.SI` | Yahoo Finance |
| Malaysia | `MYF` | MYR | `1155.KL`, or a fund name | Yahoo Finance, Principal NAV CSV, or manual |
| China | `CN` | CNY | `600519.SS`, `300750.SZ` | Yahoo Finance |
| Japan | `JP` | JPY | `7203.T` | Yahoo Finance |
| United Kingdom | `UK` | GBP | `SHEL.L` | Yahoo Finance (pence converted to pounds) |
| South Korea | `KR` | KRW | `005930.KS`, `.KQ` | Yahoo Finance |
| Hong Kong | `HK` | HKD | `0700.HK` | Yahoo Finance |
| Crypto | `CRYPTO` | USDT | `BTC` | Binance (USDT pairs) |

Notes:
- Cost is converted at the current FX rate, so currency gains and losses are not tracked separately.
- Data comes from free public sources and may be delayed or inaccurate. Verify with your broker before making decisions.

---

## 🚀 Getting Started

1. **Download** `portfolio-tracker.html`, or open the hosted version if you use GitHub Pages.
2. Open the file in any modern browser (Chrome, Safari, Firefox, Edge).
3. Add your holdings, set your market targets, or import an existing `portfolio-backup-*.json` file.

### Price proxy (important if you fork this)

Browsers block direct requests to Yahoo Finance, so stock quotes go through a small relay. The tracker tries a Cloudflare Worker first, then falls back to public CORS proxies, which are less reliable. If you fork the project, deploy your own Cloudflare Worker that forwards a `url` query parameter and replace the `PX` constant near the top of the price section in the script with your Worker's address. Use **Test connection** in the footer to check each source.

---

## 🛠️ Technical Architecture

- **Frontend:** Vanilla JavaScript (ES6+), HTML5 and CSS3, with CSS custom properties for light/dark theming. Charts are hand-built SVG, so there are no libraries.
- **Pricing:** Yahoo Finance (through the relay chain above) for stocks and ETFs, the Binance public API for crypto, open.er-api.com for FX, and optional Principal NAV CSV files for Malaysian funds.
- **Storage:** Browser `localStorage`, with history kept in tiered intervals (1 minute up to 2 hours, then daily).

---

## 🔐 Privacy

No accounts, no analytics, no advertising trackers. Your units, costs and balances never leave your device. To show prices, the page requests ticker symbols and exchange rates from the services above, which may see your IP address under their own policies. Clearing your browser's site data removes everything, so use **Export** to keep a copy.

This tracker is for tracking only. It does not give trading or investment advice and has no access to any brokerage account.

---

## 🤝 Contributing

Contributions, bug reports and feature requests are welcome. Feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the [MIT License](LICENSE).
