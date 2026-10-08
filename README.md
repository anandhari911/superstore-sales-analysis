# superstore-sales-analysis

Input Data Schema
The incoming data source must adhere following rules.
order ID- String 
date- Date format
Product- String
Category-String
Region-String
Quantity- Integer 
Price- Decimal
Discount- Decimal
Customer ID- String

Then we need to clean and validate the data to check :
1.) Duplicate values:  Remove exact duplicates rows across all fields. 
2.) NULL Values: Confirm zero NULL or empty cells exist in Order ID , Date, Quantity, Price
3.) We have to check the range for each rows like quantity must be a positive value price must be greater than zero, Discount must be bounded between 0.00 and 0.30

Total Revenue is calculated as 
 Total Revenue=Quantity*Price*(1-Discount)
First we have to calculate the Gross Revenue
Gross Revenue=Quantity * Price
Then finally we have to calculate the Net Revenue
Net Revenue=Gross Revenue*(1-Discount)


 Total Cost is the cost procured and operating cost to deliver products, benchmarked at 60% of gross retail price
       Total Cost=SUM(Quantity * Profit * 0.60)
   
 Average Order Value(AOV):  Ratio of Total Net Revenue to Count of Unique Order ID

Profit Margin% is the percentage of net revenue to net profit
 Profit Margin=(Total Net Profit/Total Net Revenue)*100

Overall Dashboard Totals:
Across 9,989 unique orders, the business generated 21.16M in Total Revenue and 17.25M in Total Profit after subtracting 3.91M in Total Cost.   Profitability Baseline: The overall business operates at an Average Order Value (AOV) of 2.12K and a Profit Margin ratio of 0.82 (82% of revenue retained as profit).   

Technology & High-Value Product Dominance: The top 4 products (Machines, Copiers, Accessories, Phones) each generated over 3.0M in Total Revenue individually (totaling 12.93M), whereas the bottom 5 products (Paper, Storage, Art, Supplies, Appliances) generated less than 150K each.  

Geographic Distribution: Revenue is evenly split across all 4 territories, with the South Region leading at 5.56M, followed by East at 5.30M, Central at 5.26M, and West at 5.05M.   

Discount Performance: Profit Margin remains elevated at 0.82 across discount levels (0.0 to 0.3) in the chart, showing that order volume remains stable across all price points.   

Top Revenue Category is Technology Category where Bottom Revenue Category is Office Supplies 

Total Net Revenue: Must equal SUM(Net Revenue) in CSV (Baseline: ₹21,158,486.06 / $21,158,486.06).

Unique Order Count: Must equal COUNT(DISTINCT Order ID) (Baseline: 9,989 orders).

