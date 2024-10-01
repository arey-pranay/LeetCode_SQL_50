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

#### 1280
- SELECT s.student_id, s.student_name, sub.subject_name, COUNT(e.student_id) AS attended_exams
- FROM Students s
- CROSS JOIN Subjects sub
- LEFT JOIN Examinations e ON s.student_id = e.student_id AND sub.subject_name = e.subject_name
- GROUP BY s.student_id, s.student_name, sub.subject_name
- ORDER BY s.student_id, sub.subject_name;

#### 570

- SELECT name from Employee JOIN(
-  SELECT managerId from (
-    SELECT managerId, count(managerId) as c
-   FROM Employee 
-   GROUP BY managerId 
- ) AS managerTable
- WHERE c >= 5
- ) AS manager 
- on Employee.id = manager.managerId

#### 1934

- select s.user_id,round(avg(if(c.action='confirmed',1,0)),2) as confirmation_rate
- from Signups s left join Confirmations c
- using (user_id)
- group by s.user_id
