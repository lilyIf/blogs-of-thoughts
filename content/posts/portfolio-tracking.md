+++
draft = false
title = 'Credit Deshboard: A Core Function of Credit Teams'
showDate = false
weight = 3
+++
Defining and monitoring portfolio credit dashboard is one of the most critical responsibilities of a credit team. For credit team, the dashboard can provide the information to track credit performance against target rate, help detect early warning signals of credit deterioration and informs future credit strategies—whether to expand or tighten credit criteria, and it can measure efficiency of varied risk strategies. Beyond the credit team, the dashboard can also faciliate the discussion with other departments such as finance and product teams, for example to align delinquency projections with finance team, and evaluate risk-based pricing strategies with product team.

When designing a portfolio credit dashboard, it’s helpful to structure it into common section and specific purpose section to differentiate the focus of the charts.

**Common Section**
1. *Delinquency Rate Trend*

Delinquency or write-off (WO) is commonly defined at 90 days past due (90+DPD). The delinquency dollar rate is typically calculated as:
Delinquent balance ÷ Total Accounts Receivable (AR) as of the end of the month. This metric provides a simple and intuitive measure for the finance team to estimate the expected annualized write-off rate, which is monthly WO rate * 12. However, for a growing portfolio or newly release lending product, this metric can be misleading because AR growth naturally suppresses the apparent delinquency rate. To address this, a more accurate measure for growing products is to calculate delinquency using the AR from three months prior as the denominator. As the portfolio matures, the difference between the two measures should narrow. In practice, we often refer to these two measures as coincidental write-off vs. contractual write-off to distinguish between the “current” vs. “lag-adjusted” perspectives. To complement this chart, we also look into 30DPD, 60DPD, as well as 30DPD-60DPD and 60DPD-90DPD rates to get a wholistic view on risk trend and predict upcoming 90+DPD rate to detect early deterioration signal. 

2. *Risk Band-Level View*

Risk bands are among the most powerful tools for differentiating credit risk. They can be based on FICO scores or internal risk scores, depending on the audience and purpose. For instance, in a cross-product risk review, FICO will be more appropriate as different product may own respective risk score. At the risk-band level, we can monitor: new account and customer distribution, average line size,delinquency rate, accounts receivable by risk level. Tracking these metrics over time offers a clear view of risk trends and AR allocation. For simplicity, some reports use a risk-weighted index to represent the overall change in portfolio risk over time.

**Specific Purpose Section**

1. *New Account Delinquency Spike*

New account delinquency tracking focuses on recently approved customers. Two metrics are commonly used: 
- Event delinquency rate (number of delinquent accounts ÷ total accounts)
- Dollar delinquency rate (delinquent balance ÷ total balance)

An increase in new account delinquency can result from: a particular customer segment performing worse than expected, or a higher concentration of new accounts in riskier bands. To diagnose the issue: 
- Risk band distribution charts to identify changes in population mix
- Tracking delinquency by risk band over time to find deteriorating segments. Once the root cause is identified, the credit team can take corrective actions—such as tightening risk controls or collaborating with Product and Marketing to attract higher-quality customers.
If only dollar delinquency rises (with stable event delinquency), the likely cause is overly high initial credit lines for risky customers. Dashboards can be designed to track: 
- Average initial line by segment over time
- The ratio of “average bad initial line” to “average good initial line”
These indicators help assess whether initial line assignments are appropriately risk-adjusted.

2. *Portfolio Delinquency Spike*

When overall portfolio performance worsens—after accounting for new-account and line-assignment effects, the root cause often lies in customer management, especially line reduction strategy. To analyze this, we look from two angles:
- Risk distribution — how the portfolio’s risk composition shifts over time
- Performance per risk band — how each risk segment performs

In addition, by tracking delinquency across segments and monitoring the ratio of “average bad AR” to “average good AR”, we can evaluate how effective line management is at controlling risk. If the portfolio gradually shifts toward higher-risk segments, it may signal that the overall portfolio is under stress. The response should be to reduce exposure at majoirity population or revisit acquisition strategies. If the overall distribution is stable but only certain segments deteriorate, those segments can be isolated and addressed in both back-book (existing accounts) and front-book (new originations).

3. *Growth*

Growth strategies often stem from fulfilling unmet needs—either those expressed by customers or identified by the lender, or creating needs. For fulfilling unmet needs we usually deploy line strategy, the growth driven by customer demand of higher line tends to be more sustainable and effective, the growth driven by lender incentives (e.g., aggressive line increases) can create unused exposure and contingent risk, especially in economic downturns. To measure growth effectiveness: for line increase strategy, compare the ratio of “balance increase” to “line increase” using A/B testing. For creating needs, promotional pricing can be one of options, to measure the effectinve of promotional pricing, track the incremental balance after promotions to ensure the lift in AR offsets the cost of the promotion. Both approaches provide a quantitative way to evaluate whether growth initiatives genuinely enhance portfolio health and profitability.