# 📈 Multi-Asset Portfolio Tracker

A high-performance, single-file web application designed to track investments across international markets with real-time price feeds, automated 5-year high tracking, interactive visualizations, and multi-currency aggregation.

![HTML5](https://img.shields.io/badge/HTML5-Single_File-orange?style=flat-square)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

## 🌟 Key Features

* **🇺🇸 US Stock Market:** Real-time quote integration and 5-year historical monthly high tracking via Yahoo Finance.
* **🇹🇼 Taiwan Stock Market:** Full coverage of TWSE (`.TW`) and TPEx (`.TWO`) equities and ETFs.
* **🪙 Cryptocurrency:** Live WebSocket/REST price synchronization and historical klines via Binance (USDT pairs).
* **🇲🇾 Malaysia Fund Market:** Custom unit trust and mutual fund tracking with manual NAV updates.
* **🎨 Interactive Visualizations:** Custom SVG donut chart featuring unique pattern fills for each asset class, hover tooltips, and percentage breakdowns.
* **💱 Multi-Currency AUM Engine:** Seamless conversion and display of Total Assets under Management (AUM) in **MYR**, **TWD**, or **USD** with auto-fetching FX rates.
* **🔍 Intelligent Search & Auto-Complete:** Instant ticker lookup utilizing built-in popular registries alongside live global search APIs.
* **🔒 Data Privacy & Portability:** 100% client-side execution utilizing `localStorage` with full JSON backup and import/export capabilities.

---

## 📊 Asset Class Breakdown

| Asset Class | Market Identifier | Price Source | Historical High (ATH) Source |
| :--- | :--- | :--- | :--- |
| **US Stocks & ETFs** | `US` | Yahoo Finance | Monthly Quotes (5-Year Range) |
| **Taiwan Stocks** | `TW` | Yahoo Finance (`.TW` / `.TWO`) | Monthly Quotes (5-Year Range) |
| **Cryptocurrency** | `CRYPTO` | Binance API (`USDT` pairs) | Monthly Klines (Binance API) |
| **MY Mutual Funds** | `MYF` | Manual NAV Input | User-managed maximum NAV |

---

## 🚀 Getting Started

Because this tracker is built as a single, self-contained HTML file (`portfolio-tracker.html`), no complex build steps, package managers, or server setups are required!

1. **Clone or Download** this repository.
2. Open **`portfolio-tracker.html`** directly in any modern web browser (Chrome, Safari, Firefox, Edge).
3. Start adding your holdings or import an existing `portfolio-backup.json` file.

---

## 🛠️ Technical Architecture

* **Frontend:** Vanilla JavaScript (ES6+), HTML5, and CSS3 using CSS Custom Properties (`:root`) for instant Light/Dark mode toggling.
* **APIs Used:** 
  * Yahoo Finance Chart API (with multi-proxy fallback layers for CORS stability).
  * Binance Public REST API.
  * Open Exchange Rates API (`open.er-api.com`) for live fiat conversion rates.
* **Storage:** Browser `localStorage` with automated state serialization.

---

## 🤝 Contributing

Contributions, bug reports, and feature requests are welcome! Feel free to open an issue or submit a pull request.

## 📄 License

This project is licensed under the [MIT License](LICENSE).
```bash
# Clone the repository
git clone (https://github.com/AlvinK98/PortfolioTracker.git)

# Navigate to the project directory
cd PortfolioTracker
