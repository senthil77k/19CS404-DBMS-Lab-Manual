# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
![image](https://github.com/user-attachments/assets/e91852a3-331c-480f-842f-e6ee392c646e)

```sql
SELECT PatientID, COUNT(*) AS AvgMedications
FROM MedicalRecords
GROUP BY PatientID;
```

**Output:**

![image](https://github.com/user-attachments/assets/49e9e08a-df9b-42b0-970f-37cf15096e50)

**Question 2**
---
![image](https://github.com/user-attachments/assets/25becd1a-d009-4965-a2fa-d1e254d7a4c9)

```sql
SELECT Medication, 
    CASE 
        WHEN Dosage GLOB '*[0-9]*' THEN CAST(
            SUBSTR(Dosage, 1, INSTR(Dosage, ' ') - 1) AS REAL
        )
        ELSE 0.0
    END AS AvgDosage
FROM Prescriptions
GROUP BY Medication;
```

**Output:**

![image](https://github.com/user-attachments/assets/f1ea69f5-a136-4030-b1ab-5d6ed7fbdff3)

**Question 3**
---
![image](https://github.com/user-attachments/assets/e60cca01-79e0-40e2-8a21-96645ce6070f)

```sql
SELECT 
    Gender, 
    COUNT(*) AS TotalPatients
FROM 
    Patients
GROUP BY 
    Gender;
```

**Output:**

![image](https://github.com/user-attachments/assets/3cf739ae-6d2f-4d70-bb1c-5835ec823479)

**Question 4**
---
![image](https://github.com/user-attachments/assets/7370db73-3d6b-418e-afcd-10f00165a2a2)

```sql
SELECT 
    name AS Employee_Name, 
    age AS Age
FROM 
    employee
ORDER BY 
    age ASC
LIMIT 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/96727dc1-7aad-407b-95e3-4a4536ce0121)

**Question 5**
---
![image](https://github.com/user-attachments/assets/6c67202a-6402-48ea-bb7e-2dc76779333b)

```sql
SELECT 
    name AS fruit_name, 
    inventory AS lowest_quantity
FROM 
    fruits
WHERE 
    inventory = (SELECT MIN(inventory) FROM fruits);
```

**Output:**

![image](https://github.com/user-attachments/assets/1b77f683-0489-4cdc-a0c7-ae221de84b0f)

**Question 6**
---
![image](https://github.com/user-attachments/assets/c5611e21-a388-4c57-9e11-dd4594f80dbd)

```sql
SELECT COUNT(*) AS employees_in_california
FROM employee
WHERE city = 'California';
```

**Output:**

![image](https://github.com/user-attachments/assets/1dceb46c-f5c8-4600-b659-5db9aeb1db81)

**Question 7**
---
![image](https://github.com/user-attachments/assets/6e00bc9a-9993-4cc8-9a71-01e3fb9b0321)

```sql
SELECT name, email, LENGTH(email) AS min_email_length
FROM customer
ORDER BY LENGTH(email) ASC
LIMIT 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/6e34396b-4c04-4585-8598-5e898e06b4da)

**Question 8**
---
![image](https://github.com/user-attachments/assets/6dad107c-31c5-4153-9eb8-5224e7862938)

```sql
SELECT jdate, AVG(workhour) AS "AVG(workhour)"
FROM employee1
GROUP BY jdate
HAVING AVG(workhour) < 10
ORDER BY AVG(workhour) DESC
LIMIT 2;
```

**Output:**

![image](https://github.com/user-attachments/assets/c8300973-a425-4be1-b033-3519e99d3d3f)

**Question 9**
---
![image](https://github.com/user-attachments/assets/9bc60292-68b8-4ab0-9ca9-3e4c5edca6d5)

```sql
SELECT city, AVG(income) AS "AVG(income)"
FROM employee
GROUP BY city
HAVING AVG(income) > 500000;
```

**Output:**

![image](https://github.com/user-attachments/assets/d83a337e-8fb3-4c52-bec9-87b723bb2450)

**Question 10**
---
![image](https://github.com/user-attachments/assets/0e540bc7-9c5c-4de1-9555-859999fb0dc4)

```sql
SELECT age, SUM(income) AS "SUM(income)"
FROM employee
GROUP BY age
HAVING SUM(income) > 1000000;
```

**Output:**

![image](https://github.com/user-attachments/assets/611c9537-4c75-4e57-9f06-e5883d708307)


## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
