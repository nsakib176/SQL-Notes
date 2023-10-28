Is these 3 types of statements:
1. [Create Table Statements] (#create-table-statement)
2. [Alter Table Statements] (#alter-table-statement)
3. [Drop Table Statement] (#drop-table-statement)

They are described below with Examples.
# Create Table Statement
The `CREATE TABLE` statement in SQL is used to define and create a new table within a database. This statement specifies the table's name, its columns, and the data types for each column. Additionally, you can specify constraints on the columns to enforce data integrity rules. Here's the basic syntax for the `CREATE TABLE` statement:

```sql
CREATE TABLE table_name (
    column1 data_type [constraint1],
    column2 data_type [constraint2],
    ...
);
```

Let's go through an example to illustrate how to create a table:

```sql
CREATE TABLE Students (
    student_id INT PRIMARY KEY,
    first_name VARCHAR(50),
    last_name VARCHAR(50),
    date_of_birth DATE,
    email VARCHAR(100) UNIQUE,
    enrollment_date DATE NOT NULL
);
```

In this example:

- `Students` is the name of the table being created.
- `student_id` is a column of type `INT` and is specified as the primary key of the table using the `PRIMARY KEY` constraint. This means it will uniquely identify each row in the table.
- `first_name` and `last_name` are columns of type `VARCHAR(50)`, which can store up to 50 characters each.
- `date_of_birth` is a column of type `DATE`, which stores dates.
- `email` is a column of type `VARCHAR(100)` with the `UNIQUE` constraint, ensuring that email addresses are unique within the table.
- `enrollment_date` is a column of type `DATE` with the `NOT NULL` constraint, ensuring that a value is always provided for this column.

Here are some common data types and constraints used in the `CREATE TABLE` statement:

Common Data Types:
- `INT`: Integer data type for whole numbers.
- `VARCHAR(n)`: Variable-length character data type with a maximum length of `n`.
- `DATE`: Data type for storing dates.
- `DECIMAL(p, s)`: Decimal data type with precision `p` and scale `s`.

Common Constraints:
- `PRIMARY KEY`: Enforces uniqueness and identifies a unique key for the table.
- `UNIQUE`: Ensures that values in the column are unique.
- `NOT NULL`: Ensures that the column cannot contain NULL values.
- `CHECK`: Defines a condition that values in the column must satisfy.
- `FOREIGN KEY`: Establishes relationships with other tables.

You can customize the table structure and constraints based on your specific database design and requirements. The `CREATE TABLE` statement is fundamental to creating the structure for storing and organizing data in a relational database.


# Alter Table Statement
The `ALTER TABLE` statement in SQL is used to modify an existing database table. You can use it to add, modify, or delete columns, as well as to add or remove constraints. Here's the general syntax for the `ALTER TABLE` statement:

```sql
ALTER TABLE table_name
[ADD | DROP] [COLUMN] column_name [data_type];
```

Let's go through some common use cases for the `ALTER TABLE` statement with examples:

1. **Add a New Column:**

   To add a new column to an existing table, you can use the `ADD COLUMN` clause:

   ```sql
   ALTER TABLE Employees
   ADD COLUMN birth_date DATE;
   ```

   This statement adds a new column named `birth_date` with the data type `DATE` to the `Employees` table.

2. **Modify an Existing Column:**

   You can use the `ALTER TABLE` statement to modify an existing column's data type or constraints. For example, let's change the data type of the `salary` column from `INT` to `DECIMAL(10, 2)`:

   ```sql
   ALTER TABLE Employees
   MODIFY COLUMN salary DECIMAL(10, 2);
   ```

3. **Rename a Column:**

   You can rename an existing column using the `ALTER TABLE` statement. For example:

   ```sql
   ALTER TABLE Employees
   CHANGE COLUMN old_column_name new_column_name data_type;
   ```

   ```sql
   ALTER TABLE Employees
   CHANGE COLUMN emp_name full_name VARCHAR(100);
   ```

   This statement renames the `emp_name` column to `full_name` and changes its data type to `VARCHAR(100)`.

4. **Drop a Column:**

   To remove a column from a table, you can use the `DROP COLUMN` clause. Be cautious when dropping columns, as it permanently deletes the data in that column.

   ```sql
   ALTER TABLE Employees
   DROP COLUMN birth_date;
   ```

   This statement removes the `birth_date` column from the `Employees` table.

5. **Add Constraints:**

   You can also add constraints using the `ALTER TABLE` statement. For example, to add a `UNIQUE` constraint to the `email` column:

   ```sql
   ALTER TABLE Employees
   ADD CONSTRAINT unique_email UNIQUE (email);
   ```

   This statement enforces that all values in the `email` column must be unique.

6. **Drop Constraints:**

   To remove a constraint from a table, you can use the `ALTER TABLE` statement with the `DROP CONSTRAINT` clause. For instance, to remove a `UNIQUE` constraint on the `email` column:

   ```sql
   ALTER TABLE Employees
   DROP CONSTRAINT unique_email;
   ```

These are some common use cases for the `ALTER TABLE` statement in SQL. It allows you to make structural changes to your database tables after they have been created, helping you adapt to evolving data requirements.


# Drop Table Statement 

The `DROP TABLE` statement in SQL is used to permanently delete an existing table and all of its data from a database. This action is irreversible and should be used with caution. Here's the basic syntax for the `DROP TABLE` statement:

```sql
DROP TABLE table_name;
```

Let's go through an example to illustrate how to use the `DROP TABLE` statement:

```sql
DROP TABLE Students;
```

In this example, the `DROP TABLE` statement is used to delete the table named "Students." All the data in the "Students" table will be permanently removed, and the table structure will no longer exist in the database.

Please be cautious when using the `DROP TABLE` statement, as it can lead to data loss. It's often a good practice to create backups of your data before executing such a command, especially in a production environment.