# Database and SQL

> Source: Canvas > Resources > Implementation > Database and SQL
> Last updated: 2026-02-10
> Status: complete

# 🗄️ Database and SQL

Storing and retrieving data with relational databases

## 🎯 Database Types: SQL vs NoSQL

To store data, you generally use a database. Broadly speaking, there are two types: **relational databases** and **non-relational databases**. Online, you often see the terms SQL and NoSQL, referring to the query language used to query the first type, but not the second.

#### 🏗️ Relational Databases (SQL)

Data stored in tables with relationships and keys.

**Examples:** MySQL, PostgreSQL, Microsoft SQL Server.

#### 📊 Non-Relational Databases (NoSQL)

Data stored in key-value pairs or as documents.

**Examples:** MongoDB, CouchDB, Redis, Cassandra.

**💡 This Semester's Default Choice:** Since an RDBMS best aligns with the simple object models we will use, this is the **sensible default**. Microsoft SQL Server integrates best with other components in the SD stack, such as ASP.NET MVC, which is why we prefer it.

## 🔧 Setting up the Database

SQL comes in two main variants that serve different purposes:

#### 🏗️ Data Definition Language (DDL)

Used to define and modify database structure (CREATE, DROP, ALTER).

#### 📊 Data Manipulation Language (DML)

Used to query and modify data (SELECT, INSERT, UPDATE, DELETE).

### Database Creation Options:

* **SQL Scripts:** Direct SQL statements for full control.
* **Visual Studio:** Database tools and designers.
* **Entity Framework (ORM):** Code-first approach (use only after understanding manual setup).

**⚠️ Learning Path:** Object-Relational Mappers like Entity Framework can generate tables for you, but this provides less control over their structure. Only use them once you understand how to create databases manually!

## 🔍 Querying the Database

Once you have a database, you can store and retrieve data from it. This is done by writing queries (literally 'questions'). Here's a practical example:

Example SQL Query:

```sql
SELECT
  Name,
  Email,
  Age
FROM
  Users
WHERE
  Age > 18;
```

**💡 Query Explanation:** This query retrieves the Name, Email address, and Age of all rows in the Users table where the Age column contains a value greater than 18.

There are many different query options available. You can learn and practice them extensively in SQL School. From your C# code, you can execute these queries on the database and display the results on the screen.

## 🎯 Hands-On Practice

**🎓 SQL School:** Master SQL fundamentals through interactive exercises and practice problems.

`http://sqlschool.fhict.nl/`

## 📚 Essential Resources

### 🔧 Setup & Configuration

* `https://selfservice.app.fhict.nl/` – request a free SQL Server account
* `https://docs.microsoft.com/en-us/visualstudio/data-tools/create-a-sql-database-by-using-a-designer?view=vs-2022`
* `https://entityframework.net/ef-code-first`

### 🔗 Related Course Materials

* How to work with relational databases?
* Relational Database Design
* Database Implementation

