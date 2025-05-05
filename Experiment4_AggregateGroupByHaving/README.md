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
How many medical records does each doctor have?

Sample table:MedicalRecords Table

```sql
select DoctorID,COUNT(*) as TotalRecords
from MedicalRecords
Group by DoctorID
order by DoctorID;
```

**Output:**

![Screenshot 2025-05-05 135541](https://github.com/user-attachments/assets/77f65636-09f3-4529-a17d-26f2d2101d00)


**Question 2**
---
What is the count of male and female patients?

Sample table: Patients Table

```sql
SELECT Gender , COUNT(*) as TotalPatients from Patients
Group by Gender;
```

**Output:**

![Screenshot 2025-05-05 135650](https://github.com/user-attachments/assets/05a6e074-97c2-44a8-a4ba-7dfd3bfd91e4)


**Question 3**
---
How many doctors specialize in each medical specialty?

Sample table:Doctors Table

```sql
select Specialty, COUNT(*) AS TotalDocto from Doctors
group by Specialty;
```

**Output:**
![Screenshot 2025-05-05 135749](https://github.com/user-attachments/assets/12c5ecf6-d31a-43d6-9d8c-3fe40c9b29e9)


**Question 4**
---
Write a SQL query to find the number of employees whose age is greater than 32.

Sample table: employee

```sql
select COUNT(*) as COUNT from employee where age > 32;
```

**Output:**

![Screenshot 2025-05-05 135836](https://github.com/user-attachments/assets/b3816950-cba4-4cc4-bfeb-c05b55f960b3)


**Question 5**
---
Write a SQL query to calculate total purchase amount of all orders. Return total purchase amount.

Sample table: orders

ord_no      purch_amt   ord_date    customer_id  salesman_id

----------  ----------  ----------  -----------  -----------

70001       150.5       2012-10-05  3005         5002

70009       270.65      2012-09-10  3001         5005

70002       65.26       2012-10-05  3002         5001

```sql
SELECT SUM(purch_amt) as TOTAL
from orders;
```

**Output:**

![Screenshot 2025-05-05 135948](https://github.com/user-attachments/assets/8b54b706-5283-41b2-877f-f90201867f9f)


**Question 6**
---
Write a SQL query to find the customer with longest name?

Table: customer

name        type
----------  ----------
id          INTEGER
name        TEXT
city        TEXT
email       TEXT
phone       INTEGER

```sql
SELECT name,LENGTH(name) as length 
from customer
order by length DESC
LIMIT 1;
```

**Output:**

![Screenshot 2025-05-05 140102](https://github.com/user-attachments/assets/45ae22a4-1f89-4ebc-b2d6-7e96d86c5f4e)


**Question 7**
---
Write a SQL query to find the number of employees who are having the same age removing the duplicate values.

Sample table: employee

```sql
SELECT COUNT(DISTINCT age) as COUNT FROM employee;
```

**Output:**

![Screenshot 2025-05-05 140201](https://github.com/user-attachments/assets/25e47e4a-57df-4fb0-b36a-378b743fbcc5)


**Question 8**
---
Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the total salary sum for each group, and excludes groups where the total salary sum is not greater than 5000.

Sample table: customer1

```sql
SELECT (age/5)*5 age_group, SUM(salary) 
from customer1
group by age_group
having SUM(salary)>5000;
```

**Output:**

![Screenshot 2025-05-05 140300](https://github.com/user-attachments/assets/3dae2aef-6f11-40eb-8fb2-6cacc342295c)


**Question 9**
---
Write the SQL query that achieves the grouping of data by age, calculates the minimum income for each age group, and includes only those age groups where the minimum income is less than 400,000.

```sql
SELECT age, MIN(income)
from employee
group by age
having MIN(income)<400000;
```

**Output:**
![Screenshot 2025-05-05 140347](https://github.com/user-attachments/assets/93e19565-7c7d-4f16-bc7b-0f7f7282c30c)


**Question 10**
---
Write the SQL query that accomplishes the selection of product which has lowest price in each category from the "products" table and includes only those products where the minimum price is less than 10.

```sql
SELECT category_id, MIN(price) as Price
from products
group by category_id
having MIN(price) < 10
```

**Output:**

![Screenshot 2025-05-05 140436](https://github.com/user-attachments/assets/2e4981fd-e552-427d-a1ef-d9a798ea1848)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
