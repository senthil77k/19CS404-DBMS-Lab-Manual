# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
![image](https://github.com/user-attachments/assets/72c52af7-8a89-4d86-ab27-9f764550a2e7)


```sql
alter table Student_details add column State TEXT;
```

**Output:**

![image](https://github.com/user-attachments/assets/6813569b-f42f-491f-8215-7272a3f40e62)

**Question 2**
---
--![image](https://github.com/user-attachments/assets/c9766ce2-4307-4c63-85c7-1484e6802bd4)


```sql
create table Orders(OrderID INTEGER primary key,OrderDate DATE NOT NULL, CustomerID INTEGER, FOREIGN
KEY (CustomerID) references Customers(CustomerID));
```

**Output:**

![image](https://github.com/user-attachments/assets/742d5840-0a59-4ab9-ad0f-8611ce5d2b12)

**Question 3**
---
-- ![image](https://github.com/user-attachments/assets/e218fa2a-8a4b-4b06-98e0-78c4b3654281)


```sql
CREATE table jobs(job_id int primary key,job_title varchar(50) default ' ',min_salary int default 8000 ,max_salary int NULL);
```

**Output:**

![image](https://github.com/user-attachments/assets/4274c9dd-2d2f-4438-9c29-2571076eecf1)

**Question 4**
---
-- ![image](https://github.com/user-attachments/assets/028d15be-2fa5-4e96-8424-2adae73bf337)


```sql
insert into Customers values(1, 'Ramesh',32,'Ahmedabad',2000);
insert into Customers values(2, 'Khilan',25,'Delhi',1500);
insert into Customers values(3, 'Kaushik',23,'Kota',2000);
```

**Output:**

![image](https://github.com/user-attachments/assets/81fa8d68-46e5-452d-916f-330feb75cdbf)

**Question 5**
---
![image](https://github.com/user-attachments/assets/3972652f-4cb5-4391-9a40-b911b1ed4243)


```sql
CREATE table Reviews(ReviewID INTEGER,ProductID INTEGER,Rating REAL, ReviewText TEXT);
```

**Output:**
![image](https://github.com/user-attachments/assets/de3f2e2d-d9e0-4e68-9765-6f7386c6358b)


**Question 6**
---
![image](https://github.com/user-attachments/assets/544d5cec-664a-4b00-9a6d-afcc7080c2a9)

```sql
alter table Student_details add column MobileNumber NUMBER;
alter table Student_details add column Address VARCHAR(100);
```

**Output:**

![image](https://github.com/user-attachments/assets/f842c7cd-f349-40af-89d5-19f7e4dd78b4)

**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/edbd93e5-c709-4959-a57d-e73f8764ce0b)


```sql
-- insert into Student_details values(201,'David Lee','M','Physics',92);
```

**Output:**

![image](https://github.com/user-attachments/assets/a93aff9e-bd3b-4517-bd8d-134728b6ae14)

**Question 8**
---
![image](https://github.com/user-attachments/assets/7196d6dd-6c64-4338-b500-7b7076bf1a8a)

```sql
create table Attendance(AttendanceID INTEGER primary key,EmployeeID INTEGER,AttendanceDate DATE,
Status TEXT CHECK(Status in('Present','Absent','Leave')),FOREIGN KEY (EmployeeID) references Employees(EmployeeID)  );
```

**Output:**

![image](https://github.com/user-attachments/assets/1e57c247-a9bf-4f6f-b0c9-1707e02bae30)

**Question 9**
---
![image](https://github.com/user-attachments/assets/b3a5e9ec-1456-4465-9eb8-07c2487683bb)

```sql
-- insert into Books select * from Out_of_print_books;
```

**Output:**

![image](https://github.com/user-attachments/assets/d842d0d1-162e-483d-9b4f-0037bf51808d)

**Question 10**
---
![image](https://github.com/user-attachments/assets/1eccca95-51c5-4a70-8f02-001f5b4fc603)

```sql
create table ProjectAssignments(AssignmentID INTEGER primary key,EmployeeID INTEGER, ProjectID INTEGER,AssignmentDate DATE NOT NULL,
FOREIGN KEY (EmployeeID) references Employees(EmployeeID),
FOREIGN KEY (ProjectID) references Projects(ProjectID));
```

**Output:**

![image](https://github.com/user-attachments/assets/1a4e253c-1726-451a-bac0-a5d27842c99e)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
