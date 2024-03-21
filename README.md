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

We examined a large dataset of over 78,000 observations representing annual financial health data of more than 8,000 distinct companies to produce a model which predicts whether a company will succeed or declare bankruptcy.  This tool can be used by our client hedge fund to assess whether they wish to invest in new companies for their stock portfolio.

Our key findings are that
 

Our key findings are summarized above in our data dictionary where these features created well performing predictor of sale price.  The architect should in particular place consideration on maximizing masonry veneer area - a suprisingly strong predictor of home value.  We imagine that this is due to masonry being a luxury decor choice.  We recommend the incorporation of masonry veneer areas to emulate the luxury lifestyle dwelling.  Meaningfully we found models that heavily weight ground floor living area to predict higher sales prices.  But more than any other feature, our  most interpretable weight should be given to size of garages as they can accomodate more cars - another hobby common to affluent individuals, and the number of full baths


## Citations
(1) https://www.kaggle.com/datasets/utkarshx27/american-companies-bankruptcy-prediction-dataset/data, mined from NYSE and NASDAQ accounting data by U. Singh