
## Financial Sector Risk Analysis (XLF, VIX, TNX)


TThis project explores systemic risk factors in the U.S. financial sector using XLF (Financial Select Sector ETF), the VIX Volatility Index, and the 10-Year Treasury Yield.
All analysis, data processing, and visualisation were performed using Python, including Pandas, NumPy, Matplotlib, Seaborn, and Statsmodels.

Provided below is a dashboard containing visuals of all data findings as well as the overview:





<img width="1212" height="883" alt="Screenshot 2025-12-11 at 7 04 00 PM" src="https://github.com/user-attachments/assets/e2b31d00-ef33-4b3b-a8e7-4d313d31cabd" />



---

## Executive Summary
### Overview of Findings

This dashboard provides a comprehensive view of risk conditions in the U.S. banking sector, using XLF (Financial Sector ETF) as a proxy for financial industry performance. It integrates volatility (VIX), interest rates (10Y Treasury yield), market risk premia, and historical return behavior to understand how macro-level forces influence banking sector stability.

The analysis reveals three core insights:

XLF’s rolling beta vs VIX has been consistently negative, meaning financials often move opposite volatility — a defensive dynamic useful for hedging.

Drawdowns show structurally rising tail-risk, with extreme declines clustered around macro shocks (COVID, rate hikes, banking stress).

Risk-adjusted returns (Sharpe ratio) are volatile, highlighting unstable reward-to-risk conditions for financial sector investors.


---




#### 1. Correlation Heatmap
The heatmap reveals the core relationships between XLF, VIX, and TNX.
XLF and VIX exhibit a strong inverse correlation, while XLF maintains a mild positive correlation with the 10-Year yield.
This reflects typical market behaviour: financial stocks weaken in risk-off environments and strengthen when interest rates rise.

Findings:

XLF vs VIX = –0.60
Strong inverse correlation (risk-off hurts banks).

XLF vs TNX = +0.40
Rising yields generally help bank profitability (better lending margins).

VIX vs TNX = –0.18
Weak inverse relationship.


<img width="945" height="778" alt="Screenshot 2025-12-12 at 9 33 37 AM" src="https://github.com/user-attachments/assets/0ca28a7e-f6af-4325-b7c0-227a3e7a9fd7" />



---

#### 2. Rolling 30-Day Beta of XLF vs. VIX

This chart shows the rolling 30-day beta of the XLF ETF (financial sector) relative to the VIX, the market’s “fear index.” A beta of +1 means XLF moves in perfect positive relation to the VIX (very rare). The chart shows XLF beta usually fluctuating between -0.3 and +0.2, rarely spiking above that.

XLF has a consistently negative or near-zero beta with the VIX.

This means:

When VIX spikes (fear rises) → XLF generally falls, but the relationship is weak and inconsistent.

Financials are not strongly reactive to volatility spikes compared to tech or small-cap sectors.

When beta trends upward toward zero or positive:

It suggests financials are moving more in sync with fear, usually a sign of systemic stress (e.g., 2020).


<img width="959" height="521" alt="Screenshot 2025-12-12 at 9 39 30 AM" src="https://github.com/user-attachments/assets/2f9bc51a-eebf-40b2-a4dd-ef03c2613efc" />






---

#### 3. Max Drawdown Over Time (XLF)
This time-series plot tracks the maximum drawdown of XLF, showing the worst peak-to-trough decline experienced at any moment from 2016 to 2026. The shaded red regions deepen whenever XLF falls significantly from its prior high. Drawdowns range from mild dips to deep multi-month declines, with several notable periods corresponding to major market stress events.

Interpretation

Deep drawdowns correlate with macro stress (pandemic, rate shocks, liquidity issues).

Prolonged drawdowns point to underlying sector-specific weakness.

Frequent moderate drawdowns demonstrate typical cyclicality in financial stocks.



<img width="908" height="492" alt="Screenshot 2025-12-12 at 9 42 15 AM" src="https://github.com/user-attachments/assets/135d62db-12b1-42af-9fbf-15fc7c69906e" />




---

#### 4. Rolling 30-Day Sharpe Ratio (XLF)
This chart shows how the 30-day rolling Sharpe ratio of XLF fluctuates over time. The Sharpe ratio represents risk-adjusted return, and the values swing constantly both above and below zero, sometimes reaching extreme positive or negative spikes. This oscillation highlights how unstable short-term risk-adjusted performance is within the banking sector.

Interpretation

Positive Sharpe spikes indicate brief windows of strong outperformance relative to risk.

Negative spikes show periods where XLF suffered poor returns relative to volatility.

High variability reinforces that financials react strongly to macroeconomic shifts.


<img width="914" height="467" alt="Screenshot 2025-12-12 at 9 43 29 AM" src="https://github.com/user-attachments/assets/a3971fbc-a6b9-46bd-b483-876c2d3d153e" />




## Final Assumptions & Recommendations

### Key Drivers & Predictive Insights
Based on the **Random Forest model**, which proved to be the most effective predictive tool for this project, we identified the primary drivers of customer churn:  

- **Age** is by far the most significant factor.  
- **Estimated Salary** and **Credit Score** follow as the next strongest drivers.  

This insight is crucial for targeting specific demographics in retention efforts.  

The model demonstrates strong performance with an **AUC of 0.85**, but the **confusion matrix** highlights a critical limitation:  

- **Correctly identified non-churners (True Negatives):** 1,536  
- **Correctly identified churners (True Positives):** 185  
- **False Positives:** 57  
- **False Negatives:** 222  

This means that while the model is strong at predicting customers who will stay, it struggles to capture a significant portion of those likely to churn.

---

### Recommendations
Based on these insights, the following actions are recommended:

1. **Implement Targeted Retention Campaigns**  
   Since age is the strongest churn driver, marketing and sales teams should develop campaigns tailored to the most at-risk age groups.  

2. **Improve Model Recall**  
   Focus on refining the model to better identify actual churners. Explore alternative algorithms (e.g., Gradient Boosting, XGBoost) or adjust hyperparameters to reduce false negatives.  

3. **Tiered Retention Strategy**  
   Use the churn risk score for segmentation:  
   - **Safe Group:** Light-touch retention monitoring.  
   - **Watchlist:** Automated, proactive interventions.  
   - **High Risk:** Personalised, high-priority outreach.  

---

### Assumptions and Caveats
The following assumptions were made during the analysis:

- **Data Integrity:** It was assumed that the dataset accurately represents customer behaviour.  
- **Model Relevance:** AUC was considered the most important performance metric.  
- **Thresholds:** Risk score cut-offs (Safe <0.3, Watchlist 0.3–0.7, High Risk >0.7) were assumed to be optimal for interventions.  
- **Causality vs. Correlation:** Feature importance values were treated as indicators of causal drivers, though in reality they represent correlation.  
