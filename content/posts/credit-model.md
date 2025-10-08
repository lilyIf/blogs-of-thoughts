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


