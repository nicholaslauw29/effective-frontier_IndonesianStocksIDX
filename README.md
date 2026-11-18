# 📈 Efficient Frontier — Indonesian Stock Portfolio Optimisation

A Python tool to visualise the **Markowitz Efficient Frontier** for Indonesian stock market (IDX/BEI) using real-time data from Yahoo Finance. It identifies the **Maximum Sharpe Ratio** portfolio and the **Minimum Volatility** portfolio, overlaid with a Monte Carlo simulation and individual stock positions.

---

## 📊 Features

- **Real-time data download** via `yfinance` for IDX (`.JK`) tickers
- **Efficient Frontier curve** using SciPy convex optimisation (SLSQP)
- **Maximum Sharpe Ratio** portfolio — best risk-adjusted return
- **Minimum Volatility** portfolio — lowest risk combination
- **Monte Carlo simulation** (5,000 random portfolios, coloured by Sharpe Ratio)
- **Individual stock scatter** — see where each emiten sits on the risk/return map
- **Interactive Plotly chart** with allocation annotations

---

## 📌 Stocks Analysed (Default)

| Ticker | Company |
|--------|---------|
| ANTM.JK | Aneka Tambang (Antam) |
| ADRO.JK | Adaro Energy |
| PTBA.JK | Bukit Asam |
| BBCA.JK | Bank Central Asia |
| BBRI.JK | Bank Rakyat Indonesia |
| ASII.JK | Astra International |

> You can easily modify the `stocklist` variable to analyse any IDX or global ticker.

---

## 🚀 Getting Started

### Prerequisites

Python 3.9 or higher is recommended.

### Installation

1. **Clone this repository:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   cd YOUR_REPO_NAME
   ```

2. **Install dependencies:**
   ```bash
   pip install numpy pandas scipy yfinance plotly
   ```
   Or if `pip` has launcher issues, use:
   ```bash
   python -m pip install numpy pandas scipy yfinance plotly
   ```

### Run

```bash
python portfolio_project_fixed.py
```

The script will:
1. Download 5 years of historical price data from Yahoo Finance
2. Compute log returns, covariance matrix, and portfolio metrics
3. Run optimisation for Max SR and Min Volatility portfolios
4. Generate an interactive Plotly chart in your browser

---

## 📐 Methodology

| Metric | Formula |
|--------|---------|
| Annualised Return | $\mu_{annual} = \bar{r}_{daily} \times 252$ |
| Annualised Volatility | $\sigma_{annual} = \sigma_{daily} \times \sqrt{252}$ |
| Sharpe Ratio | $SR = \frac{\mu - r_f}{\sigma}$ |
| Risk-Free Rate | Indonesia 10Y Government Bond (SBN): **6.53%** |

Optimisation uses `scipy.optimize.minimize` with the **SLSQP** method and long-only constraints (weights ∈ [0, 1], sum = 1).

---

## 📂 Project Structure

```
├── portfolio_project_fixed.py   # Main script (fully fixed & documented)
├── README.md                    # This file
└── LICENSE                      # MIT License
```

---

## ⚠️ Disclaimer

This project is for **educational and portfolio purposes only**. It is not financial advice. Past performance of any stock or portfolio does not guarantee future results. Always consult a licensed financial advisor before making investment decisions.

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgements

- Inspired by: [Python for Finance — YouTube Tutorial](https://www.youtube.com/watch?v=Isutk-wqJfE&t=728s)
- Data source: [Yahoo Finance](https://finance.yahoo.com/) via [`yfinance`](https://github.com/ranaroussi/yfinance)
- Visualisation: [Plotly](https://plotly.com/python/)
