# Experiment 7: PL/SQL – Variables, Control Structures and Loops

## AIM
To write and execute simple PL/SQL programs using variables, loops, and conditional statements.


## THEORY

PL/SQL, which stands for Procedural Language extensions to the Structured Query Language (SQL). It is a combination of SQL along with the procedural features of programming languages.

**Syntax:**
```sql
DECLARE 
   <declarations section> 
BEGIN 
   <executable command(s)>
EXCEPTION 
   <exception handling> 
END;
```

### Basic Components of PL/SQL Block:
- DECLARE: Section to declare variables and constants.
- BEGIN: The execution section that contains PL/SQL statements.
- EXCEPTION: Handles errors or exceptions that occur in the program.
- END: Marks the end of the PL/SQL block.

# PL/SQL Programs – Steps and Expected Output

## 1. Write a PL/SQL program to find the Greatest of Two Numbers

### Steps:
- Declare two numeric variables and initialize them.
- Use an `IF` statement to compare the values.
- Display the greater number using `DBMS_OUTPUT.PUT_LINE`.

**CODE**

DECLARE

    num1 NUMBER := 80;
    num2 NUMBER := 45;
BEGIN

    IF num1 > num2 THEN
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num1);
    ELSE
        DBMS_OUTPUT.PUT_LINE('Greater number is: ' || num2);
    END IF;
END;
/

**Expected Output:**  
Greater number is: 80

**OUTPUT**
![Screenshot 2025-05-14 155356](https://github.com/user-attachments/assets/ef1bd3f8-7695-40c2-88ee-7090ca4e0430)

---

## 2. Write a PL/SQL program to Calculate Sum of First N Natural Numbers

### Steps:
- Declare a variable `n` and assign a value (e.g., 10).
- Initialize a `sum` variable to 0.
- Use a `WHILE` loop to iterate from 1 to `n`, adding each number to the sum.
- Display the result using `DBMS_OUTPUT.PUT_LINE`.

**CODE**
DECLARE

    n NUMBER := 10;
    i NUMBER := 1;
    sum NUMBER := 0;
BEGIN

    WHILE i <= n LOOP
        sum := sum + i;
        i := i + 1;
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Sum of first ' || n || ' natural numbers is: ' || sum);
END;
/

**Expected Output:**  
Sum of first 10 natural numbers is: 55

**OUTPUT**
![Screenshot 2025-05-14 155658](https://github.com/user-attachments/assets/7ecdb03c-b602-42b1-8d87-c4260313dd36)

## 3. Write a PL/SQL program to generate Fibonacci series

### Steps:
- Declare the variable `n` to indicate how many terms to generate.
- Initialize the first two Fibonacci numbers (0 and 1).
- Use a loop to generate the next terms using the formula `c = a + b`.
- Print each term in the series.

**CODE**
DECLARE

    n NUMBER := 7;
    a NUMBER := 0;
    b NUMBER := 1;
    c NUMBER;
    i NUMBER := 3; -- starting from the 3rd term
BEGIN

    DBMS_OUTPUT.PUT_LINE('Fibonacci sequence:');
    DBMS_OUTPUT.PUT_LINE(a);
    DBMS_OUTPUT.PUT_LINE(b);

    WHILE i <= n LOOP
        c := a + b;
        DBMS_OUTPUT.PUT_LINE(c);
        a := b;
        b := c;
        i := i + 1;
    END LOOP;
END;
/

**Expected Output:**  
n = 7  
Fibonacci sequence: 0, 1, 1, 2, 3, 5, 8

**OUTPUT**
![Screenshot 2025-05-14 160059](https://github.com/user-attachments/assets/0accb3b1-708d-4e54-9e0c-d33a8e15a04d)
---

## 4. Write a PL/SQL Program to display the number in Reverse Order

### Steps:
- Declare a variable `n` and assign a value (e.g., 1535).
- Use a loop to extract each digit using modulo and reverse the number.
- Display the reversed number.

**CODE**
DECLARE

    n NUMBER := 1535;
    rem NUMBER;
    rev NUMBER := 0;
    original NUMBER := 1535;
BEGIN

    WHILE n > 0 LOOP
        rem := MOD(n, 10);       -- Get the last digit
        rev := (rev * 10) + rem; -- Build the reversed number
        n := TRUNC(n / 10);      -- Remove the last digit
    END LOOP;

    DBMS_OUTPUT.PUT_LINE('Reversed number is ' || rev);
END;
/
**Expected Output:**  
n = 1535  
Reversed number is 5351

**OUTPUT**
![Screenshot 2025-05-14 160409](https://github.com/user-attachments/assets/79fa98c6-725e-485e-8b26-67585ec8fe7f)
---

## 5. Write a PL/SQL program to find the largest of three numbers

### Steps:
- Declare three numeric variables `a`, `b`, and `c`.
- Use nested `IF-ELSIF-ELSE` conditions to find the largest among the three.
- Display the largest number.
**CODE**
  
DECLARE

    a NUMBER := 10;
    b NUMBER := 9;
    c NUMBER := 15;
    largest NUMBER;
BEGIN

    IF a >= b AND a >= c THEN
        largest := a;
    ELSIF b >= a AND b >= c THEN
        largest := b;
    ELSE
        largest := c;
    END IF;
  
    DBMS_OUTPUT.PUT_LINE('Largest of three number is ' || largest);
END;

**Expected Output:**  
a = 10, b = 9, c = 15  
Largest of three number is 15

**OUTPUT**
![Screenshot 2025-05-14 160538](https://github.com/user-attachments/assets/e7c2b732-3c3d-4fe8-abcd-8ce3f85de7ae)


## RESULT
Thus, the PL/SQL programs using variables, conditionals, and loops were executed successfully.
