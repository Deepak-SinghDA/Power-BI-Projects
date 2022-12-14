# Power-BI-Projects
## Creating a Retail Super Store Profit report
- An example of a Power BI dashboard with multiple data types can help you understand the benefits of Power BI. 
 - Each data type has the potential for valuable business insights. Consider a retail superstore, where data can be used to unlock insights about regional sales, individual store transactions, and product categories.

- The following points are relevant to the business perspective of the use case:
  - Which region is more profitable than others?
  - What customer segments should you be focusing on?
  - Identify segments that can reduce investment.
  - To gain insights on the abovementioned points, you’ll need to change how data is processed. 
  - The goal is to increase business productivity and profitability. Let’s see what insights we can gain from superstore data.
1. Sum of Profit by Year & Quarter.
2. Sum of Profit by Sub Category.
3. Sum of Profit by Region.
4. Sum of Profit by Segment.
5. Sum of Profit by Category.
6. Sum of Sub Category Profit by Region.
7. Profit by State.

## Sales Insight Data Analyst Project
In this Power BI Project I did data cleaning and built a Power full Dashboard that can help us generate sales Insights on Hardware business.
+	Data Analysis Using SQL
 1.	Show all customer records
  - SELECT * FROM customers;
 2.	Show total number of customers
  -	SELECT count(*) FROM customers;
 3.	Show transactions for Chennai market (market code for chennai is Mark001
  -	SELECT * FROM transactions where market_code='Mark001';
 4.	Show distrinct product codes that were sold in chennai
  -	SELECT distinct product_code FROM transactions where market_code='Mark001';
 5.	Show transactions where currency is US dollars
   -	SELECT * from transactions where currency="USD"
 6.	Show transactions in 2020 join by date table
   -	SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;
 7.	Show total revenue in year 2020,
   -	SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";
 8.	Show total revenue in year 2020, January Month,
   -	SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");
 9.	Show total revenue in year 2020 in Chennai
  -	SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
### Data Analysis Using Power BI
  -	Formula to create norm_amount column
    - 	= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)
