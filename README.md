# Bankruptcy Prediction for U.S. Companies (1999-2018)
This project aims to develop an effective classification model to predict corporate bankruptcy using financial indicators. Data for this analysis includes financial statement line items and macroeconomic data. The key questions for this analysis related to the following:  

Which financial indicators are the most significant predictors of coroporate bankruptcy?    
How do macroeconomic conditions affect the bankruptcy risk of companies with different financial profiles?    
Can machine learning algorithms significantly improve prediction accuracy compared to traditional statistical methods when applied to financial ratio analysis?  

Exploratory data analysis revealed a strong imbalance in the bankruptcy status label, where 93% of data points were associated with the negative class (alive companies). Predictor variables also showed positive skewness, an inflated number of near-zero values, and extreme variability. The team attempted to correct for this by calculating relative metrics, financial ratios, and normalizing the features, but ultimately, this imbalance still proved challenging for the best performing models.    

A clustering analysis using **KMeans** and **Bisecting KMeans** was intially performed to identify common characteristics among bankrupt firms. The **KMeans** models were superior for both the absolute and ratio data, utilizing 2 clusters and 4 clusters, respectively. Companies were largely grouped by their size, highlighted by those with extraordinarily high debt, low liquidity, and low retained earnings.  

A **Logistic Regression (LR)**, **Random Forest (RF)**, and **Gradient Boosted Tree (GBT)** were built for the absolute and ratio data sets, using the relative features to predict the occurence of bankruptcy. The **GBT** was the best for absolute data, while the **RF** was best for ratio data, with the <u>RF topping out as the best overall model by AUC</u>. However, its predictive power for positive classes was poor, failing to make any predictions in this category. Thus, we recommend the tuned GBT tree as the best overall model given the precision-recall tradeoff, achieving an accuracy of 94%, recall of 17%, and precision of 11%.  

Feature importance diagrams were also constructed, which largely aligned with the results of the clustering analysis. These charts indicated `asset turnover`, `market value ratios`, `long-term debt levels`, and `retained earnings` were the most impactful for the best performing models. This highlights the need for a healthy balance between all three financial statements for companies to succeed over the long-term, paticularly during years of economic uncertainty (2008-2009), where the proportion of bankrupt firms peak.
