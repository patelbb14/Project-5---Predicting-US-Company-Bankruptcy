# Predicting bankruptcy
#### Project 5
#### Binita, Juan, Faye

## Objective
We represent a financial consulting firm tasked with developing a model to predict the success or failure of businesses for our client, a hedge fund looking to add new investments to their portfolio.  We examined a dataset of 8,2626 distinct companies operating in the period of 1999 - 2018 where some fraction declared bankruptcy(1).  We examined 18 features of these companies including such attributes as assets, revenue, and long and short term debts.  We anticipate that our classification model can better advise on which companies for our client to acquire, thus mitigating investment risk.


## Data Dictionary
|Feature|Type|Dataset|Description|
|---|---|---|---|
|'company_name'|str|US Company Bankruptcy Dataset|Company Name (anonymized)|
|'status_label'|int|US Company Bankruptcy Dataset|Status alive (1) or bankrupt (0) aka the target
|'year'|int|US Company Bankruptcy Dataset|Year of operation
|'X1'|*float*|US Company Bankruptcy Dataset|Current assets - All the assets of a company that are expected to be sold or used as a result of standard business operations over the next year (millions of USD)
|'X2'|*float*|US Company Bankruptcy Dataset|Cost of goods sold - The total amount a company paid as a cost directly related to the sale of products (millions of USD)
|'X3'|*float*|US Company Bankruptcy Dataset|Depreciation and amortization - Depreciation refers to the loss of value of a tangible fixed asset over time (such as property, machinery, buildings, and plant). Amortization refers to the loss of value of intangible assets over time (millions of USD)
|'X4'|*float*|EBITDA - Earnings before interest, taxes, depreciation, and amortization. It is a measure of a company's overall financial performance, serving as an alternative to net income (millions of USD)
|'X5'|*float*|US Company Bankruptcy Dataset|Inventory - The accounting of items and raw materials that a company either uses in production or sells (millions of USD)
|'X6'|*float*|US Company Bankruptcy Dataset|Net Income - The overall profitability of a company after all expenses and costs have been deducted from total revenue (millions of USD)
|'X7'|*float*|US Company Bankruptcy Dataset|Total Receivables - The balance of money due to a firm for goods or services delivered or used but not yet paid for by customers (millions of USD)
|'X8'|*float*|US Company Bankruptcy Dataset|Market value - The price of an asset in a marketplace. In this dataset, it refers to the market capitalization since companies are publicly traded in the stock market (millions of USD)
|'X9'|*float*|US Company Bankruptcy Dataset|Net sales - The sum of a company's gross sales minus its returns, allowances, and discounts (millions of USD)
|'X10'|*float*|US Company Bankruptcy Dataset|Total assets - All the assets, or items of value, a business owns (millions of USD)
|'X11'|*float*|US Company Bankruptcy Dataset|Total Long-term debt - A company's loans and other liabilities that will not become due within one year of the balance sheet date (millions of USD)
|'X12'|*float*|US Company Bankruptcy Dataset|EBIT - Earnings before interest and taxes (millions of USD)
|'X13'|*float*|US Company Bankruptcy Dataset|Gross Profit - The profit a business makes after subtracting all the costs that are related to manufacturing and selling its products or services  (millions of USD)
|'X14'|*float*|US Company Bankruptcy Dataset|Total Current Liabilities - The sum of accounts payable, accrued liabilities, and taxes such as Bonds payable at the end of the year, salaries, and commissions remaining (millions of USD)
|'X15'|*float*|US Company Bankruptcy Dataset|Retained Earnings - The amount of profit a company has left over after paying all its direct costs, indirect costs, income taxes, and its dividends to shareholders  (millions of USD)
|'X16'|*float*|US Company Bankruptcy Dataset|Total Revenue - The amount of income that a business has made from all sales before subtracting expenses. It may include interest and dividends from investments (millions of USD)
|'X17'|*float*|US Company Bankruptcy Dataset|Total Liabilities - The combined debts and obligations that the company owes to outside parties (millions of USD)
|'X18'|*float*|US Company Bankruptcy Dataset|Total Operating Expenses - The expenses a business incurs through its normal business operations (millions of USD)


## Executive Summary
To build our bankruptcy prediction tool, we examined a dataset which tracked the financial health of US companies in the period of 1999-2018, during which 8,362 companies stayed in business but 609 companies went bankrupt.

We found that it was challenging to build a model which could predict likely bankruptcy.  The baseline prediction accuracy was 0.932, which represents the fraction of businesses which stayed in businesss out of all businesses surveyed.  A number of models were produced which attempted to improve upon this baseline score.  We also remark that for our dataset, we handled the significant imbalance between the alive and bankrupt classes by oversampling, a form of bootstrapping.  We sampled with replacement from the minority class so that it matches the size of the majority class to produce a properly balanced augmented datset. 

In part 1 of our study, we examined several tree models, a RandomForest and an XGBoost model.  A Random Forest model is an ensemble learning method that combines multiple decision trees to improve prediction accuracy and reduce overfitting. This model had a testing accuracy of 0.940.  The most important predictive features were identified as the market capitalization (X8), retained earnings (X15), and net income (X6).  In our use case, it is crucial for us to minimize false negatives, meaning that the model incorrectly predicts a business stays alive, when it will actually fail.  This would have severe financial implications for our client.  Therefore, the most important metric for our use case would be sensitivity.  We can tolerate false positives (predicting that a company will go bankrupt when it actually stays alive).  Although our testing accuracy was not significantly higher than the baseline model, we find that there is reasonable sensitivity at about 64%. 

We sought to improve upon this model by using an XGBoost model which is a scalable and efficient implementation of gradient boosted decision trees designed for speed and performance in machine learning tasks. This model performed with an accuracy of 0.939 and a sensitivty of 57%, which again, did not provide significant improvements over baseline.

We also explored whether a Support Vector Machine (SVM) could improve our predictions because of its efficacy with high-dimensional data and robustness to outliers. SVM finds the optimal hyperplane that maximizes the margin between the alive and bankrupt classes. Several versions of SVMs were tested, including different Kernel types and regularization parameters, but the results fared worse than our existing tree models with only an 8% sensitivity.

In part 2, we examined neural network (NN) models to see if our predictive power could be improved.  NNs consist of layers of interconnected nodes (neurons), where each node receives input, performs a simple operation, and passes the output to the next layer. Several models were tested, for instance, models with more layers, more dropout, batch noramlization, and early dropout. The best accuracy however was 0.834 and the sensitivity was 19%, faring worse than the tree models previously described. We also examined an Recurrent Neural Network (RNN), which is known to effectively model sequential data by maintaining a memory of previous inputs through hidden states. This memory capability allows us to handle time series data, where the order of observations is critical for making predictions.  However, we were unable to achieve more than 0.90 accuracy, which is not significantly different from baseline.

We conclude that classification of companies as likely to stay in business or to go bankrupt is difficult.  The best prediction accuracy we achieved was only a few percentage points above this baseline, indicating that our models were not substantially more effective in identifying bankruptcies. ßThis outcome suggests that our current modeling strategies may not be capturing the underlying complexities of bankruptcy prediction, including factors beyond individual company financial metrics. Importantly, we note that bankruptcy can also be influenced by external factors such as market conditions, regulatory changes, and industry trends.  Future endeavors could include feature engineering to uncover more predictive signals, exploring more advanced machine learning techniques, and incorporating domain-specific knowledge to better understand the financial health of companies, as well as the broader economic context in which they operate.


## Citations
(1) https://www.kaggle.com/datasets/utkarshx27/american-companies-bankruptcy-prediction-dataset/data, mined from NYSE and NASDAQ accounting data by U. Singh