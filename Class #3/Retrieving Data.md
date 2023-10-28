In SQL, the `SELECT` statement is used to retrieve data from a database table. It allows you to specify which columns and rows of data you want to retrieve. Here's the basic syntax for the `SELECT` statement:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

Let's go through some examples to explain how to use the `SELECT` statement:

**Example 1: Retrieving All Columns from a Table**

To retrieve all columns from a table, you can use an asterisk (*) as a wildcard:

```sql
SELECT * FROM Employees;
```

This query will retrieve all rows and all columns from the "Employees" table.

**Example 2: Retrieving Specific Columns**

You can specify the columns you want to retrieve:

```sql
SELECT first_name, last_name FROM Students;
```

This query retrieves only the "first_name" and "last_name" columns from the "Students" table.

**Example 3: Adding a WHERE Clause for Filtering**

You can use the `WHERE` clause to filter rows based on a condition:

```sql
SELECT product_name, price
FROM Products
WHERE price < 50;
```

This query retrieves the "product_name" and "price" columns for products where the price is less than 50.

**Example 4: Using Aggregate Functions**

You can use aggregate functions like `SUM`, `COUNT`, `AVG`, etc., to perform calculations on columns:

```sql
SELECT AVG(salary) as avg_salary
FROM Employees
WHERE department = 'Sales';
```

This query calculates and retrieves the average salary of employees in the "Sales" department.

**Example 5: Sorting Results with ORDER BY**

You can use the `ORDER BY` clause to sort the results:

```sql
SELECT first_name, last_name, birth_date
FROM Customers
ORDER BY last_name ASC;
```

This query retrieves customer names and birth dates from the "Customers" table, sorted in ascending order by last name.

**Example 6: Limiting the Number of Rows with LIMIT (or FETCH FIRST)**

To limit the number of rows returned, you can use the `LIMIT` clause:

```sql
SELECT * FROM Orders
LIMIT 10;
```

This query retrieves the first 10 rows from the "Orders" table.

**Example 7: Joining Tables**

You can use the `SELECT` statement to retrieve data from multiple tables using `JOIN` operations:

```sql
SELECT Customers.customer_name, Orders.order_date
FROM Customers
JOIN Orders ON Customers.customer_id = Orders.customer_id;
```

This query retrieves customer names and order dates by joining the "Customers" and "Orders" tables on the "customer_id" column.

These are just a few examples of how the `SELECT` statement can be used to retrieve data from a database. SQL provides a rich set of capabilities to filter, sort, aggregate, and join data to retrieve the information you need.