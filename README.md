# SMA Crossover Backtesting – NSE (REL, India)

This repository contains a Jupyter notebook that backtests a **Simple Moving Average (SMA) crossover trading strategy** on **NSE-listed stock RELIANCE.NS** using Python.

The goal is to evaluate whether a basic technical strategy can outperform buy-and-hold when realistic transaction costs and risk metrics are taken into account.

---

## Strategy Logic

- **Instrument:** RELIANCE.NS (NSE)
- **Fast SMA:** 10-day moving average  
- **Slow SMA:** 50-day moving average  

**Rules:**

- **Go Long** when SMA(10) crosses **above** SMA(50)  
- **Go Short** when SMA(10) crosses **below** SMA(50)  
- Positions are closed and reversed on each crossover
- Commission is set to **5 bps per trade** to approximate real costs

---

## Tech Stack

- Python, Jupyter Notebook  
- `backtesting.py` – strategy engine & performance analytics  
- `yfinance` – historical OHLCV data for NSE  
- `pandas`, `numpy` – data handling  
- `matplotlib` – visualisation  

---

## 📊 Example Results (2018–2024, RELIANCE.NS)

Key metrics from the notebook backtest:

- Number of trades: ~36  
- Final Return: ≈ **-14%**  
- Max Drawdown: ≈ **-53%**  
- Sharpe Ratio: around **-0.08**

> These results show that a naïve SMA crossover on a single stock is **not** profitable in raw form, highlighting the importance of risk management, parameter tuning, and portfolio-level strategies – a key learning from this project.

---

## How to Run Locally

1. Clone the repository:

```bash
git clone https://github.com/rugvedshete/SMA-Crossover-Backtesting-NSE.git
cd SMA-Crossover-Backtesting-NSE
pip install backtesting yfinance pandas numpy matplotlib
jupyter notebook
