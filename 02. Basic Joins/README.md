#### 1378 ( Right Join )
  - SELECT EmployeeUNI.unique_id, Employees.name FROM EmployeeUNI RIGHT JOIN Employees ON EmployeeUNI.id=Employees.id;

#### 1068 ( Left Join )
  - SELECT product_name, year, price FROM Sales LEFT JOIN Product ON Sales.product_id = Product.product_id

#### 1581 ( Count and Group By )
  - SELECT v.customer_id, COUNT(v.visit_id) as count_no_trans
  - from Visits v
  - LEFT JOIN Transactions t
  - ON v.visit_id = t.visit_id
  - WHERE t.transaction_id IS NULL
  - GROUP BY v.customer_id;

#### 197 ( Self Join and DATEDIFF )
SELECT w1.id FROM Weather w1, Weather w2
WHERE DATEDIFF(w1.recordDate, w2.recordDate) = 1 AND w1.temperature > w2.temperature;

