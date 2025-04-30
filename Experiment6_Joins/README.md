# Experiment 6: Joins

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/0a491a13-35ee-4cde-854b-da3e81dd9ba6)

```sql
SELECT n.*
FROM nurses n
INNER JOIN departments d ON n.department_id = d.department_id
WHERE d.department_name = 'Pediatrics';
```

**Output:**

![image](https://github.com/user-attachments/assets/7a29a676-a4ca-4ac6-9320-72be1f6548f1)

**Question 2**
---
![image](https://github.com/user-attachments/assets/5e071a37-4a54-4d14-a0c7-b2d082c6bbce)

```sql
SELECT c.cust_name AS "Customer Name", 
       c.city AS "city", 
       s.name AS "Salesman", 
       s.city AS "city", 
       s.commission 
FROM customer c
INNER JOIN salesman s ON c.salesman_id = s.salesman_id
WHERE c.city != s.city
  AND s.commission > 0.12;
```

**Output:**

![image](https://github.com/user-attachments/assets/6b3d8ce5-e759-459f-9945-66de2308ccf6)

**Question 3**
---
![image](https://github.com/user-attachments/assets/0b902c3b-1cd7-4f6b-b3ea-188bf928f819)

```sql
SELECT c.cust_name , 
       c.city , 
       o.ord_no, 
       o.ord_date, 
       o.purch_amt AS "Order Amount", 
       s.name AS "name", 
       s.commission
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id
LEFT JOIN salesman s ON o.salesman_id = s.salesman_id
;
```

**Output:**

![image](https://github.com/user-attachments/assets/05d520a6-34e5-448d-a38c-8ff09202bfb5)

**Question 4**
---
![image](https://github.com/user-attachments/assets/34ed136d-bc81-4a1a-804d-eeffcfd2c23a)

```sql
SELECT p.*, d.first_name AS doctor_name
FROM patients p
INNER JOIN doctors d ON p.doctor_id = d.doctor_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/c3feb091-4b02-41d1-a4ca-103414643a0c)

**Question 5**
---
![image](https://github.com/user-attachments/assets/bb5c3112-3f40-4e07-ae1f-7b6e4da2054e)

```sql
SELECT o.ord_no, o.purch_amt, c.cust_name, c.city
FROM orders o
INNER JOIN customer c ON o.customer_id = c.customer_id
WHERE o.purch_amt BETWEEN 500 AND 2000;
```

**Output:**

![image](https://github.com/user-attachments/assets/8678c93b-8d81-4247-8ab3-a64b03fc43af)

**Question 6**
---
![image](https://github.com/user-attachments/assets/2dcb89ca-3bdf-442d-92cc-24e65a03ef0c)

```sql
SELECT c.cust_name
FROM customer c
LEFT JOIN orders o ON c.customer_id = o.customer_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/e73417ce-4672-4166-b5c6-0999f2ef23b4)

**Question 7**
---
![image](https://github.com/user-attachments/assets/0ec344e7-5a21-4821-9a66-52a923311a1d)

```sql
SELECT s.name AS Salesman, c.cust_name, c.city
FROM salesman s
JOIN customer c ON s.city = c.city;
```

**Output:**

![image](https://github.com/user-attachments/assets/bc7b68f9-8788-4711-a206-f04a626dfeb0)

**Question 8**
---
![image](https://github.com/user-attachments/assets/01ae6cee-6a62-473e-925d-8e936f6f4d46)

```sql
SELECT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
WHERE c.city = 'London';
```

**Output:**

![image](https://github.com/user-attachments/assets/83531fe3-2220-4b9b-8bff-df1e9478683b)

**Question 9**
---
![image](https://github.com/user-attachments/assets/87d967d5-f4df-461d-9167-44d82f00ab02)

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders o
JOIN customer c ON o.customer_id = c.customer_id
JOIN salesman s ON o.salesman_id = s.salesman_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/d7729c58-e3ac-4743-b5c4-cf9a3d68af45)

**Question 10**
---
![image](https://github.com/user-attachments/assets/59dff5bf-e445-4b65-87f5-c10175c45be4)

```sql
SELECT 
    p.first_name AS patient_name,
    d.first_name AS doctor_name
FROM 
    patients p
INNER JOIN 
    doctors d ON p.doctor_id = d.doctor_id
WHERE 
    p.discharge_date IS NOT NULL;
```

**Output:**

![image](https://github.com/user-attachments/assets/60146667-30e8-4fb6-85f8-b07b1366aa7a)


## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
