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
Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

```sql
UPDATE Products SET product_name = 'Premium Bread'
WHERE product_id = 5;
```

**Output:**

![Screenshot 2025-05-05 134254](https://github.com/user-attachments/assets/20398f14-d470-40ef-a258-f6fd7c55a309)


**Question 2**
---
Write a SQL statement to Update the per_unit_price to 25 and total_price accordingly in purchases table where purchase_date is '2022-08-15' and product_id is 12.

```sql
UPDATE purchases 
SET per_unit_price = 25,
total_price = quantity *25
WHERE purchase_date='2022-08-15' AND product_id = 12;
```

**Output:**

![Screenshot 2025-05-05 134354](https://github.com/user-attachments/assets/3b6e6da6-1945-451b-a2b4-cf46fff7c790)

**Question 3**
---
Update the 'Selling_Price' to add 10% extra margin for all products supplied by the supplier with id 6.

PRODUCTS TABLE

name               type
-----------------  ---------------
product_id         INT
product_name       VARCHAR(100)
category           VARCHAR(50)
cost_price         DECIMAL(10,2)
sell_price         DECIMAL(10,2)
reorder_lvl        INT
quantity           INT
supplier_id        INT

```sql
UPDATE Products 
SET sell_price = sell_price+ (sell_price*0.10) 
WHERE supplier_id=6;
```

**Output:**

![Screenshot 2025-05-05 134448](https://github.com/user-attachments/assets/78afa96a-525f-48e8-bfe0-e65ebf9747ff)


**Question 4**
---
Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.
```sql

UPDATE Employees
SET hire_date = '2024-01-24'
WHERE department_id = 50 ;

 
```

**Output:**

![Screenshot 2025-05-05 134613](https://github.com/user-attachments/assets/47b76f5c-8da1-4415-aa53-2ef8d58169f8)


**Question 5**
---
Write a SQL query to Delete a Specific Surgery whose ID is 3

Sample table: Surgeries

```sql
DELETE FROM Surgeries
WHERE surgery_id = 3;
```

**Output:**
![Screenshot 2025-05-05 134656](https://github.com/user-attachments/assets/8c365f49-5f2a-4ba4-9d08-a98e5d707b93)


**Question 6**
---
Write a SQL query to remove rows from the table 'customer' with the following condition -

1. 'cust_city' should begin with the letter 'L',

Sample table: Customer

```sql
DELETE FROM customer
WHERE cust_city LIKE'L%';
```

**Output:**

![Screenshot 2025-05-05 134751](https://github.com/user-attachments/assets/90685ca8-94d1-40fa-a704-142980569c45)


**Question 7**
---Write a SQL query to delete a doctor from Doctors table whose Specialization is 'Pediatrics' and First name is 'Michael'.

Sample table: Doctors

```sql
DELETE FROM Doctors
WHERE
specialization ='Pediatrics'AND first_name = 'Michael';
```

**Output:**

![Screenshot 2025-05-05 134855](https://github.com/user-attachments/assets/eb912cfb-1793-4442-a32d-ea7e7bd1c655)


**Question 8**
---
Write a SQL query to Select all patients whose name starts with A.

Table: Patients

name                  type
--------------------  ----------
patient_id            INT
first_name            VARCHAR(50)
last_name             VARCHAR(50)
date_of_birth         DATE
admission_date        DATE
discharge_date        DATE
doctor_id             INT
```sql
SELECT * FROM Patients
WHERE first_name LIKE 'A%';
```

**Output:**
![Screenshot 2025-05-05 134943](https://github.com/user-attachments/assets/e8ff2a4c-ccff-4930-b248-fc1948b58e7c)


**Question 9**
---
Write a SQL query to categorize decimal as 'High', 'Medium', or 'Low' based on whether it is greater than 100, between 50 and 100, or less than 50 in the Calculations table

cid         name        type        notnull     dflt_value  pk
----------  ----------  ----------  ----------  ----------  ----------
0           id          INTEGER     0                       1
1           value1      REAL        0                       0
2           value2      REAL        0                       0
3           base        INTEGER     0                       0
4           exponent    INTEGER     0                       0
5           number      REAL        0                       0
6           decimal     REAL        0                       0
 

```sql
SELECT id,decimal,
case
    when decimal> 100 then 'High'
    when decimal BETWEEN 50 and 100  then 'Medium'
    ELSE 'Low'
    END AS category
    from Calculations;
```

**Output:**

![Screenshot 2025-05-05 135106](https://github.com/user-attachments/assets/1574f25a-e70f-4e83-8a8e-96642deee2b5)


**Question 10**
---
Write a SQL query to find customers who are either from the city 'New York' or who have a grade greater than 200. Return customer_id, cust_name, city, grade, and salesman_id.

Sample table: customer

 customer_id |   cust_name    |    city    | grade | salesman_id 
-------------+----------------+------------+-------+-------------
        3002 | Nick Rimando   | New York   |   100 |        5001
        3007 | Brad Davis     | New York   |   200 |        5001
        3005 | Graham Zusi    | California |   200 |        5002

```sql
SELECT customer_id, cust_name, city, grade,salesman_id FROM customer
WHERE City = 'New York' OR GRADE >200;
```

**Output:**

![Screenshot 2025-05-05 135204](https://github.com/user-attachments/assets/463194d8-3515-477e-87f1-89af39df6737)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
