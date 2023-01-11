# Data Analysis Project – Using Power BI

Power Bi project to analyze Superstore sales dataset of year 2010 to March-2014 to derive some useful insights from it .

# Overview

This data Analysis Based on a superstore sales dataset which I have taken from Kaggle. This Report’s and Dashboard aim to find some useful insights so that the company can use it to understand their sales, profits, loss and current market’s performance.

# Steps Followed 

1)	Data Cleaning
2)	Data Modeling
3)	Analyzing data
4)	Creating power BI reports
5)	Creating Dashboard

### Step1: Data Cleaning
- The data in the Superstore sales workbook is not in a cleaned format, so I have used power Query to transform the data.
- Renamed the tables (users->Managers).
- Promoted the 1st row as headers of the columns.
- Removed the unwanted columns and selected the only columns that is most relevant for the analysis by using the option choose columns.
- Renamed the columns with meaningful text (State or province  Sate).
- Checked for the datatypes of the columns (any mismatched to text)

### Step 2:  Data Modeling
- Added $ symbol to Discount, price, shipping cost, Profit, Sales as these columns are currency.
- Formatted the Order date and ship date into (mmmm,d,yyyy) format.
- Categorize the columns ( Sate  state or province, city  city, postal code postal code).
#### Breaking down the Tables:
All the details , like customer details, product details and order details are in the same table. Separated the Customer details into DimCustomers table and product details into DimProducts . These are dimension tables.

### Step 3: Analyzing data

Know we have cleaned data for analysis. Look at the data and find the connections between the columns . 
Created calculated columns like columns for year, Quarter, Month, Days to ship by using the order date and ship date columns.
- Days to ship = DATEDIF(Orders[order date].[Date],Orders[ship date].[Date])
- Month = month(Orders[order date])
- Quarter = quarter(Orders[order date])
- Year= year(Orders[order date])

Create Measures which will be helpful while creating reports.
Here are some measure I have created in this project:
- Average of Sales total for Customer Segment = CALCULATE(AVERAGE('Orders'[Sales]), ALL('Orders'[Customer Segment]))
- Orders Quantity = COUNT([Order ID])
- Total Loss = ABS(SUM(Orders[Loss]))
- Total Profit = SUM(Orders[Profit]) 
- Total Sales = CALCULATE(SUMX(Orders,Orders[Sales]))
- Total Shiping Cost = SUM(Orders[Shipping Cost])
- Total Units sold= COUNT([Unit Price])
- Step 4: Creating power BI reports
- Created Below Reports Using the Data.
#### 1)	Sales Overview 
 ![image](https://user-images.githubusercontent.com/72013551/211145440-b1875901-3de8-4f41-8345-8bdfaa990ae8.png)

#### 2)	Category Analysis
 ![image](https://user-images.githubusercontent.com/72013551/211145443-dd169218-148d-419c-8214-e528a9a06a81.png)

#### 3)	Growth Opportunities
 ![image](https://user-images.githubusercontent.com/72013551/211145452-862cac2e-084d-455b-babf-6fe16f8e7b59.png)


### Step 5: Creating Dashboard

![image](https://user-images.githubusercontent.com/72013551/211145473-aab73070-0deb-44dc-9a0d-afe16e44c988.png)
![image](https://user-images.githubusercontent.com/72013551/211145478-abed2bec-6b87-4282-9b03-898665b576c8.png)
![image](https://user-images.githubusercontent.com/72013551/211145484-03b77b4a-14ef-4e39-a127-cdd2af5b45ab.png)


# Findings From Reports

### Finding 1 : Total No. of Sales And Total Profit (2010 – 2014)
According to the dataset 8.95M sales done in 4 years with total profit of 1.13M and total loss of 1.16M.
Year wise sales and profit findings

- In 2010 it was 1.91M with profit of 0.20M and loss of 0.29M.
- In 2011 , Total sales is 1.93M with Profit of 0.30M and loss of 0.25M.
- In 2012, Total sales is of 2.25M with the profit  of 0.35M and loss of 0.26M.
- In 2013 , Total sales is of 2.85 M with the profit 0.45M which was highest amongst above and loss of 0.37M .

### Finding 2 : Sum of Sales By Customer Segment
In These Years sales have happened in 4 segments which are

- Consumer (1.84M sales, 0.21M Profit )
- Corporate (3.27M sales , 0.51M profit )
- Home Office(2.17M sales , 0.28M profit )
- Small Business(1.68M sales, 0.32M profit) 

So highest sales and profit happened in corporate segment and lowest profit in consumer segment .  superstore must focus more on Consumer to improve profits.

### Finding 3 : category analysis 
As per the Category analysis we can see the Total units sold in a product category per year. 

We can also see the sales made per product sub category from which we can understand which products are selling more and focus on improving the other categories.
### Finding 4 : Top 5 Products

As per the Growth Opportunities  the top 5 products are
 ![image](https://user-images.githubusercontent.com/72013551/211145542-6f508ed3-c3b5-4a1d-a3a4-c63814e8bc7b.png)

I have shared pbix file and dataset so that anyone can easily question any insight .


