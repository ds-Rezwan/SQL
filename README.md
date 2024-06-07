# SQL
SQL, or Structured Query Language, is a standardized programming language used for managing and manipulating relational databases. It is essential for performing various operations such as querying, updating, inserting, and deleting data within a database. Here are some key aspects of SQL:
# SQL Queries and Operations:
# 1 Basic Query:

A simple query to retrieve data from a table

SELECT * FROM employees;
# 2 Filtering Data:
Using the WHERE clause to filter data.

SELECT * FROM employees WHERE salary > 50000;
# 3 Sorting Data:
Using ORDER BY to sort data.

SELECT * FROM employees ORDER BY salary DESC;
# 4 Joining Tables:
Combining data from multiple tables using joins.

SELECT employees.name, departments.department_name

FROM employees

JOIN departments ON employees.department_id = departments.id;
# 5 Grouping Data:
Using GROUP BY to group data and aggregate results.

SELECT department, COUNT(*) AS num_employees, AVG(salary) AS avg_salary
FROM employees

GROUP BY department;
# 6 Subqueries:
Using a query within another query.

SELECT name, salary 

FROM employees

WHERE salary > (SELECT AVG(salary) FROM employees);
# Advanced SQL Concepts:
# 1 Indexes:Indexes improve the speed of data retrieval.

CREATE INDEX idx_salary ON employees(salary);
# Views:
Views are virtual tables created by a query.

CREATE VIEW high_earners AS

SELECT name, salary FROM employees WHERE salary > 75000;
# Stored Procedures:
Stored procedures are saved queries or routines that can be executed.

CREATE PROCEDURE increase_salary (IN employee_id INT, IN increase_amount DECIMAL(10, 2)) 

BEGIN

   UPDATE employees SET salary = salary + increase_amount WHERE id = employee_id;
  
  END;
  # Triggers:
  Triggers are automatic actions executed in response to specific events on a table.

CREATE TRIGGER after_employee_insert

AFTER INSERT ON employees
FOR EACH ROW

BEGIN

  INSERT INTO audit_log (action, employee_id) VALUES ('INSERT', NEW.id);
  
END;

SQL is a powerful and versatile language essential for database management and manipulation. It provides various statements and functionalities for defining database schemas, manipulating data, controlling access, and managing transactions. By mastering SQL, you can efficiently interact with and extract valuable insights from relational databases, which is crucial for many fields, including data analysis, web development, and data science.
  












