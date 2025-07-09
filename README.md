### 📘 Practice Files

* [SQL Practice 1](./practice/SQL1.md)
* [SQL Practice 2](./practice/SQL2.md)
 


 # 🧠 What is DBMS?

**DBMS (Database Management System)** is a software tool that helps in creating, managing, and interacting with databases efficiently. It provides a structured and secure way to store, retrieve, and update data.

---

### 🔍 Why Do We Need DBMS?

Before DBMS, data was stored using flat file systems (like `.txt` or `.csv`). This approach had several problems:

| 🚫 Problem in Flat Files                                                                                | ✅ Solution with DBMS                                                                              |
| ------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Data Redundancy**: Same data stored in multiple places, leading to wastage of space and confusion.    | DBMS **reduces redundancy** by storing data centrally and using relationships (e.g. foreign keys). |
| **Data Inconsistency**: If data is updated in one file but not in another, the data becomes unreliable. | DBMS **ensures consistency** by updating all references to the same data across the system.        |
| No access control or security                                                                           | DBMS allows **role-based access** to secure sensitive data.                                        |
| Difficult to search and manage data manually                                                            | DBMS provides **SQL** for efficient data queries.                                                  |
| No proper backup or recovery mechanism                                                                  | DBMS handles **automatic backups and recovery**.                                                   |

---

### 📌 Key Concepts

#### ✅ **Data Redundancy**

When the same piece of data exists in multiple places.

> Example: If a student's name and course are saved in both "students.txt" and "enrollments.txt", it's redundant.

**DBMS Fix**: It stores the student data once and links it using foreign keys.

---

#### ✅ **Data Consistency**

When the data is the same across the whole system, no matter where it’s accessed.

> Example: If a student's address changes, it should be updated everywhere. Without DBMS, some files might not be updated, leading to inconsistency.

**DBMS Fix**: Updating data in one place reflects everywhere because of relationships and transactions.

# 📘 What is SQL?

**SQL (Structured Query Language)** is a special language used to communicate with **Relational Database Management Systems (RDBMS)** like MySQL, PostgreSQL, and Oracle.

It helps you:

- Ask questions to your database (e.g., “Who are all the students older than 18?”)
- Add, update, and delete data
- Design your data in a structured way
- Set permissions (who can see or change the data)

Think of SQL as a **translator** between you and your database. You ask in SQL, and the database gives you the answer.

---

## 🚀 Features of DBMS (Why We Use It)

Here are the most important features of a DBMS and what real-world problems it solves:

---

### 🔁 1. **Reduces Data Redundancy**

**Problem without DBMS**:
In a flat file system, the same data might be copied in many files (e.g., customer info repeated in multiple places).

**DBMS Fix**:
Centralized storage and relationships (foreign keys) allow storing data only once and referencing it wherever needed.

---

### 🎯 2. **Ensures Data Consistency**

**Problem**:
If one file is updated but the others aren't, data becomes inconsistent (e.g., one file says "Mumbai", another says "Pune").

**DBMS Fix**:
Updates are done in one place and reflected everywhere — ensuring data is always accurate and synchronized.

---

### 🔐 3. **Provides Data Security**

**Problem**:
In traditional file systems, anyone with access can see or change the data.

**DBMS Fix**:
Access control and user permissions prevent unauthorized access. You can allow read-only, edit, or admin-level access.

---

### 💾 4. **Automatic Backup & Recovery**

**Problem**:
If you accidentally delete a file, it’s gone. No backup unless you manually saved one.

**DBMS Fix**:
DBMS supports automated backup, transaction logs, and recovery tools to restore data if something goes wrong.

---

### 🤝 5. **Supports Data Relationships**

**Problem**:
It’s difficult to connect data across different files manually (e.g., linking customers to orders).

**DBMS Fix**:
You can define relationships using keys, like `customer_id`, and easily join tables to get meaningful insights.

---

### 📈 6. **Improved Querying & Reporting**

**Problem**:
Searching through plain text files is slow and manual.

**DBMS Fix**:
SQL lets you filter, sort, group, and analyze data in milliseconds.

---

### ⚙️ 7. **Concurrency Control**

**Problem**:
If two users try to edit the same file at the same time, data may get corrupted.

**DBMS Fix**:
It handles **concurrent access** with locks and transactions, so multiple users can safely use the database at the same time.

---

### 🔄 8. **Data Integrity & Validation**

**Problem**:
In flat files, there’s nothing stopping someone from entering a wrong or invalid value.

**DBMS Fix**:
You can set rules (e.g., age must be a number, ID must be unique), and DBMS enforces them automatically.

---

## 🤔 Could We Do This Without a DBMS?

Yes, we _can_ use:

- Excel sheets
- Flat files like `.txt` or `.csv`
- Hardcoded arrays in code

But here’s why DBMS is better:

| Without DBMS (Flat Files)        | With DBMS                      |
| -------------------------------- | ------------------------------ |
| Hard to manage large data        | Designed for large-scale use   |
| No relationships between data    | Easy joins & links             |
| Manual filtering/searching       | Instant SQL queries            |
| No access control                | Role-based access              |
| Risk of corruption/inconsistency | Safe with ACID properties      |
| No automatic backup              | Has built-in backup & recovery |

---

**Conclusion**:
Using a DBMS with SQL is like moving from paper notebooks to a smart, digital system — it’s faster, safer, and smarter.

# 📘 What is RDBMS?

**RDBMS** stands for **Relational Database Management System**.

It’s a type of DBMS (Database Management System) that stores data in the form of **tables** (also called **relations**). Each table contains **rows** (records) and **columns** (fields).

---

## 🧱 Example to Understand RDBMS

Imagine you have this table:

### 🎬 Table: `Actors`

| ID  | FirstName | LastName  | Gender | NetWorth |
| --- | --------- | --------- | ------ | -------- |
| 1   | Chris     | Evans     | Male   | 450      |
| 2   | Scarlett  | Johansson | Female | 500      |

Each **row** = one actor (record)
Each **column** = type of data (field) like `FirstName`, `NetWorth`

---

## 🧩 Why is it called _Relational_?

Because tables in an RDBMS can be **related** to each other using keys:

- **Primary Key**: Unique ID in a table (like `ID` in `Actors`)
- **Foreign Key**: A field in another table that refers to a primary key

### 🎥 Example:

#### Table: `Movies`

| MovieID | Title       | ActorID |
| ------- | ----------- | ------- |
| 101     | Avengers    | 1       |
| 102     | Black Widow | 2       |

Here, `ActorID` in `Movies` is a **foreign key** that links to the `ID` in the `Actors` table.

This is a **relationship** — that's why it's called a **Relational** DBMS.

---

## 🛠️ Popular RDBMS Examples

- MySQL
- PostgreSQL
- Oracle
- Microsoft SQL Server
- SQLite

---

## ✅ Key Features of RDBMS

| Feature                     | Meaning                                                                   |
| --------------------------- | ------------------------------------------------------------------------- |
| 🔗 **Relationships**        | You can connect tables via keys                                           |
| 🔐 **Data Integrity**       | Enforces rules (e.g., unique ID)                                          |
| 🔄 **Data Consistency**     | Same data across linked tables                                            |
| 🔎 **Query Language (SQL)** | Use SQL to work with data                                                 |
| 🧪 **ACID Properties**      | Ensures safe transactions (Atomicity, Consistency, Isolation, Durability) |

---

## 💡 In Simple Words

> **RDBMS = A smarter, structured system to store and relate data using tables. It makes working with data clean, powerful, and scalable.**

# Normalization

## 📦 Imagine this:

You're storing data in a table about **students** and their **courses**:

| StudentName | CourseName | Teacher    |
| ----------- | ---------- | ---------- |
| Rahul       | Math       | Mr. Sharma |
| Rahul       | Science    | Ms. Mehta  |
| Sneha       | Math       | Mr. Sharma |

This table looks fine now\... but problems will start soon!

---

## ❌ What’s the Problem?

### 1. **Data Redundancy** (Repetition of Data):

- "Rahul" and "Mr. Sharma" appear **multiple times**.
- Wastes space and increases chances of mistakes.

### 2. **Update Anomalies**:

- If Mr. Sharma changes his name, you have to update **every row** where he appears. Miss one? ❌ **Inconsistency!**

### 3. **Insertion Anomaly**:

- You can’t add a new teacher unless a student is enrolled with them.

### 4. **Deletion Anomaly**:

- If Rahul drops Science, you might also lose the record of Ms. Mehta.

---

## ✅ What is Normalization?

> **Normalization** is the process of organizing data into multiple related tables to reduce redundancy and improve data integrity.

---

## 📊 Simple Example: Breaking into 3 tables

### 🔹 Table 1: Students

| StudentID | StudentName |
| --------- | ----------- |
| 1         | Rahul       |
| 2         | Sneha       |

---

### 🔹 Table 2: Courses

| CourseID | CourseName | Teacher    |
| -------- | ---------- | ---------- |
| 101      | Math       | Mr. Sharma |
| 102      | Science    | Ms. Mehta  |

---

### 🔹 Table 3: Enrollments

| StudentID | CourseID |
| --------- | -------- |
| 1         | 101      |
| 1         | 102      |
| 2         | 101      |

---

Now, if a teacher name changes, you **only update in one row** (in Courses table), not everywhere.

---

## 🎯 Why Normalize?

| Benefit            | Explanation                         |
| ------------------ | ----------------------------------- |
| ✅ Less Repetition | Save storage and reduce duplication |
| ✅ More Accurate   | Fewer chances of inconsistent data  |
| ✅ Easier Updates  | Update data in one place only       |
| ✅ Better Design   | Cleaner relationships between data  |

# 🧠 What is a **Database Schema**?

> A **Database Schema** is like the **blueprint** or **design** of your database.
> It tells **how your data is organized**, what **tables** exist, and **how they’re connected**.

---

## 🏗️ Real Life Analogy:

Imagine you're building a **house**:

- The **schema** is your **architectural plan** — showing rooms, doors, connections.
- The **actual house** is the **real data** stored as per the plan.

In a database:

- Rooms = **Tables**
- Walls = **Columns**
- Connections = **Relationships / Foreign Keys**

---

## 📘 In Technical Terms:

A **database schema defines**:

- Tables and their names
- Columns in each table (name, datatype)
- Primary and foreign keys
- Constraints (like `NOT NULL`, `UNIQUE`, etc.)
- Relationships between tables

---

## 🔹 Example of a Simple Schema:

Let’s say you’re designing a schema for a Movie App:

### 🔸 Table 1: `Users`

| Column Name | Data Type    |
| ----------- | ------------ |
| user_id     | INT (PK)     |
| name        | VARCHAR(100) |
| email       | VARCHAR(100) |

---

### 🔸 Table 2: `Movies`

| Column Name | Data Type    |
| ----------- | ------------ |
| movie_id    | INT (PK)     |
| title       | VARCHAR(100) |
| genre       | VARCHAR(50)  |

---

### 🔸 Table 3: `Watchlist`

| Column Name | Data Type         |
| ----------- | ----------------- |
| user_id     | INT (FK → Users)  |
| movie_id    | INT (FK → Movies) |

---

## 🎯 Summary:

- Schema = **Structure** of your database (like the plan of a building).
- It includes **tables, columns, data types, and relationships**.
- You define the schema **before** inserting actual data.

# 📘 What are **Axioms** in DBMS?

> In DBMS (specifically in **Normalization** and **Functional Dependency**),
> **Axioms are basic rules** that help us **infer** or **find more functional dependencies**.

You can think of **axioms** as:

> 🧠 "Logical rules that always hold true when working with functional dependencies."

They are used in **Armstrong's Axioms**, which help us **find all possible FDs** (called **closure**).

---

## 🧱 Why do we need Axioms?

Suppose you know:

- `A → B`
- `B → C`

Can you say `A → C`? ✅ YES!
Because you’re applying **Transitivity Axiom** (one of Armstrong’s Axioms).

---

## ✨ The 3 Basic Armstrong's Axioms:

| Axiom Name       | Rule                              | Meaning                                      |
| ---------------- | --------------------------------- | -------------------------------------------- |
| **Reflexivity**  | If Y is a subset of X, then X → Y | Anything determines itself or part of itself |
| **Augmentation** | If X → Y, then XZ → YZ            | You can add same thing to both sides         |
| **Transitivity** | If X → Y and Y → Z, then X → Z    | Like a chain reaction                        |

---

## 🔁 Example:

Let’s say you know:

- `RollNo → Name`
- `Name → Email`

Then using **Transitivity**, we know:

- `RollNo → Email`

That’s how **axioms help** us **deduce new FDs** from existing ones.

---

## 🧠 Summary:

- **Axioms = rules** to derive new functional dependencies.
- Based on logic that’s always valid.
- Used heavily in **normalization** and **FD closure**.

# DB Keys

### 1. **Primary Key**

- **What it is**: A primary key is like an ID card for a row in a table. It makes sure that each row can be **uniquely identified**.
- **Example**: Imagine a table of students, where each student has a unique **StudentID**. You can think of **StudentID** as the primary key. Every student must have a unique ID (no two students can have the same **StudentID**).

  - **Why important**: No two students can have the same ID, and the ID can't be empty.

### 2. **Foreign Key**

- **What it is**: A foreign key is a link between two tables. It’s like a reference to the **primary key** in another table.
- **Example**: Let's say we have two tables: one for **Students** and one for **Courses**. In the **Courses** table, we can have a column called **StudentID** which refers to the **StudentID** from the **Students** table. This way, we can link each course to a student.

  - **Why important**: It ensures that we can connect related data from different tables (like matching students to their courses).

### 3. **Unique Key**

- **What it is**: A unique key ensures that all values in a column are **different** from each other, but unlike the primary key, it **can allow null** values (empty).
- **Example**: Imagine a **Email** column in a **Users** table. Each email must be unique, meaning no two users can share the same email. But some users may not have an email (hence, it can allow empty values).

  - **Why important**: It ensures uniqueness but doesn’t force a value to be present.

### 4. **Composite Key**

- **What it is**: A composite key is made up of **two or more columns** together to create a unique identifier for a row.
- **Example**: In a table that tracks **Student Courses**, you might use both **StudentID** and **CourseID** to identify a row. So, one student might be enrolled in many courses, but each combination of **StudentID** and **CourseID** is unique.

  - **Why important**: Sometimes, a single column is not enough, and you need to combine multiple columns to create a unique identifier.

### 5. **Candidate Key**

- **What it is**: A candidate key is any column or combination of columns that could be used as a **primary key**. In other words, it’s a **potential primary key**.
- **Example**: In a **Users** table, both **Email** and **UserID** could be candidate keys because both can uniquely identify a user.

  - **Why important**: It’s the list of possible choices for what could be the primary key.

### 6. **Alternate Key**

- **What it is**: An alternate key is a **candidate key** that was **not chosen** as the primary key.
- **Example**: In the previous example, if we chose **UserID** as the primary key, then **Email** becomes the alternate key.

  - **Why important**: It’s still a unique identifier but is not the main one.

### 7. **Super Key**

- **What it is**: A super key is any combination of columns that **uniquely identifies a row**, but it may include extra columns that aren’t necessary.
- **Example**: If **UserID** is enough to uniquely identify a user, but you use both **UserID** and **Email** together as a key, this would still be a super key (though it's not minimal).

  - **Why important**: It’s a broader definition, but in practice, we use the minimal keys (primary and candidate).

### To sum up:

- **Primary Key**: Uniquely identifies rows in a table. No duplicates or empty values.
- **Foreign Key**: Links data between two tables.
- **Unique Key**: Ensures values are unique, but can have empty values.
- **Composite Key**: Combines multiple columns to uniquely identify a row.
- **Candidate Key**: A possible choice for the primary key.
- **Alternate Key**: A candidate key not selected as the primary key.
- **Super Key**: Any combination of columns that uniquely identifies a row (but may include extra, unnecessary columns).

# 1NF (First Normal Form)

**What is 1NF?**
1NF is a rule that says each column in a table should only contain **atomic** (single, indivisible) values. In simpler terms, a table is in **1NF** when:

- Each column has only one value per row (no lists or sets).
- Each value in a column is of the **same type**.
- The order of rows and columns doesn't matter.

### **Example**: Let's look at a simple table that is **NOT** in 1NF.

#### **Non-1NF Table (Not in 1NF)**

| StudentID | Name    | Courses                     |
| --------- | ------- | --------------------------- |
| 1         | Alice   | Math, Science, English      |
| 2         | Bob     | Math, History               |
| 3         | Charlie | English, Science, Geography |

Here’s the problem:

- The **Courses** column has multiple values (a list of courses) for a single student, which violates 1NF.
- A table in 1NF should not have multiple values in a single column.

#### **Convert to 1NF**

To bring this table into **1NF**, we need to make sure every column only has **one value** per row. So, we split the multiple values in the **Courses** column into separate rows.

#### **1NF Table (After Conversion)**

| StudentID | Name    | Course    |
| --------- | ------- | --------- |
| 1         | Alice   | Math      |
| 1         | Alice   | Science   |
| 1         | Alice   | English   |
| 2         | Bob     | Math      |
| 2         | Bob     | History   |
| 3         | Charlie | English   |
| 3         | Charlie | Science   |
| 3         | Charlie | Geography |

Now, each column contains only **single values**, and there are no lists or sets. Each row represents a unique combination of **StudentID**, **Name**, and **Course**, and that satisfies **1NF**.

### **Summary of 1NF**:

- Every column must have **atomic values** (no multiple values in one column).
- No repeating groups or lists in any column.
- Each record (row) in the table is unique.

So, in simple terms: **1NF ensures that each field contains only one piece of information.**

# 2NF (Second Normal Form)

**What is 2NF?**
A table is in **2NF** if:

1. It is already in **1NF**.
2. It has **no partial dependency**—this means that **every non-key column** must depend on the **entire primary key** and not just a part of it.

#### **Example of 2NF:**

Let's say we have a table with a **composite primary key** (a primary key made up of more than one column). Here's the table **before 2NF**:

#### **Non-2NF Table** (Not in 2NF)

| StudentID | CourseID | StudentName | CourseName |
| --------- | -------- | ----------- | ---------- |
| 1         | 101      | Alice       | Math       |
| 1         | 102      | Alice       | Science    |
| 2         | 101      | Bob         | Math       |
| 2         | 103      | Bob         | History    |

- **Primary Key**: (`StudentID`, `CourseID`)

**Problem**: The **StudentName** and **CourseName** are dependent on only a part of the primary key:

- **StudentName** depends only on **StudentID**.
- **CourseName** depends only on **CourseID**.

This is a **partial dependency**, which violates 2NF.

#### **To convert this to 2NF**, we need to break the table into two tables:

1. A table to store student information.
2. A table to store course enrollment information.

#### **2NF Table (After Conversion)**

**Table 1: Student Information**

| StudentID | StudentName |
| --------- | ----------- |
| 1         | Alice       |
| 2         | Bob         |

**Table 2: Course Enrollment**

| StudentID | CourseID | CourseName |
| --------- | -------- | ---------- |
| 1         | 101      | Math       |
| 1         | 102      | Science    |
| 2         | 101      | Math       |
| 2         | 103      | History    |

Now, **StudentName** depends only on **StudentID**, and **CourseName** depends only on **CourseID**, removing partial dependencies.

### **Summary of 2NF**:

- The table must be in **1NF**.
- No partial dependencies: All non-key columns must depend on the **entire primary key**, not just part of it.

---

# 3NF (Third Normal Form)

**What is 3NF?**
A table is in **3NF** if:

1. It is in **2NF**.
2. It has **no transitive dependencies**—this means that non-key columns should depend only on the primary key, not on other non-key columns.

#### **Example of 3NF:**

Let’s start with a table that’s in **2NF** but not in **3NF**:

#### **Non-3NF Table** (Not in 3NF)

| StudentID | StudentName | CourseID | CourseName | InstructorName |
| --------- | ----------- | -------- | ---------- | -------------- |
| 1         | Alice       | 101      | Math       | Dr. Smith      |
| 1         | Alice       | 102      | Science    | Dr. Johnson    |
| 2         | Bob         | 101      | Math       | Dr. Smith      |
| 2         | Bob         | 103      | History    | Dr. Lee        |

- **Primary Key**: (`StudentID`, `CourseID`)

**Problem**: The **InstructorName** is dependent on **CourseName**, and **CourseName** is dependent on **CourseID**. This creates a **transitive dependency**: **InstructorName** depends on **CourseID** via **CourseName**.

#### **To convert this to 3NF**, we need to remove the transitive dependency. We do this by creating a separate table for **Instructor** information.

#### **3NF Table (After Conversion)**

**Table 1: Student Information**

| StudentID | StudentName |
| --------- | ----------- |
| 1         | Alice       |
| 2         | Bob         |

**Table 2: Course Information**

| CourseID | CourseName | InstructorID |
| -------- | ---------- | ------------ |
| 101      | Math       | 1            |
| 102      | Science    | 2            |
| 103      | History    | 3            |

**Table 3: Instructor Information**

| InstructorID | InstructorName |
| ------------ | -------------- |
| 1            | Dr. Smith      |
| 2            | Dr. Johnson    |
| 3            | Dr. Lee        |

**Table 4: Course Enrollment**

| StudentID | CourseID |
| --------- | -------- |
| 1         | 101      |
| 1         | 102      |
| 2         | 101      |
| 2         | 103      |

Now, **InstructorName** depends only on **InstructorID**, and there is no transitive dependency between non-key columns.

### **Summary of 3NF**:

- The table must be in **2NF**.
- No transitive dependencies: Non-key columns must depend directly on the primary key, not on other non-key columns.

---

### **Summary of All Normal Forms**:

- **1NF**: Each column has atomic values (no multiple values in a single column).
- **2NF**: The table is in 1NF, and there are no partial dependencies (non-key columns depend on the whole primary key).
- **3NF**: The table is in 2NF, and there are no transitive dependencies (non-key columns depend directly on the primary key, not on other non-key columns).

# why SQL is declarative

SQL (Structured Query Language) is considered a **declarative** programming language because it focuses on **what** you want to do with the data rather than **how** to do it.

- **What you want**: In SQL, you specify the **desired result**, not the step-by-step procedure to achieve it. You tell the database what information you need, and the database figures out the best way to retrieve it.

- **You don't control the flow**: Unlike imperative languages where you manually control loops and conditions, SQL allows you to express your needs in terms of **queries** like "select rows," "insert data," or "delete records," without worrying about how the database will execute those operations internally.

### Example of SQL being Declarative:

#### **Query to Select Data (Declarative)**:

```sql
SELECT name, age FROM employees WHERE department = 'Sales';
```

- **What it specifies**: The query specifies that you want to retrieve the `name` and `age` of employees who are in the 'Sales' department.
- **How it works**: You don't need to tell the database how to go through the records or perform any looping. The database itself handles that automatically.

### SQL vs Imperative Programming:

- In **imperative programming**, you would manually specify the steps to loop through data, check each record, and store the results.

- In **SQL (declarative)**, you describe the outcome (what data you want) and let the system (the SQL engine) decide the most efficient way to execute that request.

---

### SQL and Declarative Programming:

- **Declarative**: You state your intention.

  - Example: "I want all employees in the 'Sales' department."

- **Imperative**: You tell the system how to achieve the goal.

  - Example: "Go through each record, check if the department is 'Sales', and then fetch the name and age of matching records."

### In Summary:

SQL is declarative because you specify the **what** (what data you need, what action to perform), but you don't specify the **how** (how to retrieve the data or perform the action). The database system determines the most efficient execution plan for that task.

# My SQL Installation

A step-by-step guide to installing MySQL and MySQL Workbench on Windows can be found [here](https://arvideichner.medium.com/a-step-by-step-guide-to-installing-mysql-and-mysql-workbench-on-windows-c4f2e9e37fb8).

### Step 1: Open MySQL Terminal

1. **Launch MySQL** by opening your terminal or command prompt:

   ```bash
   mysql -u root -p
   ```

   - `-u root`: Use the root user (you can use any MySQL user).
   - `-p`: Prompt for the password.

   After typing the command, you'll be asked to enter the password for the MySQL root user.

2. **Connect to a Database**:
   Once you're logged in, you need to use a specific database. If you don’t have one, you can create one.

   ```sql
   CREATE DATABASE company;
   USE company;
   ```

   - `CREATE DATABASE company;`: Creates a database called `company`.
   - `USE company;`: Switches to the `company` database.

---

### Step 2: Create a Table

Let's create a table called `employees` with some columns: `employee_id`, `name`, `age`, and `department`.

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    department VARCHAR(50)
);
```

- This command creates a table called `employees` with four columns. `employee_id` is the primary key, which uniquely identifies each employee.

---

### Step 3: Insert Data

Now that the table is created, let’s add some data.

```sql
INSERT INTO employees (employee_id, name, age, department)
VALUES (1, 'Alice', 30, 'Sales');
```

This inserts a row into the `employees` table with the values:

- `employee_id`: 1
- `name`: Alice
- `age`: 30
- `department`: Sales

You can also insert multiple rows in one command:

```sql
INSERT INTO employees (employee_id, name, age, department)
VALUES
    (2, 'Bob', 25, 'Marketing'),
    (3, 'Charlie', 28, 'HR');
```

---

### Step 4: View Data

To see the data you’ve inserted into the table, you can use the `SELECT` command:

```sql
SELECT * FROM employees;
```

This will show all rows in the `employees` table.

---

### Step 5: Update Data

Suppose you want to update Alice’s age to 31. You would use the `UPDATE` command:

```sql
UPDATE employees
SET age = 31
WHERE name = 'Alice';
```

This command will change the `age` of the employee named "Alice" to 31.

---

### Step 6: View Data After Update

You can verify the update by running:

```sql
SELECT * FROM employees;
```

You should see that Alice's age is now updated to 31.

---

### Step 7: Delete Data

If you want to delete Bob's record, use the `DELETE` command:

```sql
DELETE FROM employees
WHERE name = 'Bob';
```

This will remove Bob’s record from the `employees` table.

---

### Step 8: View Data After Deletion

Once again, you can run:

```sql
SELECT * FROM employees;
```

# commonly used SQL commands

### **1. SELECT** - Retrieve Data from a Table

The `SELECT` statement is used to retrieve data from one or more tables.

#### **Syntax**:

```sql
SELECT column1, column2, ...
FROM table_name;
```

#### **Example**:

```sql
SELECT name, age
FROM employees;
```

This will return the `name` and `age` of all employees from the `employees` table.

---

### **2. WHERE** - Filter Records

The `WHERE` clause is used to filter records based on a specific condition.

#### **Syntax**:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

#### **Example**:

```sql
SELECT name, age
FROM employees
WHERE age > 25;
```

This will return the `name` and `age` of employees who are older than 25.

---

### **3. INSERT** - Insert Data into a Table

The `INSERT INTO` command is used to insert new rows of data into a table.

#### **Syntax**:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

#### **Example**:

```sql
INSERT INTO employees (employee_id, name, age, department)
VALUES (1, 'Alice', 30, 'Sales');
```

This inserts a new row into the `employees` table.

---

### **4. UPDATE** - Update Existing Data

The `UPDATE` command is used to modify existing data in a table.

#### **Syntax**:

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

#### **Example**:

```sql
UPDATE employees
SET age = 31
WHERE name = 'Alice';
```

This updates Alice’s age to 31 in the `employees` table.

---

### **5. DELETE** - Delete Data from a Table

The `DELETE` command is used to delete existing records in a table.

#### **Syntax**:

```sql
DELETE FROM table_name
WHERE condition;
```

#### **Example**:

```sql
DELETE FROM employees
WHERE name = 'Bob';
```

This deletes the record of the employee named 'Bob' from the `employees` table.

---

### **6. CREATE TABLE** - Create a New Table

The `CREATE TABLE` command is used to create a new table in the database.

#### **Syntax**:

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    ...
);
```

#### **Example**:

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    department VARCHAR(50)
);
```

This creates a new table called `employees` with four columns: `employee_id`, `name`, `age`, and `department`.

---

### **7. ALTER TABLE** - Modify Table Structure

The `ALTER TABLE` command is used to modify the structure of an existing table, such as adding or removing columns.

#### **Syntax**:

```sql
ALTER TABLE table_name
ADD column_name datatype;
```

#### **Example**:

```sql
ALTER TABLE employees
ADD email VARCHAR(100);
```

This adds a new column `email` to the `employees` table.

---

### **8. DROP TABLE** - Delete a Table

The `DROP TABLE` command is used to delete an entire table from the database.

#### **Syntax**:

```sql
DROP TABLE table_name;
```

#### **Example**:

```sql
DROP TABLE employees;
```

This will delete the `employees` table from the database.

---

### **9. GROUP BY** - Group Records

The `GROUP BY` clause groups rows that have the same values into summary rows, often used with aggregate functions like `COUNT()`, `SUM()`, `AVG()`, etc.

#### **Syntax**:

```sql
SELECT column1, SUM(column2)
FROM table_name
GROUP BY column1;
```

#### **Example**:

```sql
SELECT department, COUNT(*) AS num_employees
FROM employees
GROUP BY department;
```

This counts the number of employees in each department.

---

### **10. HAVING** - Filter Grouped Records

The `HAVING` clause is used to filter the results after using `GROUP BY`. It’s similar to the `WHERE` clause but applies to grouped data.

#### **Syntax**:

```sql
SELECT column1, COUNT(*)
FROM table_name
GROUP BY column1
HAVING COUNT(*) > 5;
```

#### **Example**:

```sql
SELECT department, COUNT(*) AS num_employees
FROM employees
GROUP BY department
HAVING COUNT(*) > 2;
```

This retrieves departments where the number of employees is greater than 2.

---

### **11. ORDER BY** - Sort Data

The `ORDER BY` clause is used to sort the result set in either ascending or descending order.

#### **Syntax**:

```sql
SELECT column1, column2
FROM table_name
ORDER BY column1 [ASC|DESC];
```

#### **Example**:

```sql
SELECT name, age
FROM employees
ORDER BY age DESC;
```

This sorts the employees by age in descending order.

---

### **12. DISTINCT** - Remove Duplicates

The `DISTINCT` keyword is used to remove duplicate rows from the result set.

#### **Syntax**:

```sql
SELECT DISTINCT column1
FROM table_name;
```

#### **Example**:

```sql
SELECT DISTINCT department
FROM employees;
```

This returns a list of unique departments, removing any duplicates.

---

### **13. JOIN** - Combine Data from Multiple Tables

The `JOIN` clause is used to combine rows from two or more tables based on a related column between them.

#### **Types of Joins**:

- **INNER JOIN**: Returns only matching rows from both tables.
- **LEFT JOIN**: Returns all rows from the left table, and matched rows from the right table.
- **RIGHT JOIN**: Returns all rows from the right table, and matched rows from the left table.
- **FULL OUTER JOIN**: Returns rows when there is a match in either the left or right table.

#### **Example** (INNER JOIN):

```sql
SELECT employees.name, departments.name
FROM employees
INNER JOIN departments
ON employees.department_id = departments.department_id;
```

This retrieves the employee names along with their department names by matching the `department_id` in both tables.

---

### **14. LIMIT** - Limit the Number of Rows

The `LIMIT` clause is used to specify the number of records returned.

#### **Syntax**:

```sql
SELECT column1, column2
FROM table_name
LIMIT number_of_rows;
```

#### **Example**:

```sql
SELECT name, age
FROM employees
LIMIT 5;
```

This retrieves the first 5 rows from the `employees` table.

---

### **15. BETWEEN** - Filter Data Within a Range

The `BETWEEN` operator is used to filter the result set within a certain range (inclusive).

#### **Syntax**:

```sql
SELECT column1, column2
FROM table_name
WHERE column1 BETWEEN value1 AND value2;
```

#### **Example**:

```sql
SELECT name, age
FROM employees
WHERE age BETWEEN 20 AND 30;
```

This retrieves employees whose ages are between 20 and 30.

---

### **16. IN** - Check if a Value is Within a Set of Values

The `IN` operator is used to check if a value matches any value in a list or subquery.

#### **Syntax**:

```sql
SELECT column1, column2
FROM table_name
WHERE column1 IN (value1, value2, ...);
```

#### **Example**:

```sql
SELECT name, department
FROM employees
WHERE department IN ('Sales', 'Marketing');
```

This retrieves employees who belong to either the `Sales` or `Marketing` department.

---

### **17. LIKE** - Pattern Matching

The `LIKE` operator is used to search for a specified pattern in a column.

#### **Syntax**:

```sql
SELECT column1, column2
FROM table_name
WHERE column1 LIKE pattern;
```

#### **Example**:

```sql
SELECT name
FROM employees
WHERE name LIKE 'A%';
```

This retrieves employees whose names start with the letter 'A'.

---

### **18. IS NULL** - Check for NULL Values

The `IS NULL` operator is used to check if a column contains a **NULL** value.

#### **Syntax**:

```sql
SELECT column1, column2
FROM table_name
WHERE column1 IS NULL;
```

#### **Example**:

```sql
SELECT name
FROM employees
WHERE department IS NULL;
```

This retrieves employees whose `department` column contains NULL values.

### **19. OFFSET** - Skips a number of rows before starting to return rows.

#### **Syntax**:

```sql
SELECT column1, column2
FROM table_name
LIMIT number_of_rows
OFFSET number_to_skip;
```

### Summary of Common SQL Commands:

| **Command**      | **Purpose**                               | **Example**                                                                           |
| ---------------- | ----------------------------------------- | ------------------------------------------------------------------------------------- |
| **SELECT**       | Retrieve data from a table                | `SELECT name, age FROM employees;`                                                    |
| **WHERE**        | Filter records based on conditions        | `SELECT * FROM employees WHERE age > 25;`                                             |
| **INSERT**       | Insert new rows into a table              | `INSERT INTO employees (name, age) VALUES ('Alice', 30);`                             |
| **UPDATE**       | Modify existing records in a table        | `UPDATE employees SET age = 31 WHERE name = 'Alice';`                                 |
| **DELETE**       | Delete records from a table               | `DELETE FROM employees WHERE name = 'Bob';`                                           |
| **CREATE TABLE** | Create a new table                        | `CREATE TABLE employees (id INT, name VARCHAR(50));`                                  |
| **ALTER TABLE**  | Modify the structure of a table           | `ALTER TABLE employees ADD email VARCHAR(100);`                                       |
| **DROP TABLE**   | Delete a table from the database          | `DROP TABLE employees;`                                                               |
| **GROUP BY**     | Group rows by a specific column           | `SELECT department, COUNT(*) FROM employees GROUP BY department;`                     |
| **HAVING**       | Filter results after `GROUP BY`           | `SELECT department, COUNT(*) FROM employees GROUP BY department HAVING COUNT(*) > 2;` |
| **ORDER BY**     | Sort results based on one or more columns | `SELECT * FROM employees ORDER BY age DESC;`                                          |
| **JOIN**         | Combine data from multiple tables         | `SELECT * FROM employees JOIN departments ON employees.dept_id = departments.id;`     |
| **LIMIT**        | Limit the number of rows returned         | `SELECT * FROM employees LIMIT 5;`                                                    |
| **BETWEEN**      | Filter results within a range             | `SELECT * FROM employees WHERE age BETWEEN 20 AND 30;`                                |
| **IN**           | Filter results based on a list of values  | `SELECT * FROM employees WHERE department IN ('Sales', 'HR');`                        |
| **LIKE**         | Pattern matching for strings              | `SELECT * FROM employees WHERE name LIKE 'A%';`                                       |
| **IS NULL**      | Check for NULL values                     | `SELECT * FROM employees WHERE department IS NULL;`                                   |



# 🔹 What is a **Trigger** in SQL?

A **Trigger** is **like an automatic response** to some event happening in a database.

### ✅ Think of it like:

> “If someone **inserts**, **updates**, or **deletes** a row in a table, then do something automatically.”

---

### 🔧 Real-life Example:

> Imagine you have a table called `Employees`, and whenever someone adds a new employee, you want to log that action into another table called `Employee_Log`.

---

### 📦 Table Setup

```sql
-- Main table
CREATE TABLE Employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    salary DECIMAL
);

-- Log table
CREATE TABLE Employee_Log (
    log_id INT AUTO_INCREMENT PRIMARY KEY,
    message VARCHAR(255),
    log_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

### 🧠 Trigger Example

```sql
DELIMITER //

CREATE TRIGGER after_employee_insert
AFTER INSERT ON Employees
FOR EACH ROW
BEGIN
    INSERT INTO Employee_Log(message)
    VALUES (CONCAT('New employee added: ', NEW.name));
END //

DELIMITER ;
```

#### ✅ What this trigger does:

* It runs **AFTER** a new row is added to `Employees`.
* It inserts a message in the `Employee_Log` table automatically.

---

## 🔹 What is a **Stored Procedure**?

A **Stored Procedure** is like a **named function** in the database.

> You write some SQL code once and give it a name, and you can call it whenever needed.

---

### 🧠 Simple Example:

```sql
DELIMITER //

CREATE PROCEDURE AddEmployee(
    IN empName VARCHAR(100),
    IN empSalary DECIMAL
)
BEGIN
    INSERT INTO Employees(name, salary)
    VALUES (empName, empSalary);
END //

DELIMITER ;
```

### ✅ To run this procedure:

```sql
CALL AddEmployee('Sangam', 50000);
```

#### ✅ What this procedure does:

* You call it with a name and salary.
* It adds a new row to the `Employees` table.


## 🟨 Key Differences

| Feature    | Trigger                         | Stored Procedure            |
| ---------- | ------------------------------- | --------------------------- |
| Invoked    | Automatically on table events   | Manually using `CALL`       |
| Use Case   | Logging, validation, automation | Reuse logic, business rules |
| Parameters | No (uses NEW/OLD values)        | Yes (accepts input/output)  |




# Conflicts in DB
When multiple **transactions** try to access the **same data** at the same time, we have to manage:

* **Who reads** (`R`) the data
* **Who writes** (`W`) the data

These actions can happen in different combinations, leading to different problems or no problems.

---

## 🔹 1. **WR Conflict** – Write **after** Read

### ➡️ Also called: **Unrepeatable Read**

> One transaction reads the data, then another transaction writes (updates) it.

### 🔧 Example:

* **T1:** `READ(X)` → sees value = 10
* **T2:** `WRITE(X)` → changes value to 20
* **T1:** reads X again → now it's 20 ❌ (value changed in between)

➡️ ⚠️ Problem: T1 saw different values in same transaction

---

## 🔹 2. **RW Conflict** – Read **after** Write

### ➡️ Also called: **Dirty Read**

> One transaction writes a value, another transaction reads it **before the first one is committed.**

### 🔧 Example:

* **T1:** `WRITE(X)` → sets X = 500 (but not committed)
* **T2:** `READ(X)` → sees X = 500
* **T1:** rolls back (undo write)
* Now X is not 500 anymore 😬

➡️ ⚠️ Problem: T2 read something that never really happened

---

## 🔹 3. **WW Conflict** – Write **after** Write

### ➡️ Also called: **Lost Update**

> Two transactions write to the same data item without knowing about each other.

### 🔧 Example:

* **T1:** `WRITE(X = 100)`
* **T2:** `WRITE(X = 200)` (overwrites T1)
* **Only T2’s write is saved**, T1’s update is **lost** ❌

➡️ ⚠️ Problem: One update disappears

---

## 🧩 Summary Table

| Conflict Type | Meaning           | Problem Name      | What happens?                            |
| ------------- | ----------------- | ----------------- | ---------------------------------------- |
| WR            | Write after Read  | Unrepeatable Read | First reads value, then it changes       |
| RW            | Read after Write  | Dirty Read        | Reads a value that might get rolled back |
| WW            | Write after Write | Lost Update       | One write overwrites another             |

# How atomicity is ensured

## 🔹 Why Use Logging?

> Logging is like **keeping a backup notebook** of what your database is doing.

When a transaction runs:

* We write the operations to a **log file first**
* Only then do we apply changes to the **actual database**

If a failure happens (like power cut 💡⚡️), the database uses the log to **recover or rollback** safely.

---

## 🔹 1. **Standard Logging (Write-Ahead Logging – WAL)**

### ✅ Key Idea:

> First write to a log file, then update the database.

---

### 🧠 Real-world analogy:

Imagine you're filling a form. You first **write all answers in pencil** on rough paper (log), and only after double-checking, you fill them on the final form (DB).

---

### 🔧 How It Works:

1. Transaction begins
2. Writes its changes to **log file**
3. Once logged, changes are applied to the database
4. If crash happens, logs are replayed to **recover** or **undo**

---

### 🔁 What is Stored in the Log?

* Transaction ID
* Operation type (insert, update, delete)
* Old value (for undo)
* New value (for redo)

---

### ✅ Ensures Atomicity because:

* If a crash happens, we can look at the log and **redo** or **undo** changes correctly.

---

## 🔹 2. **Shadow Logging (Shadow Paging)**

### ✅ Key Idea:

> Keep a **shadow copy** (backup) of the database page.
> If everything goes well, swap the shadow with the actual data.

---

### 🧠 Real-world analogy:

You're editing a Word document, but instead of changing the real file, you copy it and work on the copy. Only when you're happy with changes, you replace the original.

---

### 🔧 How It Works:

1. Before making changes, copy the original page (called **shadow page**)
2. Perform changes on a **new page (updated copy)**
3. When transaction commits, update the **page table pointer**
4. The old version (shadow) is kept aside in case something fails

---

### ✅ Ensures Atomicity because:

* If a crash happens, the pointer still points to the original page — so no corrupt data
* We either switch completely to new or stick with old — never half-updated

---

## 📊 Difference Table

| Feature          | **Write-Ahead Logging**            | **Shadow Paging (Logging)**            |
| ---------------- | ---------------------------------- | -------------------------------------- |
| Log Required?    | Yes (UNDO & REDO logs)             | No actual log, uses shadow copies      |
| Performance      | Slower (log I/O + DB I/O)          | Faster for read-heavy, slow for writes |
| Rollback support | Yes (via logs)                     | No direct rollback (uses pointer swap) |
| Storage Use      | Less                               | More (duplicate pages)                 |
| Used In          | Most modern DBMS (MySQL, Postgres) | Some older or embedded systems         |

---

## ✅ Summary:

| Method           | Ensures Atomicity? | How?                                   |
| ---------------- | ------------------ | -------------------------------------- |
| Standard Logging | ✅ Yes              | Logs before applying, allows undo/redo |
| Shadow Paging    | ✅ Yes              | Uses backup pages; commit via pointer  |

