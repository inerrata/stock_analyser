# 📈 Portfolio Analyser

A Streamlit dashboard for analysing multi-asset portfolios — risk metrics, benchmarking, and interactive charts. No installation required.

---

![Python 3.10+](https://img.shields.io/badge/Python_3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![yfinance](https://img.shields.io/badge/yfinance-0.2.36+-8a6112?style=for-the-badge)

[Highlights](#highlights) • [Live Demo](#live-demo) • [Quickstart](#quickstart) • [Features](#features) • [Metrics](#metrics-reference) • [Structure](#project-structure)

---

## Highlights

- **100+ tickers** — stocks, broad market ETFs, sector ETFs, bonds, commodities, leveraged/inverse
- **6 risk metrics** — return, volatility, Sharpe, max drawdown, VaR, beta
- **5 interactive charts** — cumulative returns, drawdown, correlation heatmap, risk vs return, return distribution
- **Cookie persistence** — your last portfolio is saved automatically across sessions
- **No login, no setup** — use it directly in the browser

---

## Live Demo

🔗 **[stockportfolioanalyser.streamlit.app](https://stockportfolioanalyser.streamlit.app/)** — no installation needed. Your portfolio is saved in cookies so it persists between visits.

---

## Quickstart

```bash
# 1. Clone the repo
git clone https://github.com/your-username/portfolio-analyser.git
cd portfolio-analyser

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run
streamlit run app.py
```

Then open [http://localhost:8501](http://localhost:8501).

---

## Features

### Portfolio Builder
Search and select from 100+ tickers. Set custom weights per holding — automatically normalised to 100%.

### Metrics Cards
Six key metrics displayed at a glance on every analysis run.

### Charts (5 tabs)

| Tab | Chart |
|---|---|
| 📊 Cumulative Returns | Portfolio vs SPY benchmark + individual stocks (toggle via legend) |
| 📉 Drawdown | Peak-to-trough decline over time, filled area chart |
| 🔥 Correlation | Lower-triangle heatmap of pairwise return correlations |
| ⚖️ Risk vs Return | Annualised scatter — stocks, portfolio ★, and benchmark |
| 📐 Distribution | Daily return histogram with normal fit and VaR 95% line |

### Holdings Table
Per-stock annualised return, volatility, Sharpe ratio, and max drawdown alongside normalised weights.

---

## Metrics Reference

| Metric | Description |
|---|---|
| Annualised Return | Geometric mean return scaled to 1 year |
| Annualised Volatility | Daily std dev × √252 |
| Sharpe Ratio | Excess return over risk-free rate per unit of volatility |
| Max Drawdown | Largest peak-to-trough decline |
| VaR (95%, 1-day) | Estimated daily loss not exceeded 95% of the time (parametric) |
| Beta (vs SPY) | Portfolio sensitivity to S&P 500 moves |

---

## Project Structure

```
portfolio-analyser/
├── app.py           # Streamlit UI, charts, sidebar inputs
├── analysis.py      # Pure computation backend — no UI dependencies
└── requirements.txt
```

`analysis.py` can be imported and used standalone without Streamlit.

---

## Requirements

| Package | Version |
|---|---|
| streamlit | ≥ 1.32.0 |
| yfinance | ≥ 0.2.36 |
| pandas | ≥ 2.0.0 |
| numpy | ≥ 1.24.0 |
| plotly | ≥ 5.18.0 |
| scipy | ≥ 1.11.0 |
| extra-streamlit-components | ≥ 0.1.60 |

Python 3.10+ recommended.

---

## Notes

- Price data is fetched live from Yahoo Finance — an internet connection is required
- SPY is always fetched alongside your holdings and used as the benchmark
- Leveraged/inverse ETFs (e.g. TQQQ, SQQQ) are supported but carry higher risk

---

## License

MIT
