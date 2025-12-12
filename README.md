
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

The dashboard allows portfolio managers, market analysts, and risk strategists to assess sector fragility, stress-test positioning, and evaluate macro-sensitivity over time.






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

#### 2. Rolling Risk Metrics

This chart shows the rolling 30-day beta of the XLF ETF (financial sector) relative to the VIX, the market’s “fear index.” A beta of +1 means XLF moves in perfect positive relation to the VIX (very rare). The chart shows XLF beta usually fluctuating between -0.3 and +0.2, rarely spiking above that.

XLF has a consistently negative or near-zero beta with the VIX.

This means:

When VIX spikes (fear rises) → XLF generally falls, but the relationship is weak and inconsistent.

Financials are not strongly reactive to volatility spikes compared to tech or small-cap sectors.

When beta trends upward toward zero or positive:

It suggests financials are moving more in sync with fear, usually a sign of systemic stress (e.g., 2020).



<img width="528" height="468" alt="Screenshot 2025-09-09 at 9 45 48 AM" src="https://github.com/user-attachments/assets/75c861e6-b946-400a-8730-36edd8ae3de3" />


---

#### 3. Customer Churn Risk Score Distribution
The churn risk score distribution segments customers based on their likelihood to churn. The data shows:

- Majority of customers fall into the **"Safe"** category (low churn risk)  
- Smaller number are on the **"Watchlist"** (moderate risk)  
- A critical, small group is **"High Risk"** (highest probability of churning)  

This segmentation allows the business to efficiently allocate resources, focusing proactive retention efforts on the customers most likely to leave.  



<img width="696" height="472" alt="Screenshot 2025-09-09 at 9 46 06 AM" src="https://github.com/user-attachments/assets/f68d7961-142a-4d56-b75d-101a9c29d69c" />




---

#### 4. Top 10 Features Driving Churn
This bar chart visualizes the factors with the greatest influence on the model's ability to predict churn.  

- **Horizontal bars** show each feature's "importance" score, ranking how much it contributes to the model's predictions.  
- **Key insights:** Age is by far the most important factor, followed by Estimated Salary and Credit Score.  

This insight is critical for creating targeted business strategies, as it shows which aspects of customer data most influence churn outcomes.  


<img width="805" height="470" alt="Screenshot 2025-09-09 at 9 46 16 AM" src="https://github.com/user-attachments/assets/df15091c-61f6-4d53-bf34-bafd52f23b12" />





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
