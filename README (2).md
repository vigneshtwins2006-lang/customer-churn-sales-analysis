# Customer Churn and Sales Trend Analysis

End-to-end analysis of a real e-commerce sales dataset to find **top customer segments**, **revenue trends** and **churn drivers**, finishing with **actionable business recommendations**.

**Author:** Vignesh Murugesan | **Task 3, InternCircle Data Science Internship**

## Dataset
UCI **Online Retail** dataset: about 540,000 transactions from a UK-based online gift retailer, 1 Dec 2010 to 9 Dec 2011, customers in 38 countries. The notebook downloads it automatically from a public GitHub copy.

## What the notebook covers
| Step | Techniques |
|------|-----------|
| Cleaning | cancellations, negative quantity/price, duplicates, missing CustomerID, outlier orders |
| Feature engineering | revenue, year-month, quarter, weekday, hour, new vs returning customer |
| Revenue trends | monthly revenue, orders, AOV and MoM growth, country pivot, weekday x hour heatmap, top products |
| Customer segments | RFM scoring (quintiles) into 6 business segments, Pareto analysis |
| Churn | leakage-free definition (history before 1 Sep 2011, outcome after), churn by recency, frequency and spend |
| Retention | monthly cohort retention heatmap |
| Recommendations | 9 actions, each backed by a number from the data |

## Headline findings
- **10.4M pounds** revenue from about 20,000 orders; average order value about **521 pounds**; UK = **84%** of revenue.
- **Strong seasonality:** September to November bring **37%** of the revenue of the 12 complete months.
- **Champions** (26% of customers) generate **68%** of revenue; the top 20% of customers generate **74%**.
- **Churn is 41%** over the last ~100 days. One-order customers churn at **60%**, customers with 9+ orders at **4%**; after 90 days of silence churn reaches **58%**.
- Only **20%** of new customers buy again the next month.
- No sales on Saturdays; **75%** of revenue arrives between 10:00 and 15:59.

![Churn drivers](figures/08_churn_drivers.png)

## Files
| Path | Description |
|------|-------------|
| `03_Customer_Churn_Sales_Trend_Analysis.ipynb` | Full analysis with outputs |
| `figures/` | 9 charts exported as PNG |
| `outputs/` | CSV exports: monthly trend, RFM segments, customer segments, cohort retention |

## Run it
Open the notebook in **Google Colab** and choose *Runtime > Run all*, or locally:
```bash
pip install -r requirements.txt
jupyter notebook
```

## Limitations
Only 12 months of data (December 2011 incomplete); churn uses a fixed 100-day inactivity rule; revenue is before costs; about 17% of revenue has no CustomerID and is excluded from customer-level analysis.

## Credit
Dataset: Daqing Chen et al., *Online Retail*, UCI Machine Learning Repository.
