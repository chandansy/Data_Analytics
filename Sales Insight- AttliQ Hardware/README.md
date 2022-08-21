## Sales Insights Data Analysis Project,
In this project, I've acted out the settlement of a business issue for an Indian hardware manufacturer.

**AtliQ Hardware**
- Is a business that serves a large number of customers in India by providing computer hardware and accessories.
- The business has regional offices all throughout India in addition to its head office in Dehli.

**Business Problem**
  The sales director is facing a lot of issues such as: The market is increasing dynamically and so he’s suffering in terms of tracking the sales, demanding more     accurate information about the company sales, and then take the appropriate judgments.
  
**Consider the following situation**: 
The sales director has to be aware of the status of sales across all operations, and the information provided by regional sales managers is insufficient.
Receiving a tonnes of excel files or just hearing the figures is hardly ever a trustworthy way huge get a handle on the business.
Instead, he preferred to be able to quickly analyse the data and determine what was happening.

**Solution**
Create a simple yet very insightful dashboard using PowerBi;
I used **SQL** queries in **MySQLWorkbench** to take a look into data and Power BI for ETL and visualizations to create the insights.

**Overview**
After a quick look at the data in MySQL , here are some quick findings.
The database contains 5 tables: customers, date, markets, products, and transactions;
There are 17 markets, 279 products, and 38 customers;
The observation period is from january 2018 to june 2020;
The total revenue in 2020 was Rs142,23 Milion, 42% less than 2019, which was Rs336,45 Million;
Most of the transactions data are in INR currency, but there were 4 records in US $ currency.
And Paris and New York were observed on the “sales markets” table.It will be dealt with in the ETL process.

**ETL (Extract, Transform, Load)**

Once I know the basic features of the data I have to work with, I imported the MySQL database into Power BI to do the necessary transformations and end up with a simple, reliable, and useful dashboard.

**Data Modelling**
There are in total of 5 tables , and it should be made sure that the tables are connected correctly.

![image](https://user-images.githubusercontent.com/100086571/185561528-7a3e4f3b-e4dc-4ba4-972e-b7c620463e3e.png)

**sales transactions** — main table
TABLES CONNECTED
- sales customers > connected by “customer_code” column;
- sales date> connected by “date” column;
- sales products > connected by “product_code” column;
- sales markets > connected by “market_code” column.

**Measures Created**
“Revenue” and “Sales Qty” measures to get the sum of each column instantly in the dashboard.
![image](https://user-images.githubusercontent.com/100086571/185562149-2ab17889-af50-42f1-ac4d-097d57e87504.png)

**Filtering**
Once the company is operating only in India, Ifiltered out “Paris” and “New York” in the sales markets table by unchecking the “(blank)” field in the “zone” column
![image](https://user-images.githubusercontent.com/100086571/185562945-8f169745-3909-46a5-bd51-f4e1a535fe63.png)

Cleaning and adding new column**
- The “sales_amount” column has -1 and 0 values. I removed them in this case so we can see only the actual sales numbers on the dashboard (sometimes “0” means promotional sales and giveaways, but to know that, we should have further information, which is not the case of this project).

- I find out that the “currency” column (sales transactions table) have 4 USD currency values, 2 of them with hidden characters, so i had to include an argument into the conditional formula, in order to create a new column called “norm_sales_amount”, where it converts the USD currency value into INR currency value.

After all the analysis , the data is reliable enough to build the dashboard.

**Dashboard**

![image](https://user-images.githubusercontent.com/100086571/185780641-c07b81fe-c766-4fc9-ba48-4a1addd0606c.png)













