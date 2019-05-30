## SQL_Week_3

##Subqueries and Joins:

A query embedded within a query.    
1.  Start with the inner-most query
2.  No limit to subqueres
3.  Slows performance
4.  Can only select one column at a time.

Best practices:     
Indent each SELECT series
www.poorsql.com  

**Cartesian or Cross Join** 
**Takes one table and multiplies it on the other**    
SELECT product_name
,unit_price (from products table)
,company_name (from the suppliers table)
FROM suppliers CROSS JOIN products;

**Inner Joins**
Select matching values in both records: Union

SELECT suppliers.CompanyName
    ,ProductName
    ,UnitPrice
FROM Suppliers INNER JOIN Products
ON Suppliers.suppliersId = 
Products.suppliersId;

Prequalifying....small nightmare:

SSELECT o.OrderID, c.CompanyName
,e.LastName 
FROM((Orders o INNER JOIN Customers c ON 
o.CustomerId = c.CustomerId)  
INNER JOIN Employees e ON o.EmployeeID = 
e.EmployeeId);

**Aliases and Self Joins**     
Table aliases: Shortening names and simplifying how we're pre-qualifying them. SELECT vendor_name
    ,product_name
    ,product_price
FROM Vendors AS v, Products AS p
WHERE v.vendor_id = p.product_id 

Set-up the "aliases in the FROM line.     
You don't have to use single letters.  Can us pr, vn, etc...

**Self Joins**

SELECT column_name(s)
FROM table1 T1, table2 T2
WHERE condition;

This is because the LEFT JOIN command tells the database to return all rows in the table in the FROM clause, regardless of whether or not they have matches in the table in the LEFT JOIN clause.    

Normally, filtering is processed in the WHERE clause once the two tables have already been joined. It’s possible, though that you might want to filter one or both of the tables before joining them. For example, you only want to create matches between the tables under certain circumstances.    





