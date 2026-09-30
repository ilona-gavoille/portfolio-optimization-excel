# Portfolio Optimization & Asset Allocation Tool

Automated Excel tool for portfolio construction based on **Markowitz's Modern Portfolio Theory**: it pulls market data, computes risk/return statistics, and uses Solver to generate an efficient frontier, an Optimal portfolio and a Minimum Variance portfolio, all explored through an interactive dashboard.

**Tech:** Excel · Power Query · VBA · Solver · Financial Modeling Prep API

<img width="2828" height="1230" alt="image" src="https://github.com/user-attachments/assets/9a896c7b-12d2-4dbe-b0fe-2441a1a0761c" />


## Key Features

- **Automated market data:** daily prices for 8 US stocks via the Financial Modeling Prep API, imported with Power Query and refreshed by a VBA button.
- **Risk & return analytics:** daily returns, annualized return and volatility, correlation and covariance matrices, Sharpe ratio.
- **Constrained optimization** with Excel Solver: user-defined min/max weights per asset, fully invested, no short selling.
- **Efficient frontier:** 12 portfolios plus the Capital Allocation Line, the Optimal Sharpe portfolio and the Minimum Variance portfolio.
- **Interactive dashboard:** select any portfolio and see allocation, expected return, volatility, Sharpe ratio, maximum drawdown, cumulative performance and comparison with the S&P 500 (SPY).

## Quick Start

1. Download `Portfolio_Optimizer.xlsm` and open it in **Excel Desktop** (enable macros and the **Solver** add-in).
2. Get a free API key from [Financial Modeling Prep](https://site.financialmodelingprep.com/) and paste it into the Power Query editor.
3. On the Dashboard: **REFRESH $\rightarrow$ OPTIMIZE PORTFOLIO** (set min/max weights and risk-free rate) $\rightarrow$ **GENERATE**.

Full step-by-step guide with screenshots:
`docs/How_to_Use.pdf`

## Methodology (summary)

| Item | Approach |
| :--- | :--- |
| Returns | Simple daily returns, $R = (P_t - P_{t-1}) / P_{t-1}$ |
| Expected return | Historical average daily return $\times 252$ |
| Portfolio risk | $\sigma_p = \sqrt{(w^T \Sigma w)} \times \sqrt{252}$ (covariance matrix) |
| Efficient frontier | For 12 target returns, Solver minimizes volatility under constraints |
| Optimal portfolio | Maximizes Sharpe ratio = $(R_p - R_f) / \sigma_p$ |

Complete details, assumptions and formulas:
`docs/Project_documentation.pdf`

## Investment Universe

AAPL · MSFT · JPM · XOM · JNJ · AMZN · KO · WMT (chosen for sector diversification). The S&P 500 is used only as a benchmark.

## Limitations

- Fixed universe of 8 US equities (constraint of the API's free plan); no ETFs or bonds
- Historical returns are used as a proxy for expected returns
- All capital is invested in risky assets; risky/risk-free allocation is not optimized
- No transaction costs, taxes, liquidity or market impact

## Roadmap

- Selectable historical window (5Y, 1Y, 6M, 3M)
- User-selected assets from the Dashboard
- Multi-asset universe (ETFs, bonds, commodities)
- Risk-aversion parameter and risky/risk-free allocation
- Next projects in this toolkit: DCF valuation, Risk management (VaR) with Python, Investment Tracker Dashboard

## Repository Structure

```text
├── Portfolio_Optimizer.xlsm
├── README.md
├── docs/
│   ├── How_to_Use.pdf
│   └── Project_documentation.pdf
└── screenshots/
    ├── Dashboard.png
    ├── Portfolio_Optimization.png
    ├── Efficient_Frontier.png
    ├── VBA_Code.png
    ├── Power_Query.png
    └── Key_Formulas.png
```
## Behind the Model

The workbook is protected to preserve the integrity of the model and its automated processes.

Selected screenshots are provided to showcase the underlying VBA code, key formulas, Power Query workflows and technical features of the model.

## Disclaimer

Demo version. Not investment advice.

---

**Author:** Ilona Gavoille · **Version:** 2.2 · **Last updated:** 30/09/2026
