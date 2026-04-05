SQL QUERIES

--Revenue--
SELECT
YEAR(Date) as Year,
SUM(TotalPrice) as Revenue 
FROM [Online-Store-Orders]
GROUP BY YEAR(Date)
ORDER BY Year


--Total Order--
SELECT 
YEAR(Date) as Year,
COUNT(OrderID) as Total_Orders
FROM [Online-Store-Orders]
GROUP BY YEAR(Date)
ORDER BY Year


--Total Quantity--
SELECT 
YEAR(Date) as Year,
SUM(Quantity) as Total_Qty
FROM [Online-Store-Orders]
GROUP BY YEAR(Date)
ORDER BY Year, Total_Qty


--Returned Orders--
SELECT 
YEAR(Date) as Year,
COUNT(*) as Returned_Orders 
FROM [Online-Store-Orders]
WHERE OrderStatus = 'Returned'
GROUP BY YEAR(Date)
ORDER BY Year


--Cancelled Orders--
SELECT 
YEAR(Date) as Year,
COUNT(*) as Cancelled_Orders
FROM [Online-Store-Orders]
WHERE OrderStatus = 'Cancelled'
GROUP BY YEAR(Date)
ORDER BY Year

--Delivered Orders--
SELECT 
YEAR(Date) as Year,
COUNT(*) as Delivered_Orders
FROM [Online-Store-Orders]
WHERE OrderStatus = 'Delivered'
GROUP BY YEAR(Date)
ORDER BY Year


--Average Order Value--
SELECT 
SUM(TotalPrice) / COUNT(OrderID) As AOV 
FROM [Online-Store-Orders]


--Top Selling Product--
SELECT
YEAR(Date) as Year,
Product,
SUM(TotalPrice) as Revenue
FROM [Online-Store-Orders]
GROUP BY YEAR(Date), Product
ORDER BY Year, Revenue DESC


--Monthly Revenue Trend--
SELECT 
YEAR(Date) as Year,
MONTH(Date) as Month,
SUM(TotalPrice) as Monthly_Revenue 
FROM [Online-Store-Orders]
GROUP BY YEAR(Date), MONTH(Date)
ORDER BY Year, Month


--Monthly Quantity Sold Trend--
SELECT 
YEAR(Date) as Year,
MONTH(Date) as Month, 
SUM(Quantity) as Total_Qty
FROM [Online-Store-Orders]
GROUP BY YEAR(Date), MONTH(Date)
ORDER BY Year, Month


--Monthly Total Order Trend--
SELECT 
YEAR(Date) as Year,
MONTH(Date) as Month, 
COUNT(OrderID) as Total_Order
FROM [Online-Store-Orders]
GROUP BY YEAR(Date), MONTH(Date)
ORDER BY Year, Month


--Total Orders by Status--
SELECT 
YEAR(Date) as Year,
OrderStatus,
COUNT(OrderID) as Total_Order
FROM [Online-Store-Orders]
GROUP BY  YEAR(Date), OrderStatus
ORDER BY Year


--Revenue by Payment Method--
SELECT 
YEAR(Date) as Year,
PaymentMethod,
SUM(TotalPrice) as Revenue
FROM [Online-Store-Orders]
GROUP BY YEAR(Date), PaymentMethod
ORDER BY Year


--Revenue by Referral Source--
SELECT 
YEAR(Date) as Year,
PaymentMethod,
SUM(TotalPrice) as Revenue
FROM [Online-Store-Orders]
GROUP BY YEAR(Date), PaymentMethod
ORDER BY Year
