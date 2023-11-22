Database normalization is a process used in database design to organize tables and their relationships in a way that reduces redundancy and dependency. The normalization process helps improve data integrity and avoid anomalies during data manipulation. There are several normal forms (1NF, 2NF, 3NF, BCNF, 4NF, 5NF), each addressing specific issues related to data organization. Let's focus on the first three normal forms with examples:

### 1. First Normal Form (1NF):

A table is in 1NF if it contains only atomic (indivisible) values and there are no repeating groups or arrays.

**Example:**

Consider the following table that violates 1NF:

```
| Student_ID | Courses                       |
|------------|-------------------------------|
| 1          | Math, Physics                 |
| 2          | Chemistry, Biology            |
| 3          | Math, Chemistry, Physics      |
```

SELECT 
To bring it to 1NF, we create a separate table for courses:

```
| Student_ID | Course    |
|------------|-----------|
| 1          | Math      |
| 1          | Physics   |
| 2          | Chemistry |
| 2          | Biology   |
| 3          | Math      |
| 3          | Chemistry |
| 3          | Physics   |
```

### 2. Second Normal Form (2NF):

A table is in 2NF if it is in 1NF and all non-key attributes are fully functionally dependent on the primary key.

**Example:**

Consider the following table:

```
| Student_ID | Course    | Professor    |
|------------|-----------|--------------|
| 1          | Math      | Dr. Smith    |
| 1          | Physics   | Dr. Johnson  |
| 2          | Chemistry | Dr. Anderson |
| 2          | Biology   | Dr. Williams |
| 3          | Math      | Dr. Smith    |
| 3          | Chemistry | Dr. Anderson |
| 3          | Physics   | Dr. Johnson  |
```

The primary key is (Student_ID, Course). However, the professor is functionally dependent only on the course, not on the entire primary key. To bring it to 2NF, we split the table into two:

Table 1: StudentCourses

```
| Student_ID | Course    |
|------------|-----------|
| 1          | Math      |
| 1          | Physics   |
| 2          | Chemistry |
| 2          | Biology   |
| 3          | Math      |
| 3          | Chemistry |
| 3          | Physics   |
```

Table 2: CourseProfessors

```
| Course    | Professor    |
|-----------|--------------|
| Math      | Dr. Smith    |
| Physics   | Dr. Johnson  |
| Chemistry | Dr. Anderson |
| Biology   | Dr. Williams |
```

### 3. Third Normal Form (3NF):

A table is in 3NF if it is in 2NF and all attributes are functionally dependent only on the primary key (no transitive dependencies).

**Example:**

Consider the following table:

```
| Student_ID | Course    | Professor    | Professor_Office |
|------------|-----------|--------------|-------------------|
| 1          | Math      | Dr. Smith    | Room 101          |
| 1          | Physics   | Dr. Johnson  | Room 102          |
| 2          | Chemistry | Dr. Anderson | Room 103          |
| 2          | Biology   | Dr. Williams | Room 104          |
| 3          | Math      | Dr. Smith    | Room 101          |
| 3          | Chemistry | Dr. Johnson  | Room 103          |
| 3          | Physics   | Dr. Anderson | Room 102          |
```

Here, the Professor_Office is dependent on the Professor, which is not directly dependent on the primary key. To bring it to 3NF, we split the table:

Table 1: StudentCourses

```
| Student_ID | Course    |
|------------|-----------|
| 1          | Math      |
| 1          | Physics   |
| 2          | Chemistry |
| 2          | Biology   |
| 3          | Math      |
| 3          | Chemistry |
| 3          | Physics   |
```

Table 2: CourseProfessors

```
| Course    | Professor    |
|-----------|--------------|
| Math      | Dr. Smith    |
| Physics   | Dr. Johnson  |
| Chemistry | Dr. Anderson |
| Biology   | Dr. Williams |
```

Table 3: ProfessorOffices

```
| Professor    | Professor_Office |
|--------------|-------------------|
| Dr. Smith    | Room 101          |
| Dr. Johnson  | Room 102          |
| Dr. Anderson | Room 103          |
| Dr. Williams | Room 104          |
```

These are just examples to illustrate the concepts of 1NF, 2NF, and 3NF. In practice, normalization is a crucial part of

 database design to ensure data consistency, reduce redundancy, and avoid anomalies during data manipulation. The level of normalization depends on the specific requirements of the database and the relationships between entities.