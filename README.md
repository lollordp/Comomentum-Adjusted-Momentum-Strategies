# 📈 Comomentum-Adjusted Momentum Strategies

## Overview
This project implements and evaluates comomentum-based enhancements to traditional momentum trading strategies. Inspired by Lou and Polk (2021), we develop a practical framework that dynamically adjusts momentum exposure based on arbitrage crowding risk—proxied by the correlation of residual returns.

The project consists of:

- A baseline momentum factor model (Jegadeesh & Titman 1993)
- A simplified comomentum measure (residual return correlation)
- Multiple enhanced strategies:
  - Comomentum-scaled momentum
  - Threshold-adjusted strategy
  - Composite signal optimization
  - Conditional Fama-MacBeth regression model

---

## Project Setup

### Data
- Source: U.S. equity returns
- Signal: 48-week past returns with 4-week skip
- Factors: Fama-French three-factor model
- Time Frame: Weekly returns

---

## Tools & Technologies
- **Python**
- Pandas, NumPy for data handling
- Statsmodels for regressions
- Matplotlib, Seaborn for visualization
- Custom rolling-window correlation and strategy backtesting scripts

---

## Methodology

### 🧪 1. Baseline Momentum Model
- Rank stocks using 48-week cumulative return (skip latest 4 weeks)
- Weekly Fama-MacBeth regressions to estimate momentum premium
- Cumulative return tracked over time (benchmark strategy)

### 🔄 2. Comomentum Proxy
- Use residuals from weekly cross-sectional regressions
- Compute average pairwise correlation across residuals (52-week rolling window)
- High comomentum = arbitrage crowding → weaker future returns

### ⚙️ 3. Strategy Enhancements

#### ✔️ Scaled Momentum Strategy
Adjust momentum exposure each week:
Optimal (α, β) chosen to maximize Sharpe Ratio.

#### ✔️ Conditional Regression Strategy
Interaction model:
Adjust exposure dynamically based on comomentum-momentum interaction.

---

## 📊 Results Summary

| Strategy                       | Annual Return | Annual Std Dev | Sharpe Ratio |
|-------------------------------|---------------|----------------|---------------|
| Conditional Fama-MacBeth      | 25.72%        | 28.99%         | 0.8871        |
| Composite Adjusted Momentum   | 23.99%        | 25.95%         | 0.9245        |
| Threshold Adjusted            | 21.08%        | 28.22%         | 0.7469        |
| Equally Weighted Benchmark    | 21.16%        | 20.27%         | 1.0439        |

---

## 🔍 Key Insights
- **Momentum works** but is volatile and crash-prone.
- **Comomentum enhances momentum** by reducing exposure during crowding.
- **Best Composite Strategy** offers the most balanced performance (high Sharpe, moderate risk).
- **Conditional Model** maximizes return but comes with higher volatility.
- **Equally weighted portfolios** remain competitive due to diversification.

---

## 🧭 Practical Implications
- For **return-maximizers**: Conditional Fama-MacBeth strategy is best.
- For **risk-conscious quants**: Composite signal is more stable.
- For **conservative investors**: Equally weighted benchmark offers highest Sharpe.

A hybrid approach combining comomentum-adjusted signals with diversified weighting may yield optimal real-world results.

---

## 📬 Contact
**Lorenzo Rossi**  
📧 Email: lollordp@gmail.com  
🔗 LinkedIn: [Lorenzo Rossi](https://www.linkedin.com/in/lorenzo-rossi-profile)
