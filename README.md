Online Retail — Data Cleaning & Visualization

📌 Project Overview

This project performs data cleaning, preprocessing, feature engineering, and visualization on an online retail transactions dataset.

The notebook uses the Online_Retail.xlsx dataset from a UK-based online gift retailer covering transactions from December 2010 to December 2011. The main goal is to clean raw transactional data and extract useful business insights through visual analysis.

🎯 Objectives

Load and inspect the raw online retail dataset.

Identify and handle missing values.

Remove exact duplicate records.

Separate cancelled transactions from valid sales.

Remove invalid quantities and prices.

Remove non-product stock codes.

Detect and remove extreme outliers using the IQR method.

Create useful time-based features.

Calculate revenue and order-level metrics.

Visualize important business trends and patterns.

Export the cleaned dataset for further analysis.

📊 Dataset

File: Online_Retail.xlsx

The notebook describes the raw dataset as:

Rows: 541,909

Columns: 8

Business: UK-based online gift retailer

Period: December 2010 – December 2011

The main transaction fields include invoice information, product details, quantity, date/time, price, customer ID, and country.

🛠️ Technologies Used

Python

Jupyter Notebook

Pandas

NumPy

Matplotlib

Seaborn

Excel / CSV

🧹 Data Cleaning Process

1. Missing Values

Missing Description values are replaced with UNKNOWN ITEM.

Missing CustomerID values are retained because they represent guest checkouts.

CustomerID is converted to Pandas nullable integer type.

2. Duplicate Removal

Exact duplicate rows are identified and removed using Pandas drop_duplicates().

3. Cancellation Handling

Invoices beginning with C are treated as cancellations.

Instead of deleting them immediately:

Cancellation records are stored separately in cancellations.

Valid sales are stored in df_sales.

This allows cancellation information to be used as a business metric.

4. Invalid Transactions

Transactions with:

Quantity <= 0

UnitPrice <= 0

are removed from the sales dataset.

Non-product stock codes such as postage, fees, manual adjustments, and bank charges are also excluded.

5. Outlier Treatment

The project uses the Interquartile Range (IQR) method.

A multiplier of k = 3 is used instead of the usual 1.5 because the dataset represents a gift/wholesale retailer where legitimate bulk purchases may occur.

The filtering is applied to:

Quantity

UnitPrice

6. Feature Engineering

The project creates the following features:

TotalPrice = Quantity × UnitPrice

Year

Month

YearMonth

DayOfWeek

Hour

The cleaned data is then exported as:

cleaned_online_retail.csv

📈 Visualizations

The notebook creates the following visualizations:

1. Monthly Revenue Trend

Shows how revenue changes month by month.

Output:
01_monthly_revenue_trend.png

2. Top 10 Countries by Revenue

Shows the countries generating the highest total revenue.

Output:
02_top_countries_by_revenue.png

3. Top 10 Best-Selling Products

Ranks products based on total quantity sold.

Output:
03_top_products_by_quantity.png

4. Order Value Distribution

Shows the distribution of invoice/order values.

Output:
04_order_value_distribution.png

5. Revenue by Day of Week

Compares revenue generated on different days of the week.

Output:
05_revenue_by_day_of_week.png

6. Top 10 Customers by Total Spend

Ranks registered customers based on total spending.

Output:
06_top_customers_by_spend.png

7. Combined Insights Dashboard

Combines multiple important visualizations into one dashboard.

Output:
07_dashboard_summary.png

📌 Key Metrics

The notebook calculates:

Total cleaned revenue

Total number of orders

Number of unique registered customers

Average order value

Top revenue-generating country

Revenue share of the top country

Best-performing month

Cancellation rate

🔍 Key Findings

According to the notebook analysis:

The cleaned dataset retains approximately 91% of the raw rows.

The UK generates the majority of revenue.

Revenue shows a strong peak around November, associated in the notebook with holiday gift-buying activity.

Order values are right-skewed, with many smaller orders and a smaller number of large/bulk orders.

Missing CustomerID values are treated as guest transactions rather than automatically being considered bad data.

📁 Project Structure

Online-Retail-Data-Cleaning-Visualization/
│
├── Online_Retail_Data_Cleaning_Visualization.ipynb
├── Online_Retail.xlsx
├── cleaned_online_retail.csv
│
├── 01_monthly_revenue_trend.png
├── 02_top_countries_by_revenue.png
├── 03_top_products_by_quantity.png
├── 04_order_value_distribution.png
├── 05_revenue_by_day_of_week.png
├── 06_top_customers_by_spend.png
└── 07_dashboard_summary.png

▶️ How to Run

1. Clone the repository

git clone https://github.com/your-username/Online-Retail-Data-Cleaning-Visualization.git
cd Online-Retail-Data-Cleaning-Visualization

2. Install dependencies

pip install pandas numpy matplotlib seaborn openpyxl jupyter

3. Start Jupyter Notebook

jupyter notebook

4. Open the notebook

Open:

Online_Retail_Data_Cleaning_Visualization.ipynb

Make sure Online_Retail.xlsx is available in the same working directory.

5. Run all cells

The notebook will clean the data, generate the analysis, save the cleaned CSV, and create the visualization images.

🚀 Possible Future Improvements

The notebook suggests several possible extensions:

RFM Customer Segmentation

Cohort and Retention Analysis

Market Basket Analysis

Association Rule Mining

Time-Series Revenue Forecasting

Customer lifetime value analysis

Product-level profitability analysis

💼 Skills Demonstrated

This project demonstrates practical skills in:

Data Cleaning

Exploratory Data Analysis (EDA)

Data Preprocessing

Feature Engineering

Outlier Detection

Missing Value Handling

Data Visualization

Business Analytics

Python

Pandas

NumPy

Matplotlib

Seaborn

👨‍💻 Author
Shubham Lad

🔗 GitHub
https://github.com/ladshubham742-bit/Shubham-Lad.

🔗 LinkedIn
www.linkedin.com/in/shubham-lad-314a66319.

⭐ If You Find This Project Useful
If you find this project helpful, consider giving the repository a ⭐ on GitHub!
