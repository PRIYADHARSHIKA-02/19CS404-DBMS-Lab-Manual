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
Create a table named Invoices with the following constraints:

InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
DueDate as DATE should be greater than the InvoiceDate.
Amount as REAL should be greater than 0.

```sql
CREATE TABLE Invoices(
InvoiceID INTEGER PRIMARY KEY,
InvoiceDate DATE,
DueDate DATE CHECK(DueDate >InvoiceDate),
Amount REAL CHECK (Amount > 0)
)
```

**Output:**
![Screenshot 2025-04-28 144215](https://github.com/user-attachments/assets/160a25e6-61cc-4476-aadf-9c604367bfc6)


**Question 2**
---
Write an SQL command can to add a column named email of type TEXT to the customers table

```sql
ALTER TABLE Customers ADD COLUMN email TEXT;
```

**Output:**

![Screenshot 2025-04-28 144448](https://github.com/user-attachments/assets/196ac254-4e63-4871-8c1b-650dfbddfe48)


**Question 3**
---
Create a table named Reviews with the following columns:

ReviewID as INTEGER
ProductID as INTEGER
Rating as REAL
ReviewText as TEXT

```sql
CREATE TABLE Reviews(
ReviewID INTEGER,
ProductID INTEGER,
Rating REAL,
ReviewText TEXT
);
```

**Output:**

![Screenshot 2025-04-28 144655](https://github.com/user-attachments/assets/239db912-cbe0-4793-8fad-63e105d73003)


**Question 4**
---
Insert the below data into the Student_details table, allowing the Subject and MARKS columns to take their default values.

```sql
INSERT INTO Student_details(RollNo, Name, Gender)
VALUES(204,'Samuel Black','M');
```

**Output:**

![Screenshot 2025-05-05 132850](https://github.com/user-attachments/assets/7e7fb804-af68-4bc2-902a-6acb58000463)


**Question 5**
---Write an SQL Query to add the attributes designation, net_salary, and dob to the Companies table with the following data types:
designation as VARCHAR(50)
net_salary as NUMBER
dob as DATE

```sql
ALTER TABLE Companies ADD COLUMN designation  varchar(50);
ALTER TABLE Companies ADD COLUMN net_salary  number;
ALTER TABLE Companies ADD COLUMN dob  date;
```

**Output:**
![Screenshot 2025-05-05 133025](https://github.com/user-attachments/assets/9340132f-fc02-4f67-945d-2d5c7ad0bf73)


**Question 6**
---
Create a table named Shipments with the following constraints:
ShipmentID as INTEGER should be the primary key.
ShipmentDate as DATE.
SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).

```sql
CREATE TABLE Shipments(
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY(SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)

);
```

**Output:**

![Screenshot 2025-05-05 133153](https://github.com/user-attachments/assets/77f8e7de-ce3f-4d43-862e-5d24244f4a4e)


**Question 7**
---
Create a table named Department with the following constraints:
DepartmentID as INTEGER should be the primary key.
DepartmentName as TEXT should be unique and not NULL.
Location as TEXT.

```sql
CREATE TABLE Department(
DepartmentID INTEGER PRIMARY KEY,
DepartmentName TEXT UNIQUE NOT NULL,
Location TEXT
);

```

**Output:**

![Screenshot 2025-05-05 133333](https://github.com/user-attachments/assets/0451ce42-362c-470b-9799-5935ab7cb312)

**Question 8**
---
Write an SQL Query to add the attributes designation, net_salary, and dob to the Companies table with the following data types:
designation as VARCHAR(50)
net_salary as NUMBER
dob as DATE

```sql
ALTER TABLE Companies ADD COLUMN designation  varchar(50);
ALTER TABLE Companies ADD COLUMN net_salary  number;
ALTER TABLE Companies ADD COLUMN dob  date;
```

**Output:**

![Screenshot 2025-05-05 133714](https://github.com/user-attachments/assets/3ae86a8c-d6c0-4d7f-9001-98e06bf91001)


**Question 9**
---
Create a table named Orders with the following columns:

OrderID as INTEGER
OrderDate as TEXT
CustomerID as INTEGER

```sql
CREATE TABLE Orders(
OrderID INTEGER,
OrderDate TEXT,
CustomerID INTEGER
);
```

**Output:**

![111](https://github.com/user-attachments/assets/340f2aae-8265-482b-b065-2341c0a75c43)


**Question 10**
---
Create a table named Products with the following constraints:
ProductID as INTEGER should be the primary key.
ProductName as TEXT should be unique and not NULL.
Price as REAL should be greater than 0.
StockQuantity as INTEGER should be non-negative.

```sqlCREATE TABLE Products(
ProductID INTEGER PRIMARY KEY,
ProductName TEXT UNIQUE NOT NULL,
Price REAL CHECK(Price>1),
StockQuantity INTEGER CHECK(StockQuantity>=1)
);
```

**Output:**

![Uploading 122.jpg…]()



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
