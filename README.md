# DAX-Assignment
DAX and Data Visualisation
calculated columns
Category Type = 'Order Details (1)'[Category] & "-" & 'Order Details (1)'[Sub-Category]
Revenue = 'Order Details (1)'[Amount] * 'Order Details (1)'[Quantity]
Sales Category = IF('Order Details (1)'[Amount]>= AVERAGE('Order Details (1)'[Amount]) , "Above Average" , "Below Average")
calculated measures
Total orders = COUNT('Order Details (1)'[Order ID])
Average profit Delhi = CALCULATE(AVERAGE('Order Details (1)'[Profit]),'List of Orders (1)'[City]= "Delhi")
created a DATE TABLE = ADDCOLUMNS(CALENDAR(DATE(2018,01,01),DATE(2019,03,31)),"YEAR",YEAR([Date]),"MONTH NUMBER",MONTH([Date]),"MONTH NAME",FORMAT([Date],"MMMM"),"QUARTER", "Q" & QUARTER([Date]), "DAY", DAY([Date]),"DAY NAME",FORMAT([Date],"DDDD"))

Sales YTD = TOTALYTD(SUM('Order Details (1)'[Revenue]),'DATE TABLE'[Date])
Data visualisation
column chart / x-axis= category , y-axis=total sales & sum of target
Donut chart / legend= sub category , values= max profit
Line chart / x-axis = month name , y-axis=total sales
scatter chart/ values=sub category , x-axis= sum of quantity , y-axis=sum of profit
cards/ total sales , total target 
value=min target , category = sub category
matrix / rows= category and month name , values= total sales and total target
map/ location=city , bubble size = total sales
tree map / category=sub category , values= total sales
funnel / category=state , values=total orders
