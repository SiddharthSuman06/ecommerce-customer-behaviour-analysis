# E-Commerce Customer Behaviour Analysis

A year of real transactions from a UK online retailer: 530,104 line items, 19,960 orders, about GBP 10.7 million in revenue. I wanted to find out what drives revenue here, which customers matter most, and what the international numbers really say.

The most useful thing I learned came from getting something wrong first. More on that below.

![Trading overview](images/1_trading_overview.png)

## What I found

**1. Per order, "guest" orders are bigger than registered ones. Per line item, it's the other way round.**
My first version compared spend per line item and found registered customers spending 69% more. When I added up each invoice and compared whole orders instead, guest orders averaged GBP 1,229 against GBP 481 (medians GBP 465 vs GBP 303; 95% bootstrap interval for the gap: about GBP 615 to 900).

![Registered vs guest](images/4_registered_vs_guest.png)

The reason is that the two groups are different kinds of buyer:

| | Registered | Guest (no CustomerID) |
|---|---|---|
| Median units per line | 6 | 1 |
| Median unit price | GBP 1.95 | GBP 3.29 |
| Median lines per order | 15 | 36 |
| Orders with website postage charge | 16 of 18,532 | 690 of 1,428 |

Registered accounts look like trade customers buying in multiples. Guest orders look like the website channel. So the useful recommendation isn't "convert guests to boost spend". It's that 16% of revenue (GBP 1.76M) can't be linked to any customer, which makes retention and lifetime value impossible to measure for that channel.

**2. A handful of foreign accounts place very large orders.**
Mean order value is about GBP 3,037 for the Netherlands and GBP 2,430 for Australia, against GBP 501 for the UK. But their medians are much lower (GBP 807 and GBP 430), so a few big invoices drive those averages. Japan is consistently high (median GBP 1,607) but only has 19 orders. EIRE is the steadiest international market: 288 orders, median about GBP 650.

![International performance](images/2_international_performance.png)

**3. Revenue ramps up from September and peaks in November.**
GBP 1.51M in November 2011, against GBP 0.5 to 0.8M in a typical month. There are no Saturday sales at all, which fits the dataset description saying many customers are wholesalers.

**4. The data needs cleaning before any product ranking means anything.**
Postage is recorded as a product. Two huge orders (80,995 paper craft kits and 74,215 storage jars) were cancelled the same day they were placed. Left in, they push both products into the top 10.

![Product performance](images/3_product_performance.png)

## What I changed in October 2026

The first version of this project had two mistakes, and I've left notes in the notebook where each one was fixed:

- I compared registered and guest spend per line item instead of per order. That's how I got "69% more", and it doesn't hold up.
- I labelled the average value of a line item as "average order value", so the country figures were off by a lot.

I also stopped calling the registered vs guest comparison an A/B test. Nobody was randomly assigned, so it's an observational comparison.

## How to run it

1. Download the dataset from [Kaggle (E-Commerce Data)](https://www.kaggle.com/datasets/carrie1/ecommerce-data). The original source is the [UCI Online Retail dataset](https://archive.ics.uci.edu/dataset/352/online+retail).
2. Rename the file to `E-commerce_data.csv` and put it in a folder called `data/` next to the notebook.
3. Install the packages and open the notebook:

```bash
pip install -r requirements.txt
jupyter notebook E_Commerce_Customer_Behaviour_Analysis.ipynb
```

If you're using Google Colab, upload the CSV to your Drive instead. The first code cell checks for Colab and reads from there.

## Tools

Python, pandas, NumPy, Matplotlib, SciPy (Welch's t-test, Mann-Whitney U, bootstrap confidence interval).

## Author

Siddharth Suman, Data Analyst, Berlin
[LinkedIn](https://www.linkedin.com/in/siddharthsuman06)
