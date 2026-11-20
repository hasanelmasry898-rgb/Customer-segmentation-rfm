# Customer Segmentation with RFM + K-Means

## Problem
A retailer has one year of raw transaction data but treats every customer the same. Who are the best customers, who is slipping away, and where should marketing money go?

## What I did
- Converted transaction-level data into one row per customer (300 customers)
- Built RFM features: Recency, Frequency, Monetary
- Standardized the features so no single metric dominates
- Chose k using the elbow method and silhouette score (k=4 gave clearly interpretable segments)
- Visualized the clusters with PCA (2 components capture 98.7% of variance)
- Translated each cluster into a business persona with a recommended action

## Results

| Segment | Customers | Avg. spend | Avg. purchases | Days since last purchase | Action |
|---|---|---|---|---|---|
| VIP | 40 | ~$29,700 | ~35 | ~8 | Protect: dedicated support, early access |
| Loyal / Regular | 128 | ~$4,700 | ~14 | ~20 | Upsell: bundles, recommendations |
| New / Occasional | 111 | ~$750 | ~4 | ~72 | Light re-engagement offers |
| Dormant | 21 | ~$320 | ~2 | ~263 | Low-cost win-back email |

**Key insight:** the 40 VIP customers (13% of the base) generate roughly 63% of total revenue, so losing even a few of them would hurt far more than losing the entire Dormant group.

## Tools
Python, Pandas, NumPy, scikit-learn, Matplotlib

## How to run
1. pip install -r requirements.txt
2. Put your transactions CSV in the project folder (columns: customer_id, transaction_date, amount)
3. Open the notebook and run all cells
