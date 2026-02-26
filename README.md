# Lab-3
EDA analysis
The dataset was loaded using Pandas.
After loading, the data structure and content were examined.
Data Types Inspection
The dataset initially contained some columns stored as object type, including the Date column
The Date column was converted to datetime format to enable time-based analysis:

df['Date'] = pd.to_datetime(df['Date'])

Converting the Date column allows grouping by month, year, and performing time trend analysis.
We checked for missing values using:

df.isna().sum()

The dataset does not contain significant missing values.
This indicates the data is clean and suitable for analysis.

If missing values had been present, appropriate handling methods such as removal or imputation would be applied.
Duplicate rows were checked to ensure no repeated transactions exist.

The dataset does not contain duplicate records, meaning each transaction is unique.

6️⃣ Datase
The dataset consists of:
3,282 rows
6 columns

This size is appropriate for performing exploratory analysis and extracting meaningful insights.
Distribution of Boxes Shipped

The histogram shows how shipment sizes are distributed.

Observation:

Most transactions involve a moderate number of boxes.

There are fewer transactions with very large shipment sizes.

This indicates that extreme large shipments are less frequent.
The line chart shows the monthly revenue trend over time.
Revenue increases during certain months, indicating possible seasonal effects.
Some months show noticeable drops, which may require further investigation
7️⃣ Descriptive Statistics

Descriptive statistics were calculated for numerical columns.

Key observations:

Boxes Shipped shows variability across transactions.

Revenue (Amount) has a wide range, indicating different transaction sizes.

The mean is higher than the median, suggesting possible right-skewness in revenue.
evenue by Sales Person

Revenue contribution varies among salespersons.

Observation:

A few salespersons generate higher total revenue.

Performance varies across individuals.

This may indicate differences in experience, region, or customer base.

🔟 Boxes vs Revenue Relationship

A scatter plot was created between Boxes Shipped and Revenue.

Observation:

There is a general positive relationship.

As the number of boxes increases, revenue increases.

This makes logical sense because revenue depends on sales quantity.

1️⃣1️⃣ Correlation Matrix

A heatmap was used to measure correlation between numerical variables.

Observation:

There is a strong positive correlation between Boxes Shipped and Amount.
1️⃣2️⃣ Time-Based Analysis

Monthly revenue was calculated using:

df['Month'] = df['Date'].dt.to_period('M')
monthly_revenue = df.groupby('Month')['Amount'].sum()

Observation:

Revenue fluctuates over time.

Some months show peaks in revenue.

Some months show noticeable declines.

This may indicate seasonal patterns or market variations.

Further investigation could analyze:

Seasonal demand

Promotions

Market conditions.
From the exploratory analysis, we conclude:

The dataset is clean and well-structured.

Revenue distribution is right-skewed.

Shipment size strongly affects revenue.

Some countries and products contribute more to total sales.

Salesperson performance varies.

Revenue shows time-based fluctuations, possibly seasonal.

Overall, the EDA provides a strong understanding of sales behavior and prepares the dataset for further machine learning modeling.

Correlation close to 1 indicates a strong linear relationship.

This confirms that shipment size is a key driver of revenue.
