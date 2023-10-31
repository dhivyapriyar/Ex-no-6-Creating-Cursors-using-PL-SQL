# Ex. No: 5 Creating Cursors using PL/SQL

### AIM: 

To create a cursor using PL/SQL.

### Steps:

1. Create employee table with following attributes (empid NUMBER, empname VARCHAR(10), dept VARCHAR(10),salary NUMBER);

2. Create a cursor named as employee_cursor

3. Using cursor read each record and display the result

4. Close the cursor

### Program:

### Create employee table
```
create table EMPLOYEE3 (empid NUMBER, name CHAR(40), dept CHAR(30),salary NUMBER);

```

### PLSQL Cursor code
```

SET SERVEROUTPUT ON;
DECLARE
CURSOR employee_cursor IS
SELECT * FROM employee;
empid NUMBER;
name CHAR(40);
dept CHAR(30);
salary NUMBER;
BEGIN
OPEN employee_cursor;
LOOP
FETCH employee_cursor INTO empid, name, dept, salary;
EXIT WHEN employee_cursor%NOTFOUND;
 
DBMS_OUTPUT.PUT_LINE('Employee ID: ' || empid);
DBMS_OUTPUT.PUT_LINE('Employee Name: ' || name);
DBMS_OUTPUT.PUT_LINE('Department: ' || dept);
DBMS_OUTPUT.PUT_LINE('Salary: ' || salary);
DBMS_OUTPUT.PUT_LINE('--------------------------');
END LOOP;
CLOSE employee_cursor;
END;
/

### Output:

### Result:
