**Week2**


Getting onto sqlite is a challenge.  I feel that the instructor is using one .db and I'm practicing on another, which isn't neccessarily bad.

When setting upsqlite:    
.headers  on   
.mode    column


SELECT    
FROM   
WHERE    
    =       
    <>    
    >    
    >    
    >            
    <    
    >=    
    <=     
    BETWEEN  AND    
    IS NULL    

Now IN, OR and NOT  

WHERE SupplierId is IN(3,5,7,10);     
WHERE ProductName = 'Tofu' OR "Cofu";     
   Be careful here because it will stop once it satisfies the OR statement.

With IN: you can list multiple items and broght it all back.        
With OR:  You can only list two items.     

WHERE (SupplierId = 9 OR      
        SupplierId = 15)     
        AND UnitPrice < 16;     
Place () around the OR statement to make sure that it runs first, and then the AND runs.  Also its a good habit.

WHERE NOT City ='London' AND NOT City = 'Seattle';  
**Make sure that you're using single quotes '' and not "" to denote itemsI**     
 **Using Wildcards**     
 LIKE - can be used with text or string data, but not numericals.   
 '%Pizza'  - Anyhing **ending** with Pizza   
 'Pizza%'  - Anything **after** the word Pizza    
 '%Pizza%'  - Grabs anything before and after the word Pizza.  
 'S%E'    - Grabs anything that starts with S and ends with E    
 't%@gmail.com' - Grabs gmail email addr that starts with T.    
Wildcards will NOT match NULL values.
Downsides - querries take a longer time to run.   

**Sorting with ORDER BY**

Sorts data by particular column(s).  Add comma between colummns.
Must be the last clause in the SELECT statement.  
DESC or ASC

**Math Operations**

SELECT   
ProductId     
,UnitsOnOrder     
,UnitPrice     
,UnitsOnOrder * UnitPrice AS Total_Order_Cost   
FROM Products;

Order of Operations    
- paraenthesis
- Exponents
- Multiplication
- Division
- Addition
- Subtraction
**Aggregte Functions**
- AVG()
- COUNT()
- MIN()
- MAX()
- SUM()
SELECT COUNT(CustomerID) AS     
    total_customers
    FROM Customers

Can use Function (*) if you want to iterate over everything, i.e.,

SELECT COUNT (*) AS
total_customers
    FROM Customers

Returns total rows in the column Customers.
Ignores NULL values.

**Min and Max**
SELECT MAX(UnitPrice) AS max_prod_price
FROM Products;    

NULL Values ignored 

DISTINCT()
  Cannot use DISTINCT on COUNT with (*)    

**Grouping Data with SQL**

GROUP BY 
 SELECT Region
 , COUNT(CustomerID) AS total_customers
    FROM Customers
    GROUP BY Region

WWHERE does not work for groups, because it filters on rows. Therefore, we have to use the HAVING clause when filtering with an aggregate function in grouping them.

WHERE filters **before** the data is grouped and then HAVING filters **after** the data is grouped.

Good practice to use ORDER BY with GROUP BY because GROUP BY does not order the data in any fashion.  It just groups it.








