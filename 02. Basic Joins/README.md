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
  - SELECT w1.id FROM Weather w1, Weather w2
  - WHERE DATEDIFF(w1.recordDate, w2.recordDate) = 1 AND w1.temperature > w2.temperature;

#### 1661 ( Average and Round off )
  - SELECT *  from Activity a1, Activity a2
  - WHERE a1.process_id = a2.process_id AND a1.machine_id = a2.machine_id AND a1.activity_type = 'start' AND a2.activity_type = 'end'
  - GROUP BY a1.machine_id

#### 577
  - SELECT name, bonus 
  - FROM Employee as e LEFT JOIN Bonus as b 
  - ON e.empId = b.empId
  - WHERE b.bonus < 1000 || b.bonus IS NULL

#### 
