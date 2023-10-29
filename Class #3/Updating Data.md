
The `UPDATE` SQL query is used to modify existing records in a database table. It allows you to change the values of one or more columns in existing rows that meet a specified condition. Here's the basic syntax for the `UPDATE` query:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

- `table_name`: The name of the table you want to update.
- `column1`, `column2`, ...: The columns you want to update and the new values you want to assign.
- `value1`, `value2`, ...: The new values to set for the specified columns.
- `WHERE condition`: An optional condition that determines which rows should be updated. If omitted, all rows in the table will be updated.

Let's go through some examples to illustrate how to use the `UPDATE` query:

**Example 1: Updating a Single Row**

Suppose you want to update the email address of a specific student in the "Students" table:

```sql
UPDATE Students
SET email = 'new.email@example.com'
WHERE student_id = 1;
```

This query will update the email address for the student with `student_id` equal to 1.

**Example 2: Updating Multiple Rows**

To update multiple rows that meet a certain condition, you can use the `WHERE` clause. For instance, you want to increase the salary of all employees in the "Employees" table who work in the "Marketing" department:

```sql
UPDATE Employees
SET salary = salary * 1.1
WHERE department = 'Marketing';
```

This query increases the salary of all employees in the "Marketing" department by 10%.

**Example 3: Updating Multiple Columns**

You can update multiple columns in a single query. For instance, you want to change both the first name and last name of a student with `student_id` equal to 2:

```sql
UPDATE Students
SET first_name = 'NewFirstName', last_name = 'NewLastName'
WHERE student_id = 2;
```

This query updates both the first name and last name for the specified student.

**Example 4: Updating All Rows**

If you omit the `WHERE` clause, the `UPDATE` query will modify all rows in the table. Be cautious when doing this to avoid unintended consequences.

```sql
UPDATE Products
SET price = price * 1.05;
```

This query increases the price of all products in the "Products" table by 5%.

Before running an `UPDATE` query, it's essential to ensure that the condition and the columns to be updated are specified correctly, as incorrect queries can result in unintended data modifications. Always make a backup of your data before making significant changes using the `UPDATE` statement, especially in a production environment.