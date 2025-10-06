[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/gdTY4KPC)
[![Open in Codespaces](https://classroom.github.com/assets/launch-codespace-2972f46106e565e64193e422d61a12cf1da4916b45550586e14ef0a7c637dd04.svg)](https://classroom.github.com/open-in-codespaces?assignment_repo_id=19441770)

# Algorithmic Trading Case

This is the top-level README for your GitHub repository.

You must include **clear instructions here on how to run your replication package**. Be specific: mention any required credentials, file paths, environment setup steps, or entry points for your analysis.

> If you're looking for the full case description and requirements, see **case/README.md**

## Repository Structure

```bash
CasestudyAlgoTrading/
├── case/
│   ├── README.md                   # Case description and full instructions
│   ├── 151TradingStrategies.pdf    # Inspiration for potential strategies
│   └── Example [...].pdf           # Example strategy proposals
├── data/                           # Example data files or data access scripts
├── my data                         # my backtest Data
├── res/                            # Additional resources and figures
├── trade_dashboard                 # django project(A dashboard to report my portfolio performance)
├── README.md                       # This file (top-level project overview)
├── .env                            # Local credentials 
├── alpaca_example.ipynb            # Example: how to interact with Alpaca's API
├── vectorbt_example.ipynb          # Example: using vectorbt for backtesting
├── requirements.yml                # Conda environment definition
├── proposal.pdf                    # My  final strategy proposal
├── trade_logs                      # Entries and Exit trade log
├── .github/workflows               # file to create a github action workflow
├── Data_download_Binance.ipynb     # Notebook for data download from Binance
├── strategy_alpaca_trading.ipynb   # Algo trade Strategy notebook
├── EMA_SMA_backtest.ipynb          # Backtesting notebook
├── strategy_alpaca_trading.py      # converted strategy notebook to python script
└──
```

## How to Run This Replication Package

To run the strategy notebook (strategy_alpaca_trading.ipynb) you need the following requirement and steps:

### Requirements

- Python 3.9+
- Alpaca API credentials (free signup at https://alpaca.markets)

### Setup Instructions

- Clone this repo
- Create a `.env` file in the root directory with this infomation in it:
  ```
  APCA_API_KEY_ID=your_api_key
  APCA_API_SECRET_KEY=your_secret_key
  APCA_API_BASE_URL=https://paper-api.alpaca.markets
  ```
- Create a virtual environment and install dependencies:
  ```
  python -m venv venv
  source venv/bin/activate
  pip install -r requirements.yml


  ```
  **NOTE that all other notebooks (ipynb files) do not require any api credentials to run**
  
# Brief Overview of the Project

## EMA/SMA Fusion trading strategy

A systematic crypto trading strategy using EMA + SMA fusion to outperform traditional buy-and-hold methods. Designed for mid- to long-term profitability, risk control, and capital growth across volatile markets like Bitcoin (BTC), Ethereum (ETH), and Ripple (XRP).

## Problem & Opportunity

Cryptocurrency markets are volatile and inefficient:

- Missed entries from slow reaction times
- False signals from rapid market reversals
- Inconsistent results from emotional decision-making

## Opportunity

A disciplined, data-driven approach that captures price momentum while managing risk.

## Our Solution

We combine Exponential Moving Averages (EMA) with Simple Moving Averages (SMA)to:

- Detect short-term momentum (EMA)
- Confirm long-term trend (SMA)
- Filter out false signals

## Key Trade Logic:

- Buy: Fast EMA (9) > Slow EMA (21) AND price > SMA (50) AND breakout > 0.5% above slow EMA
- Sell: Fast EMA < Slow EMA AND price < SMA (50)

## Strategy Highlights

- Momentum + trend confirmation logic
- Diversification across BTC, ETH, and XRP
- Buffer zones to avoid false breakouts

## Backtest Performance (2020–2025)

The data used for basktesting was downloaded from Binance for BTC, ETH and XRP 2020 to 2025

| Strategy       | Total Return | Sharpe Ratio | Sortino Ratio | Max Drawdown |
| -------------- | ------------ | ------------ | ------------- | ------------ |
| EMA/SMA Fusion | 5,216%       | 1.41         | 2.05          | -68.2%       |
| Buy and hold   | 1,443%       | 0.2          |               | -81%         |

## Risk Management

- Position sizing based on volatility
- Diversification by asset and strategy
- Regular audits and compliance checks

## July 2025 Paper Trade Results

| Detail          | Value           |
| --------------- | --------------- |
| Initial Capital | $100,000        |
| Peak Value      | $121,000        |
| Value @ july 27 | $115,914        |
| Net Return      | +14.5%(30 days) |

A more up to date Live performance dashboard and trades made can be found here: [https://tradedash.eu.pythonanywhere.com](https://tradedash.eu.pythonanywhere.com)
The strategy script (strategy_alpaca_trading.py) was added to git action workflow to run automaticaly every 15 minutes.

## Why You Should Invest

- Founder continual research
- +14.5% return in under 30 days (simulated)
- No management fees for early investors
- Full transparency & access to strategy development
- Designed to handle volatile market phases
