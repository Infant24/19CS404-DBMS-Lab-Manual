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
--
<img width="889" height="280" alt="image" src="https://github.com/user-attachments/assets/b6355d46-96f0-43df-bbc6-40653e7624ff" />


```
insert into Employee (EmployeeID, Name, Position, Department, Salary)
values (001, 'Sarah Parker', 'Manager', 'HR', 60000);
```

**Output:**

<img width="873" height="338" alt="image" src="https://github.com/user-attachments/assets/ea3cf373-ea7e-43b3-b7f9-d090f232dfe3" />

**Question 2**
---
<img width="861" height="467" alt="image" src="https://github.com/user-attachments/assets/560639f0-0f90-48bb-9e12-bf5c8706568e" />


```
create table item(item_id TEXT PRIMARY KEY, item_desc TEXT NOT NULL, rate INTEGER NOT NULL, icom_id TEXT(4), FOREIGN KEY (icom_id) REFERENCES company(com_id) 
ON UPDATE SET NULL
ON DELETE SET NULL);
```

**Output:**

<img width="865" height="422" alt="image" src="https://github.com/user-attachments/assets/ad26bcd9-e286-44c6-beac-a934253c4ebe" />


**Question 3**
---
<img width="869" height="450" alt="image" src="https://github.com/user-attachments/assets/cedf6bd7-d51f-439c-827c-790f013d6f70" />


```
create table Tasks(TaskID INTEGER, TaskName TEXT, DueDate DATE);
```

**Output:**

<img width="873" height="458" alt="image" src="https://github.com/user-attachments/assets/e9a52ef3-723c-40e9-9b9d-8d5e47f40a5f" />

**Question 4**
---
<img width="861" height="341" alt="image" src="https://github.com/user-attachments/assets/bf1dc638-8755-432b-9462-70eaab3a5888" />

```
CREATE TABLE Orders(OrderID INTEGER PRIMARY KEY, OrederDate DATE NOT NULL, cUSTOMERID INTEGER, FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID));
```

**Output:**

<img width="868" height="424" alt="image" src="https://github.com/user-attachments/assets/5d048f19-49d7-4144-a254-d50195e30bc8" />

**Question 5**
---
<img width="868" height="382" alt="image" src="https://github.com/user-attachments/assets/7f501529-3bfd-44e9-beee-9f999e87b51f" />


```
INSERT INTO Products(ProductID, ProductName, Price, Stock)
SELECT ProductID, ProductName, Price, Stock
FROM Discontinued_products;
```

**Output:**

<img width="867" height="313" alt="image" src="https://github.com/user-attachments/assets/671ce47b-6f6c-416b-aa49-2681f8705bc9" />

**Question 6**
---
<img width="868" height="436" alt="image" src="https://github.com/user-attachments/assets/f562b0d0-2b15-4207-9ea7-ab49b32e9e70" />

```
ALTER TABLE student_details ADD
ParentsNumber number;
ALTER TABLE student_details ADD
Adhar_Number number;
```

**Output:**
<img width="877" height="432" alt="image" src="https://github.com/user-attachments/assets/33223c3c-cfaa-42f9-a5c6-e31556236c0e" />


**Question 7**
---
<img width="872" height="387" alt="image" src="https://github.com/user-attachments/assets/c959034b-69fd-41a5-850f-c96fdbeea43c" />


```
ALTER TABLE Student_details
ADD email TEXT NOT NULL DEFAULT 
'Invalid';
```

**Output:**

<img width="865" height="290" alt="image" src="https://github.com/user-attachments/assets/4bc803b0-3f6c-426c-9026-5e83d80bcc97" />


**Question 8**
---
<img width="876" height="380" alt="image" src="https://github.com/user-attachments/assets/60ad30bf-2290-4a5c-95a5-ddd89724656e" />


```
CREATE TABLE Products(ProductID INTEGER PRIMARY KEY, ProductName TEXT NOT NULL, Price REAL CHECK (Price>0), Stock INTEGER CHECK (Stock>=0));
```

**Output:**

<img width="865" height="343" alt="image" src="https://github.com/user-attachments/assets/37a7d3cc-cedc-43ce-a659-8ba0706686e3" />

**Question 9**
---
<img width="879" height="536" alt="image" src="https://github.com/user-attachments/assets/dca896ef-c81f-4c39-9e0e-9a3bf3622025" />

```
```

**Output:**


**Question 10**
---
<img width="857" height="439" alt="image" src="https://github.com/user-attachments/assets/c2845ea4-7499-4925-a9f5-e93263c31a2f" />


```
CREATE TABLE Bonuses(BonusID INTEGER PRIMARY KEY, EmployeeID INTEGER, BonusAmount REAL CHECK (BonusAmount>0), BonusDate DATE, Reason TEXT NOT NULL, FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID));
```

**Output:**

<img width="875" height="323" alt="image" src="https://github.com/user-attachments/assets/039734fa-995a-488c-ae31-b78fc6eb3f10" />

## RESULT:

Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
