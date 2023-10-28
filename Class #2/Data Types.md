The Common data types of SQL are given below in a chart.

| Data Type                  | Explanation                               | Example                             |
|----------------------------|-------------------------------------------|-------------------------------------|
| INTEGER or INT             | Whole numbers (positive or negative)      | `employee_id INT, age INT`         |
| SMALLINT                   | Smaller whole numbers                     | `book_id SMALLINT, pages SMALLINT` |
| BIGINT                     | Very large whole numbers                  | `customer_id BIGINT, total_purchase_amount BIGINT` |
| NUMERIC or DECIMAL(p, s)   | Fixed-point numbers with precision and scale | `product_id INT, price DECIMAL(10, 2)` |
| FLOAT(p)                   | Approximate numeric values with precision | `item_id INT, weight FLOAT(5)`     |
| REAL                       | Single-precision floating-point numbers   | `sensor_id INT, temperature REAL`  |
| DOUBLE PRECISION or DOUBLE | Double-precision floating-point numbers   | `value1 DOUBLE, value2 DOUBLE`    |
| CHAR(n)                    | Fixed-length character strings             | `first_name CHAR(50), state CHAR(2)` |
| VARCHAR(n)                 | Variable-length character strings          | `last_name VARCHAR(100), city VARCHAR(50)` |
| TEXT                       | Variable-length character strings (long)   | `description TEXT, comments TEXT`  |
| DATE                       | Date values                               | `order_date DATE, birth_date DATE` |
| TIME                       | Time values                               | `start_time TIME, end_time TIME`   |
| TIMESTAMP                  | Date and time values                      | `created_at TIMESTAMP, updated_at TIMESTAMP` |
| BOOLEAN                    | Represents true, false, or unknown        | `is_active BOOLEAN, is_published BOOLEAN` |
| BINARY(n)                  | Fixed-length binary data                  | `image_data BINARY(1024), binary_file BINARY(4096)` |
| VARBINARY(n)               | Variable-length binary data               | `thumbnail VARBINARY(512), file_data VARBINARY(8192)` |
| BLOB                       | Binary large objects (for large binary data) | `document BLOB, profile_picture BLOB` |

Keep in mind that the specific data types and their capabilities may vary depending on the database system you are using. This chart provides a general overview of common data types in SQL.