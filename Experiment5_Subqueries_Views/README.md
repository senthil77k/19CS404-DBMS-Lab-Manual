# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/1165e6ca-2d49-41ef-8cd1-a2061b5fef2e)

```sql
SELECT *
FROM CUSTOMERS
WHERE SALARY > 4500;
```

**Output:**

![image](https://github.com/user-attachments/assets/12dcc0a1-d671-4eb8-afe8-6bbd09ed688d)

**Question 2**
---
![image](https://github.com/user-attachments/assets/0223399a-4922-41ab-b72e-fb0285c6d2f5)

```sql
SELECT name
FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(*) = 1
);
```

**Output:**

![image](https://github.com/user-attachments/assets/c32f9b69-c4ee-4904-bb33-a5122fc12200)

**Question 3**
---
![image](https://github.com/user-attachments/assets/5ed2ffc7-fb7c-48ee-b9d9-badb1da0cd4d)

```sql

SELECT grade, COUNT(*)
FROM customer where grade > (SELECT AVG(grade) FROM customer WHERE city = 'New York')
GROUP BY grade;
```

**Output:**

![image](https://github.com/user-attachments/assets/514e626b-d8a0-4e4d-872f-b72ed53408ac)

**Question 4**
---
![image](https://github.com/user-attachments/assets/19e9b00d-58e3-48be-9fec-71f01570922b)

```sql
SELECT ord_no, purch_amt, ord_date, s.salesman_id
FROM orders
JOIN salesman s ON orders.salesman_id = s.salesman_id
WHERE s.commission = (
    SELECT MAX(commission)
    FROM salesman
);
```

**Output:**

![image](https://github.com/user-attachments/assets/c758ada8-76b8-497c-8d3f-80ec6f96436a)

**Question 5**
---
![image](https://github.com/user-attachments/assets/4adc7758-ab6d-4992-9651-fa6f3c6c8717)

```sql
select * from customers where Address= "Delhi" and AGE <30 Order by ID;
```

**Output:**

![image](https://github.com/user-attachments/assets/844d7884-a8d9-4a00-88af-aebaf3d7540d)

**Question 6**
---
![image](https://github.com/user-attachments/assets/5cd8edc7-44e3-45b4-b5ef-abe1f4fa9b4c)

```sql
select * from CUSTOMERS where salary < 2500;
```

**Output:**

![image](https://github.com/user-attachments/assets/8fe56024-791b-4878-8444-870ac2ff0320)

**Question 7**
---
![image](https://github.com/user-attachments/assets/1a0aee2a-92bf-4ceb-95fc-30236923af12)

```sql
SELECT *
FROM customer
WHERE customer_id = (
    SELECT salesman_id - 2001
    FROM salesman
    WHERE name = 'Mc Lyon'
);
```

**Output:**

![image](https://github.com/user-attachments/assets/3e82ec14-696f-4dd7-b8fd-77dc38494967)

**Question 8**
---
![image](https://github.com/user-attachments/assets/4a5d146b-59d6-4cd6-9aa4-9972c5af621d)

```sql
SELECT * FROM Employee
WHERE age < (
    SELECT AVG(age)
    FROM Employee
    WHERE income > 250000
);
```

**Output:**

![image](https://github.com/user-attachments/assets/57af9f69-6c7a-4db9-bd91-ba4efcdc96e9)

**Question 9**
---
![image](https://github.com/user-attachments/assets/41d01b5b-cef4-423f-af93-11f22d090cf5)

```sql
SELECT department_id, department_name
FROM Departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name))
    FROM Departments
);
```

**Output:**

![image](https://github.com/user-attachments/assets/8a96449a-21de-49b8-bfd1-af125e120e83)

**Question 10**
---
![image](https://github.com/user-attachments/assets/987464c8-4528-4a61-8f48-5d95f859e72f)

```sql
SELECT * 
FROM Employee
WHERE age < (
    SELECT AVG(age) 
    FROM Employee 
    WHERE income > 1000000
);
```

**Output:**

![image](https://github.com/user-attachments/assets/0eccc763-d792-4c2a-9ac7-f2c5cde8fff4)


## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
