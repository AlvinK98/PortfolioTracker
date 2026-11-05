# 📈 Multi-Asset Portfolio Tracker

A high-performance, feature-rich single-file web application designed to track investments across international markets with real-time price feeds, automated 5-year high tracking, interactive visual analytics, multi-currency aggregation, and trade management.

![HTML5](https://img.shields.io/badge/HTML5-Single_File-orange?style=flat-square)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

## 🌟 Key Features

* **🇺🇸 United States Market:** Real-time quote integration and 5-year historical monthly high tracking via Yahoo Finance and Google Finance.
* **🇹🇼 Taiwan Market (TWSE/TPEx):** Seamless handling of Taiwan equities and ETFs with automatic `.tw` / `.TW` suffix resolution.
* **🇸🇬 Singapore Market (SGX):** Full tracking of Singapore blue-chip stocks and REITs via `.SI` ticker integration and SGD currency support.
* **🪙 Cryptocurrency:** Live REST synchronization and historical klines via Binance (USDT trading pairs).
* **🇲🇾 Malaysia Market & Mutual Funds:** Support for Bursa Malaysia `.KL` equities/ETFs alongside manual NAV unit trust tracking.
* **🎨 Interactive SVG Doughnut Chart:** Custom vector pattern fills for each asset class, hover tooltips, and real-time percentage allocation breakdowns.
* **💱 Multi-Currency AUM Engine:** Instant toggle of Total Assets under Management (AUM) and P/L between **MYR**, **SGD**, **TWD**, and **USD** with auto-fetching FX rates.
* **📊 Portfolio Value Over Time:** Interactive historical graph tracking portfolio value and cost basis over custom time ranges (4H, 1D, 5D, 1M, 3M, YTD, 1Y, 5Y).
* **⚖️ Target Allocation & Rebalancing:** Set target percentage weights per market to instantly calculate market drift and actionable buy/sell rebalancing amounts.
* **🔄 Trade Logging & Undo Stack:** Full buy, sell, and edit workflows with automated WAC blending, realized P/L tracking, and a 20-step undo action history stack.
* **🔍 Intelligent Search & Sorting:** Auto-complete search engine combined with interactive click-to-sort table headers across all breakdowns.
* **🔒 Data Privacy & Portability:** 100% client-side execution via browser `localStorage` with timestamped JSON backup, export, and import capabilities.

---

## 📊 Asset Class Summary

| Asset Class | Market Tag | Currency | Price & History Sources |
| :--- | :--- | :--- | :--- |
| **United States** | `US` | `USD` | Google Finance / Yahoo Finance |
| **Taiwan** | `TW` | `TWD` | Google Finance / Yahoo Finance (`.tw`) |
| **Singapore** | `SG` | `SGD` | Google Finance / Yahoo Finance (`.si`) |
| **Crypto** | `CRYPTO` | `USDT` | Binance REST API (`USDT` pairs) |
| **Malaysia** | `MYF` | `MYR` | Bursa Malaysia (`.KL`) or Manual NAV |

---

## 🚀 Getting Started

Because this tracker is built as a single, self-contained HTML file, no complex build steps, package managers, or server setups are required!

1. **Download** or clone the latest HTML file (`portfolio_tracker.html` or your custom build).
2. Open the file directly in any modern web browser (Chrome, Safari, Firefox, Edge).
3. Start adding your holdings, configure your market targets, or import an existing `portfolio-backup-*.json` file.

---

## 🛠️ Technical Architecture

* **Frontend:** Vanilla JavaScript (ES6+), HTML5, and CSS3 using CSS Custom Properties (`:root`) for instant Light/Dark mode switching via clean SVG icon buttons.
* **Pricing Engines:** Dual-engine redundant price lookups combining **Google Finance** and **Yahoo Finance** with CORS proxy fallback layers and Binance public REST APIs.
* **Storage:** Browser `localStorage` with automated state serialization and change detection.

---

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome! Feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the [MIT License](LICENSE).
