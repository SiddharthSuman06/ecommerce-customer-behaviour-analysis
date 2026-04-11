# E-Commerce Customer Behaviour Analysis

A year of real transactions from a UK online retailer. 530,104 clean records, GBP 10.6 million in revenue, 38 countries. This project examines what genuinely drives revenue, which customer segments are most valuable, and what the data reveals about international market opportunity.

## What This Project Covers

Using the UCI Online Retail Dataset, this analysis moves through data cleaning, exploratory analysis, product performance evaluation and a statistically tested comparison of registered versus guest customer spend behaviour.

## Key Findings

**Registered customers spend 69% more than guests per transaction**
An independent samples t-test confirmed this difference at p less than 0.0001. The median gap is even more striking at GBP 11.80 versus GBP 4.96, meaning the spending advantage runs consistently through the full customer distribution rather than being driven by outliers. Every guest converted to a registered account represents a projected 69% uplift in transaction value.

**Revenue is heavily concentrated in Q4**
November drives the sharpest revenue peak, consistent with Christmas gifting behaviour. Thursday is the strongest trading day and Sunday registers almost no activity, suggesting the business serves other businesses rather than weekend retail consumers.

**International markets deliver disproportionate value**
The Netherlands generates GBP 285k from just 94 orders, an average order value of GBP 121 against the UK average of GBP 18. Australia and Japan show comparable patterns. These are almost certainly wholesale buyers who warrant a fundamentally different commercial approach to standard retail marketing.

**Data quality is an analytical discipline**
Postage charges recorded as product line items, single bulk wholesale transactions and administrative entries all distort product performance metrics if left unaddressed. Identifying and handling these artefacts before drawing conclusions is as important as the analysis itself.

## Tools and Methods

Python, Pandas, NumPy, Matplotlib, Seaborn, Scipy. Independent samples t-test for A/B analysis. Dataset: UCI Online Retail via Kaggle, covering December 2010 to December 2011.

## Business Recommendations

A post-purchase account creation prompt with a tangible incentive would be among the highest return conversion investments available to any e-commerce platform. The statistical case is beyond dispute. Separately, international markets with average order values exceeding GBP 100 warrant dedicated wholesale acquisition strategies rather than standard retail campaigns.

## Author

Siddharth Suman

Data Analyst, Berlin

linkedin.com/in/siddharthsuman06
