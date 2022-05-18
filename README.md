# Fall-2022-Data-Science-Intern-Challenge

# Question 1:
On Shopify, we have exactly 100 sneaker shops, and each of these shops sells only one model of shoe. We want to do some analysis of the average order value (AOV). When we look at orders data over a 30 day window, we naively calculate an AOV of $3145.13. Given that we know these shops are selling sneakers, a relatively affordable item, something seems wrong with our analysis. 

A)
The incorrectly calculated AOV of $3145.13 occurred due to calculating the total_items by using the count function instead of the sum function. Since the count function will only provide the sum of the number of rows in the total_items column and not the sum of the values in the rows. A better way to evaluate this data is to use the sum function to obtain the sum of the values in the rows.

B)    	
To obtain the correct AOV the reported metrics needed are the sums of the total_items and order_amount. Then, divide the sum of the order_amount column by the sum of the total_items columns to get the AOV.

AOV=Σorder_amount/Σtotal_items

C)    	
The Average Order Value is $357.92.

# Question 2: 

A)  
SELECT count(*)  
FROM Orders  
JOIN Shippers   
ON Orders.ShipperID=Shippers.ShipperID  
WHERE ShipperName = 'Speedy Express';  

Answer: 54 orders were shipped by Speedy Express  

B)  
SELECT Employees.LastName   
FROM Orders   
JOIN Employees   
ON Orders.EmployeeID=Employees.EmployeeID   
GROUP BY LastName   
ORDER BY Count(OrderID) DESC  
Limit 1;

Answer: Peacock is the employee with the most orders

C)  
SELECT Products.ProductName   
FROM Orders   
JOIN Customers   
ON Orders.CustomerID = Customers.CustomerID   
JOIN OrderDetails   
ON Orders.OrderID = OrderDetails.OrderID   
JOIN Products   
ON OrderDetails.ProductID = Products.ProductID   
WHERE Country = 'Germany'   
GROUP BY ProductName   
ORDER BY COUNT(ProductName) DESC   
LIMIT 1;

Answer: Gorgonzola Telino is the product most ordered by customers in Germany



