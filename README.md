# Sales-Dashboard-Indian-Dataset
Power BI dashboard assessing company sales in Indian cities 

Problem Statement:
How to track overall sales revenue in real-time for each market (city)?

Step 1) 
Run basic queries in SQL to understand the dataset

Step 2)
Clean data & perform ETL in Power BI

Step 3) 
Build Dashboard

> Page 1 called "Profit Analysis" is created using multiple measures:

- Profit margin % = Divide([Total Profit Margin], [Revenue],0)

- Profit Margin Contribution % = Divide([Total Profit Margin],CALCULATE([Total Profit Margin],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
- Revenue = Sum('sales transactions'[norm_sales_amount])
- Revenue LY = CALCULATE([Revenue], SAMEPERIODLASTYEAR('sales date'[date]))
- Revenue Margin Contribution % = Divide([Revenue],CALCULATE([Revenue],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
- Sales Qty = Sum('sales transactions'[sales_qty])
- Target diff = [Profit margin %] - 'Profit Target '[Profit Target  Value]
- Total Profit Margin = Sum('sales transactions'[profit_margin])
- [Profit Target ] = GENERATESERIES(-0.05, 0.15, 0.01)
- Profit Target  Value = SELECTEDVALUE('Profit Target '[Profit Target ])

- Also, a date hierarchy was created to drill down on sale prices by year, quarter, month, and day

> Page 2 called "Ecomm vs. Brick and Mortar" is similar to page one, but looks at the sale differences between real stores (brick and mortar) and online stores (e-commerce)

> Page 3 called "Performance" looks at the Revenue by year and whether or not cities are meeting their Profit Targets. 

Overall, this dashboard provides a solid foundation for visualizing sales data across various cities. As the next step, it would be beneficial to conduct a deeper analysis aimed at replicating the successful results seen in profitable cities such as Delhi and Surat. This includes addressing the missing data for dates in cities like Hyderabad and Bengaluru that are currently not reflected in this dashboard.
Additionally, evaluating the performance of online versus in-store sales can offer valuable insights into potential areas for boosting E-commerce sales. By identifying key factors contributing to success in certain cities and channels, we can strategically implement these practices to drive overall sales growth.

    Profit Vs. Sales Dashboard (Power BI, SQL)
![Screen Shot 2025-02-20 at 5 48 38 PM](https://github.com/UserDna95/Sales-Dashboard-Indian-Dataset/blob/main/2025-02-20%20(19).png)
![Screen Shot 2025-02-20 at 5 48 38 PM](https://github.com/UserDna95/Sales-Dashboard-Indian-Dataset/blob/main/2025-02-20%20(20).png)
![Screen Shot 2025-02-20 at 5 48 38 PM](https://github.com/UserDna95/Sales-Dashboard-Indian-Dataset/blob/main/2025-02-20%20(21).png)
