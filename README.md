Customer Sales Analysis and Historic CLV Calculation
This notebook performs an in-depth analysis of customer sales data to understand customer behavior and calculate Historic Customer Lifetime Value (CLV).

Objectives
The primary objectives of this analysis are to:

Understand the dataset, including identifying missing values, data ranges, and key statistics.
Explore the dataset to identify outliers, analyze the impact of discounts on sales and profits, and determine factors affecting sales.
Determine the origin year for each customer to group them into cohorts.
Calculate cumulative transaction amounts for each customer cohort over time.
Calculate the number of new customers by origin year.
Compute the Historic CLV for each customer cohort.
Combine cohort-specific CLV into a single, volume-weighted average CLV curve.
Interpret the results and discuss their implications for the business.
Analysis Steps
The notebook follows these steps:

Data Loading and Initial Understanding:

Load the customer_sales.csv dataset into a pandas DataFrame.
Examine the first few rows and check for missing values.
Determine the date range of the data.
Count the number of unique customers and orders.
Calculate descriptive statistics for the 'Sales' field.
Analyze whether transaction amounts increase over time.
Data Exploration:

Check for outliers in the 'Sales' data using methods like the IQR.
Analyze the relationship between 'Discount', 'Sales', and 'Profit' through grouping and plotting.
Identify the optimal discount level for maximizing total profit.
Use linear regression to identify factors that affect 'Sales' the most (based on available numeric features).
Determine Customer Origin Year:

Identify the first order date for each unique customer.
Extract the origin year from the first order date.
Calculate Cumulative Transaction Amounts:

For each customer cohort (grouped by origin year), calculate the cumulative sum of 'Sales' at different age intervals (12, 24, 36, 48, 60, and 72 months from the first order date).
Calculate Number of New Customers:

Count the number of unique customers acquired in each origin year.
Calculate Historic CLV:

Divide the cumulative transaction amounts (from Step 4) by the number of new customers (from Step 5) for each cohort and age interval to get the Historic CLV per customer.
Combine Historic CLV:

Calculate a volume-weighted average of the Historic CLV across all cohorts at each age interval to create a single CLV curve.
Interpret Results:

Analyze the Historic CLV trends for different cohorts and the overall weighted-average CLV.
Discuss the spending patterns of customers and their implications for customer retention and acquisition strategies.
