
## Financial Sector Risk Analysis (XLF, VIX, TNX)


TThis project explores systemic risk factors in the U.S. financial sector using XLF (Financial Select Sector ETF), the VIX Volatility Index, and the 10-Year Treasury Yield.
All analysis, data processing, and visualisation were performed using Python, including Pandas, NumPy, Matplotlib, Seaborn, and Statsmodels.

Provided below is a dashboard containing visuals of all data findings as well as the overview:





<img width="1536" height="1024" alt="ChatGPT Image Dec 12, 2025, 10_06_54 AM" src="https://github.com/user-attachments/assets/1f8a464d-8273-4d72-812d-72860e42ea93" />




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



<img width="945" height="778" alt="Screenshot 2025-12-12 at 9 33 37 AM" src="https://github.com/user-attachments/assets/0ca28a7e-f6af-4325-b7c0-227a3e7a9fd7" />


Findings:

XLF vs VIX = –0.60
Strong inverse correlation (risk-off hurts banks).

XLF vs TNX = +0.40
Rising yields generally help bank profitability (better lending margins).

VIX vs TNX = –0.18
Weak inverse relationship.



---

#### 2. Rolling 30-Day Beta of XLF vs. VIX

This chart shows the rolling 30-day beta of the XLF ETF (financial sector) relative to the VIX, the market’s “fear index.” A beta of +1 means XLF moves in perfect positive relation to the VIX (very rare). The chart shows XLF beta usually fluctuating between -0.3 and +0.2, rarely spiking above that.



<img width="959" height="521" alt="Screenshot 2025-12-12 at 9 39 30 AM" src="https://github.com/user-attachments/assets/2f9bc51a-eebf-40b2-a4dd-ef03c2613efc" />



XLF has a consistently negative or near-zero beta with the VIX.

This means:

When VIX spikes (fear rises) → XLF generally falls, but the relationship is weak and inconsistent.

Financials are not strongly reactive to volatility spikes compared to tech or small-cap sectors.

When beta trends upward toward zero or positive:

It suggests financials are moving more in sync with fear, usually a sign of systemic stress (e.g., 2020).



---

#### 3. Max Drawdown Over Time (XLF)
This time-series plot tracks the maximum drawdown of XLF, showing the worst peak-to-trough decline experienced at any moment from 2016 to 2026. The shaded red regions deepen whenever XLF falls significantly from its prior high. Drawdowns range from mild dips to deep multi-month declines, with several notable periods corresponding to major market stress events.



<img width="908" height="492" alt="Screenshot 2025-12-12 at 9 42 15 AM" src="https://github.com/user-attachments/assets/135d62db-12b1-42af-9fbf-15fc7c69906e" />



Deep drawdowns correlate with macro stress (pandemic, rate shocks, liquidity issues).

Prolonged drawdowns point to underlying sector-specific weakness.

Frequent moderate drawdowns demonstrate typical cyclicality in financial stocks.



---

#### 4. Rolling 30-Day Sharpe Ratio (XLF)
This chart shows how the 30-day rolling Sharpe ratio of XLF fluctuates over time. The Sharpe ratio represents risk-adjusted return, and the values swing constantly both above and below zero, sometimes reaching extreme positive or negative spikes. This oscillation highlights how unstable short-term risk-adjusted performance is within the banking sector.



<img width="914" height="467" alt="Screenshot 2025-12-12 at 9 43 29 AM" src="https://github.com/user-attachments/assets/a3971fbc-a6b9-46bd-b483-876c2d3d153e" />



Positive Sharpe spikes indicate brief windows of strong outperformance relative to risk.

Negative spikes show periods where XLF suffered poor returns relative to volatility.

High variability reinforces that financials react strongly to macroeconomic shifts.



---


#### 5. Distribution of Daily Returns (XLF)
The histogram illustrates the distribution of daily percentage returns for XLF from 2016–2026. The shape resembles a bell curve centred around zero, with most returns clustering near the middle. However, the distribution also features wider tails, indicating a higher-than-normal frequency of large positive or negative daily moves compared with a standard normal distribution.



<img width="819" height="444" alt="Screenshot 2025-12-12 at 9 45 47 AM" src="https://github.com/user-attachments/assets/68558144-7b55-4ccb-b1b3-78d773658341" />




Most daily moves are small and stable, typical of a large diversified sector ETF.

Fat tails signal vulnerability to outsized shocks during crises.

Tail-risk patterns align with systemic risk events such as credit tightening or liquidity stress.



---


## AI Integration — Automated Commentary & Executive Summaries

I decided to includes an automated, AI-driven commentary system in this project that converts raw market metrics into executive-grade insights. The module calls an LLM (OpenAI) to generate a polished executive summary for presentations or emailing stakeholders.

**Why this matters:** The feature demonstrates production-ready automation: the model codifies domain rules, flags risk conditions, and creates a shareable narrative — a capability interviewers at banks and asset managers value highly.

**Files / functions:**
- `ai_insights.py` — contains `risk_commentary()` and `executive_insights()` functions (rule-based).
- `llm_summary()` — optional wrapper to call OpenAI for a concise human-level paragraph (requires `OPENAI_API_KEY`).


---

## Python Snippet for Analysis


from openai import OpenAI

client = OpenAI()

def generate_ai_summary(text: str) -> str:
    """
    Sends analysis text (market conditions, correlations, indicators)
    to the LLM and returns a polished executive-level summary.
    """
    response = client.chat.completions.create(
        model="gpt-4.1-mini",
        messages=[
            {"role": "system", "content": "You are a financial analyst."},
            {"role": "user", "content": f"Summarise this analysis: {text}"}
        ],
        max_tokens=200,
        temperature=0.2
    )

    return response.choices[0].message["content"]







The following is a snippet of the AI integration using OpenAI API token. The full implementation, including data processing, visualization, and AI-generated commentary, is available in the uploaded Jupyter Notebook (.ipynb) for anyone to review and reproduce.


## Final Assumptions & Recommendations

### Key Drivers & Predictive Insights

This analysis reveals several critical relationships within the banking sector. The strongest driver of risk sentiment is market volatility, captured by the VIX, which consistently shows a negative correlation with XLF performance. When volatility rises, banking equities tend to weaken. Treasury yields, particularly the 10-year, also demonstrate a meaningful relationship with XLF, showing that changes in interest rate expectations can materially impact sector performance.

The AI-generated commentary further enhances interpretability by summarizing real-time market states, correlations, and directional risk indicators. This makes the framework suitable for both daily monitoring and long-term strategic reporting.


---

### Recommendations

Strengthen volatility monitoring. given the consistent negative relationship between VIX and XLF, volatility should be a primary early-warning indicator. Significant spikes above historical norms often precede declines in banking equities and should trigger heightened risk review.

Integrate rate-sensitivity dashboards. The relationship between XLF and Treasury yields suggests that interest-rate-driven macro shocks meaningfully influence bank performance. A yield-monitoring module tied to XLF beta or return sensitivities would help anticipate sector rotations.

Use rolling metrics for regime detection. Rolling beta, Sharpe ratio, and drawdowns effectively highlight shifts in risk regimes. Declining Sharpe ratios, rising drawdowns, or compression in return distributions can signal deteriorating conditions before the broader market reacts.

Finally, automate daily executive summaries. The OpenAI-powered analysis demonstrates the value of automated narrative generation. Integrating this into a dashboard or reporting pipeline could help teams receive professional summaries without manual interpretation.
