\# SLABS - Fundamentals of Database Design \& Information Systems

\## Class Activity 3 - Software Analysis and PostgreSQL DML



\*\*Student:\*\* \[Agnes Langa]

\*\*Date:\*\* 26-10-2026



\---



\### 2. Software \& Operating Systems Analysis



\*\*1. Vertical vs. Horizontal Software\*\*



\*\*Vertical Package (Industry-Specific):\*\*

Example: Pastel Accounting or SAP Retail Module used in supermarkets like Shoprite.

A Vertical package is built for ONE specific industry. It has features only that industry needs.



\*\*Horizontal Package (General Purpose):\*\*

Example: Microsoft Office 365 (Word, Excel) or Microsoft Excel.

A Horizontal package can be used by ANY business type - a school, a hospital, or a retail store.



\*\*How they differ in scope:\*\*

Vertical software has a narrow scope (deep features for one industry). Horizontal software has a wide scope (basic features for all industries).



\*\*2. Operating System Modes: Batch Processing vs. Real-Time Processing\*\*



\*\*Batch Processing:\*\*

Data is collected over time and processed all at once as a batch, without immediate user interaction.

\*Business Scenario:\* A bank processing all daily transactions at night to calculate interest, or a payroll system processing all employee salaries at month-end. Used in your Stock Controller background - processing stock counts at end of day.



\*\*Real-Time Processing:\*\*

Data is processed instantly as it happens, with immediate response.

\*Business Scenario:\* An ATM withdrawal, a Point of Sale (POS) system at a cashier till, or booking a flight online. As a cashier, when you scan an item, the price shows immediately - that is Real-Time.



\---



\### 3. PostgreSQL DML Practical Exercise



\*\*Database Created: company\_db\*\*



Commands used in Git Bash:



psql -U postgres

CREATE DATABASE company\_db;

\\c company\_db



\*\*Create employees table:\*\*



CREATE TABLE employees (

&#x20;   id SERIAL PRIMARY KEY,

&#x20;   name VARCHAR(100),

&#x20;   department VARCHAR(100),

&#x20;   salary INT

);



\*\*Insert Records (3 new employees):\*\*



INSERT INTO employees (name, department, salary) VALUES ('Thabo Mbeki', 'Logistics', 18000);

INSERT INTO employees (name, department, salary) VALUES ('Lerato Dlamini', 'Sales', 22000);

INSERT INTO employees (name, department, salary) VALUES ('James Nkosi', 'IT', 25000);



\*\*Query Records (salary above threshold):\*\*

\-- Get all employees whose salary is above 20000



SELECT \* FROM employees WHERE salary > 20000;



Output Example:

&#x20;id |      name       | department | salary

\----+-----------------+------------+--------

&#x20; 2 | Lerato Dlamini  | Sales      | 22000

&#x20; 3 | James Nkosi     | IT         | 25000



\*\*Update \& Delete:\*\*



\-- Update one employee's salary using their ID

UPDATE employees SET salary = 20000 WHERE id = 1;



\-- Delete another employee record

DELETE FROM employees WHERE id = 2;



\-- Final check

SELECT \* FROM employees;

