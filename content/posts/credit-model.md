+++
date = '2025-10-07T13:26:35-04:00'
draft = false
title = 'Credit Model'
+++
All the credit strategy should be powered by models if sufficient data samples available, as models can capture much higher dimension of data information compared with the ones processed by human brain. Using new account model as an example, higher dimension means higher degree of discrimination detected from data, and model can capture true defaulter with less sacrifice of non-defaulter. Therefore we usually use *Gini* to measure overall discrimination power and *Capture rate at top X%* to check the potential performance in strategy, the way to use the model to set a cutoff threshold to decline applicants. Once a cutoff has been set, it will be natually bring in two types of errors, type I and type II errors. Type I error (false positive) for credit model is to classify non-defaulters as defaulters and yields decline decision. Type II error (false negative) is to consider defaulters as non-defaulters. The cost of Type I error is lossing a good customer, and cost of Type II error is default risk. Therefore, credit risk management is to design a strategy to manage type II error. However you can consider an extreme case, with a perfect model which can score highest for all the defaulters and we set a threshold perfectly to seperate out all the defaulters from non-defaulters, we will have 0% for both Type I and Type II errors; with imperfect model in reality, type I and type II error trade off with each other based on the cutoff selection, which means we will either sacrifice many good customers for low default risk, or bring in more defaulters for high approval rate. Based on above, we can tell the importance of a powerful model, and importance of cutoff threshold selection on the impact of business growth and credit performance. Therefore, the contribution of a good model to bring in more good customer given the same default risk. 

Another use case which requires the model is around line assignment, the line strategy without model usually only focus on risk and repayment, however the model can introduce long view on card member value (CMV), which is the combination of component such as borrowing revenue, spending revenue and risk cost. Each applicant will be assessed at these three dimensions and the line which provides highest CMV will be offered to customers after layered with many other policies. 

The majoirty of credit models are based on supervised modeling technique as there is tag to be used for prediction, however unsupervised models on the other sidecan add value as well. Unsupervised modeling is a common technique for classification when tag is not available, it's ideal to handle situation when the relationship between dep and indep is not well defined, such as used as anomaly detector or high balance loss capture. However to assess the production feasibility to implement a new modeling technique, it requires many considerations, such as  tradeoff in type I and II errors, implementation complexity, interpretation requirement.  

Credit model's main challenges are around:
- Data Representative: As modeling data is always the ones have been observed historically. We need to check the following to ensure the model performance is consistent between production and development stages: if the modeling data similar to the data in production, in terms of population coverage and relationship trend.
- Data Treatment: How to treat blank and outlier in modeling dataset, will they provide meaningful relationship to target variables OR they are just noise.
- Data Scarcity: How to handle extreme conditions which is rarely shown in modeling data, such as extremely high balance. Sampling technique is one of ways to ensure the model reflects correctly on the biased sitution. 
- Feature Engineering: Given raw data, how to bring out the insights from data. Traditional way mainly focuses around variable creation. Given recent surge of advanced machine learning techniques, NN and LLM can help capture many patterns exist in time series, NLP to nowadays' models. 
- Model Redevelopment/Refreshment: As more production data comes in, can we identify a deterioration signal to redevelope the model or make model to have self-learning ability to adapt to the new trend.
- Model Interpretation: How to interprete advanced model, such as NN, NLP, LLM in credit decision.

Reflect modeling challenges from above, it comes the following focus areas when we conduct model validation:
1. Model Usage and assumption: understand the model use case in business, and confirm if modeling data is suitable and match model usage; 
2. Data: ensure modeling data and production data are similar in terms of coverage and behavior; 
3. Model performance: detect model overfitting by checking model performance consistency across out-of-time and out-of-sample
4. Ongoing monitoring: set up monitoring strategy to raise alarm on model deterioration and model redevelopment


Model-Driven Credit Strategy

All credit strategies should be powered by statistical or machine learning models whenever sufficient data samples are available. Models can process and capture far higher-dimensional data relationships than human judgment alone. Taking a new account model as an example, a higher-dimensional model can better differentiate between good and bad applicants — identifying true defaulters with less sacrifice of non-defaulters.

To evaluate model performance, we commonly use two metrics:

Gini: measures overall discrimination power — how well the model separates defaulters from non-defaulters.

Capture Rate at Top X%: assesses how effectively the model ranks defaulters toward the top, which supports cutoff threshold design.

Once a cutoff is set, two types of errors naturally arise:

Type I Error (False Positive) – classifying a good customer as a bad one (lost opportunity).

Type II Error (False Negative) – classifying a bad customer as a good one (default risk).

In practice, credit risk management is about balancing these two errors — minimizing defaults (Type II) while maintaining growth. In theory, a perfect model with ideal separation would yield 0% for both errors, but in reality, improving one usually worsens the other. This trade-off underscores the dual importance of model quality and cutoff calibration, as both directly impact portfolio growth and credit performance. A stronger model enables lenders to approve more good customers for the same level of default risk.

Model Use in Line Assignment

Modeling also plays a critical role in credit line assignment. Traditional line strategies often focus only on risk and repayment ability. However, model-based approaches can incorporate a long-term value perspective through Card Member Value (CMV) modeling.

CMV combines multiple dimensions — such as borrowing revenue, spending revenue, and risk cost — to estimate expected profitability. By modeling these factors jointly, the optimal credit line is assigned to maximize CMV while staying aligned with policy constraints.

Modeling Techniques and Challenges

Most credit models use supervised learning, as default outcomes (tags) are available for prediction. However, unsupervised models also add value when outcome tags are unavailable. They are especially useful for anomaly detection or identifying hidden risk clusters (e.g., unusually high balances or suspicious behavior).

That said, the feasibility of adopting new modeling techniques depends on several practical considerations — including trade-offs in error types, implementation complexity, and regulatory interpretability.

Key Modeling Challenges

Data Representativeness – Modeling data should mirror production data in both population and relationship patterns to maintain stable performance.

Data Treatment – Blanks, outliers, and anomalies must be carefully handled to avoid introducing noise or bias.

Data Scarcity – Extreme or rare scenarios (e.g., very high balances) may be underrepresented; sampling techniques can help balance this.

Feature Engineering – Extracting insights from raw data remains fundamental. With advances in ML, neural networks (NN) and large language models (LLMs) can now uncover temporal or linguistic patterns beyond traditional variables.

Model Refresh & Adaptation – Continuous monitoring helps detect performance drift; models may need redevelopment or adaptive self-learning capabilities.

Interpretability – As models become more complex (e.g., NN, NLP, LLM), explainability becomes critical for credit decisioning and compliance.

Focus Areas in Model Validation

Given these challenges, effective model validation should emphasize:

Usage & Assumptions – Confirm the model’s intended business purpose and ensure data aligns with that use case.

Data Consistency – Validate that modeling and production datasets are comparable in coverage and behavior.

Performance Stability – Detect overfitting through out-of-time and out-of-sample tests.

Ongoing Monitoring – Establish thresholds and alerts to identify performance deterioration and trigger redevelopment when needed.