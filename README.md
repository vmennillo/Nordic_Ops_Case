# Nordic_Ops_Case
A PowerBI dashboard that tracks delivery performance and the cost of delays across six Nordic and Baltic Sites.

The data is synthetic and does not describe any real company.

The dashboard answers practical operations questions:
1. Where and when are deliveries late?
2. What does it cost?
3. Which suppliers and sites should be prioritised?

Metrics:
- On-Time Delivery (OTD %): Share of deliveries received on time
- Average delay days: avg number of days late across delayed deliveries
- Fill rate %: share of orders that were actually delivered
- Total delay cost: sum of the cost estimated for delayed deliveries
- Delay cost % of value: total delay cost / total order value

Data Pipeline:
1. Data generation in Python (pandas, numpy): 6000 orders for year 2025
2. Staging and Validation: CSVs stored in an AWS S3 bucket and checked through SQL
3. Modelling and Visualization: data cleaning in Power Query, star schema, defined measures in DAX

Dashboard structure:
Page 1.
Supply chain:
- KPIs: OTD%, AVG delay days, Fill rate%
- Least performing suppliers bar chart (target: 85%)
- OTD% per each site
- Filter by country and category
Page 2.
Delay cost:
- KPIs: total delay cost, delay cost as % of value
- Delay cost per site
- Scatter plot of OTD% against delay cost per supplier, and total orders
- Matrix of delay cost per site and category

(Some) Findings:
- OTD is 82,6%, below the target(85%)
- The average delay is 6 days, and almost 97% of the orders get delivered
- The total delay cost is more than 176.000 euros, which is about 0.43% of the total order value
- The Nordics perform better than the Baltics, and performance drops during the winter months
- Copenhagen has the highest impact in terms of delay cost

Tools:
PowerBI, Python, ASW S3, Athena/SQL




