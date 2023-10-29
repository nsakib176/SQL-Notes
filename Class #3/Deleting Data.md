
The `DELETE` SQL query is used to remove rows from a database table. It allows you to specify a condition to determine which rows should be deleted. Here's the basic syntax for the `DELETE` query:

```sql
DELETE FROM table_name
WHERE condition;
```

- `table_name`: The name of the table from which you want to delete rows.
- `WHERE condition`: An optional condition that specifies which rows should be deleted. If omitted, all rows in the table will be deleted.

Let's go through some examples to illustrate how to use the `DELETE` query:

**Example 1: Deleting a Single Row**

Suppose you want to delete a specific student's record from the "Students" table based on their `student_id`:

```sql
DELETE FROM Students
WHERE student_id = 1;
```

This query will remove the student with `student_id` equal to 1 from the "Students" table.

**Example 2: Deleting Multiple Rows**

You can delete multiple rows that meet a certain condition using the `WHERE` clause. For instance, you want to remove all students who haven't enrolled in the current year (2023):

```sql
DELETE FROM Students
WHERE enrollment_date < '2023-01-01';
```

This query deletes all student records where the enrollment date is earlier than January 1, 2023.

**Example 3: Deleting All Rows**

If you omit the `WHERE` clause, the `DELETE` query will remove all rows in the table, effectively truncating the table. Be very cautious when using this, especially in a production environment, as it results in data loss.

```sql
DELETE FROM Orders;
```

This query removes all rows from the "Orders" table.

**Example 4: Deleting Rows from Related Tables**

You can use `DELETE` with a subquery to delete rows from one table based on information in another table. For example, you might delete all orders associated with a specific customer:

```sql
DELETE FROM Orders
WHERE customer_id = (SELECT customer_id FROM Customers WHERE customer_name = 'John Doe');
```

This query removes all orders associated with the customer whose name is "John Doe" from the "Orders" table.

Before executing a `DELETE` query, it's crucial to ensure that the condition is specified correctly to avoid unintended data loss. Always make a backup of your data before deleting records, especially in a production environment.