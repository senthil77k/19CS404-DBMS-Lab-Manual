# Experiment 3: DML Commands

## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
-- ![image](https://github.com/user-attachments/assets/d3ae6f94-0338-4939-9d49-c95c3e302d1e)


```sql
UPDATE Customer
SET grade = 5
WHERE city = 'Chennai';

```

**Output:**

![image](https://github.com/user-attachments/assets/cd0c3406-c5bc-471b-b5d5-b3477b2dbe35)

**Question 2**
---
![image](https://github.com/user-attachments/assets/122ca041-f9f5-4db9-8671-33959b10dc3a)

```sql
UPDATE Products
SET quantity = quantity * 1.10;

```

**Output:**

![image](https://github.com/user-attachments/assets/45542c91-ee45-4e84-bb35-ca5cec13bdaf)

**Question 3**
---
![image](https://github.com/user-attachments/assets/dc329747-819b-4ba8-9868-dfa6af9da2b1)

```sql
-- UPDATE Products
SET category = 'Household'
WHERE product_name LIKE '%Detergent%';
```

**Output:**

![image](https://github.com/user-attachments/assets/7b519a7c-fe01-4ef7-9f64-9853e108899e)

**Question 4**
---
![image](https://github.com/user-attachments/assets/84d55697-91c5-49a8-86af-c4502d26073a)

```sql
-- UPDATE suppliers
SET supplier_name = UPPER(supplier_name)
WHERE contact_person LIKE '% Singh';

```

**Output:**

![image](https://github.com/user-attachments/assets/543b9b65-352d-429a-b7c0-17cbfa15054b)

**Question 5**
---
![image](https://github.com/user-attachments/assets/43c51949-f3f5-4604-802a-fc3b037b7723)

```sql
UPDATE sales
SET sell_price = sell_price * 1.05
WHERE product_id = 15 AND sale_date = '2023-01-31';

```

**Output:**

![image](https://github.com/user-attachments/assets/911d7e54-53d9-41e7-a184-7ba44c539ba0)

**Question 6**
---
![image](https://github.com/user-attachments/assets/2fa49e84-80d7-4c0b-898e-002fa556bc43)

```sql
DELETE FROM Customer
WHERE GRADE = 3
  AND CUST_NAME LIKE '%BBB%'
  AND PAYMENT_AMT > 2000;
```

**Output:**

![image](https://github.com/user-attachments/assets/71d64dd6-170f-4b7b-b9bc-666ebdddd501)

**Question 7**
---
![image](https://github.com/user-attachments/assets/a7806300-af05-4bd7-8ce7-fb8d4758720c)

```sql
DELETE FROM Customer
WHERE CUST_COUNTRY = 'UK'
  AND WORKING_AREA = 'London'
  AND GRADE < 3;
```

**Output:**

![image](https://github.com/user-attachments/assets/506be834-a24e-46d2-920e-923c2bfbb161)

**Question 8**
---
![image](https://github.com/user-attachments/assets/a549d7d5-6216-4e67-81c3-e08607bc4d18)

```sql
DELETE FROM Customer
WHERE LENGTH(CUST_NAME) = 6;
```

**Output:**

![image](https://github.com/user-attachments/assets/7bcf1616-2d29-4a73-a825-20e94f98f9a8)

**Question 9**
---
![image](https://github.com/user-attachments/assets/1de12681-2c3d-4805-95de-cf2b575af5fa)

```sql
DELETE FROM Customer
WHERE GRADE % 2 = 1;
```

**Output:**

![image](https://github.com/user-attachments/assets/185849a8-5b74-42e7-937c-3b029e2f3b4d)

**Question 10**
---
![image](https://github.com/user-attachments/assets/9a1beadd-c792-45e3-babf-63b84be7b88c)

```sql
DELETE FROM surgeries
WHERE surgery_date = '2024-02-28';
```

**Output:**

![image](https://github.com/user-attachments/assets/ad587c27-eaa0-42ef-ab55-a7cb904ec2f9)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
