# Bank-Sector-Risk-Market-Full-Analysis-
Financial Sector Risk Analysis (XLF, VIX, 10Y Yield)

Main Dashboard Screenshot
(replace this placeholder with your actual dashboard image)

![Dashboard Overview](images/dashboard_overview.png)

Project Overview

This project analyses systemic risk in the U.S. financial sector by examining relationships between XLF, VIX, and the 10-Year Treasury Yield.
The dashboard visualizes rolling risk metrics, distribution of returns, cross-asset correlations, and long-term drawdowns to uncover how the financial sector behaves under different market regimes.

Project Analysis

Below you will insert each screenshot (you will drag them into GitHub), and beneath each one you will put the interpretation exactly as written.

Correlation Heatmap
![Correlation Heatmap](images/heatmap.png)


Interpretation:
The heatmap shows the correlations between XLF, VIX, and the 10Y yield.
XLF and VIX show a strong negative correlation, meaning financial stocks fall when volatility rises.
XLF and the 10Y yield show a mild-positive correlation, meaning financials tend to perform better when interest rates rise.
VIX and 10Y yields show a negative correlation, consistent with risk-off market behavior.

Rolling 30-Day Beta (XLF vs VIX)
![Rolling Beta](images/rolling_beta.png)


Interpretation:
The rolling beta is consistently below zero, showing that XLF moves inversely to volatility.
During macro stress events, beta becomes more negative, meaning XLF becomes even more sensitive to volatility spikes.
This metric highlights the financial sector’s tendency to underperform during periods of uncertainty.

XLF Maximum Drawdown Over Time
![Max Drawdown](images/max_drawdown.png)


Interpretation:
The maximum drawdown plot highlights periods of severe stress within the financial sector.
Major drawdowns align with tightening cycles, recessionary fears, and high-volatility regimes.
Drawdown depth and recovery time provide insight into long-term sector resilience.

Rolling 30-Day Sharpe Ratio
![Sharpe Ratio](images/sharpe_ratio.png)


Interpretation:
The Sharpe ratio fluctuates significantly, showing unstable risk-adjusted performance.
Positive spikes occur during low-volatility, stable-rate environments.
Negative values dominate in volatile or tightening environments, indicating unfavourable risk-return conditions.

Distribution of XLF Daily Returns
![Return Distribution](images/return_distribution.png)


Interpretation:
The distribution shows heavy tails, meaning large moves occur more often than a normal distribution would predict.
The slight negative skew shows that downside risk is more pronounced than upside.
This confirms the asymmetric risk profile of the financial sector.

Conclusion

The financial sector exhibits clear sensitivity to volatility and monetary policy.
XLF performs poorly in high-volatility regimes and improves in rising-rate environments.
Drawdown analysis, Sharpe ratios, and return distributions collectively reveal a sector with meaningful exposure to macro stress cycles.
This dashboard provides a structured, quantitative view of these dynamics.
