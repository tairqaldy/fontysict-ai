# How to work with relational databases?

> Source: Canvas > Software Development Skills > Implementation
> Last updated: 2026-02-10
> Status: complete

# 🗄️ Database Integration Mastery

Secure, performant, and maintainable database operations in production applications

**⚠️ Security First:** Database operations are a prime target for attacks. SQL injection vulnerabilities have compromised millions of applications. This workshop teaches you to write secure, robust database code that protects your users and your business.

**🎯 Workshop Goal:** Master professional database integration techniques. Learn to perform CRUD operations securely, handle errors gracefully, and optimize performance while maintaining code quality and security standards.

## 🔒 Database Security Fundamentals

**🚨 SQL Injection: The Million-Dollar Vulnerability**

**The Attack:** Malicious users can execute arbitrary SQL commands by manipulating input parameters.

**❌ Vulnerable Code:**

```csharp
string sql = "SELECT * FROM Products WHERE ProductName = '" + productName + "';";
```

**✅ Secure Code:**

```csharp
string sql = "SELECT * FROM Products WHERE ProductName = @productName";
command.Parameters.AddWithValue("@productName", productName);
```

**Why parameterization works:** Parameters are treated as data, not executable code. Even malicious input becomes harmless data.

## 🛡️ Professional Database Operations

**📝 CRUD Operations: The Professional Way**

**Create, Read, Update, Delete** - the fundamental operations that power every application.

* **CREATE:** INSERT statements with proper validation
* **READ:** SELECT with efficient filtering and pagination
* **UPDATE:** Targeted updates with concurrency control
* **DELETE:** Safe deletion with referential integrity

**⚡ Error Handling & Resource Management**

**Databases are external systems** - they can fail, be unavailable, or return unexpected results.

* **Connection failures:** Network issues, server downtime
* **Query errors:** Invalid SQL, missing tables, constraint violations
* **Resource leaks:** Unclosed connections, memory issues
* **Timeout handling:** Long-running queries

## 💻 Code Patterns & Best Practices

**🔧 Professional Database Code Structure**

**Using Statement Pattern:** Automatic resource disposal

```csharp
using (SqlConnection connection = new SqlConnection(connectionString))
{
    string sql = "SELECT * FROM Products WHERE CategoryId = @categoryId";
    using (SqlCommand command = new SqlCommand(sql, connection))
    {
        command.Parameters.AddWithValue("@categoryId", categoryId);
        try
        {
            connection.Open();
            using (SqlDataReader reader = command.ExecuteReader())
            {
                while (reader.Read())
                {
                    // Process results
                }
            }
        }
        catch (SqlException ex)
        {
            LogError($"Database error: {ex.Message}");
            throw new DataAccessException("Failed to retrieve products", ex);
        }
        catch (Exception ex)
        {
            LogError($"Unexpected error: {ex.Message}");
            throw;
        }
    }
}
```

## 🛠️ Prerequisites & Setup

**📋 Essential Knowledge:**

* [Database design principles](../design/relational-db-design.md)
* Basic SQL commands (SELECT, INSERT, UPDATE, DELETE)
* C# fundamentals and exception handling
* Understanding of [SQL parameterization](https://learn.microsoft.com/en-us/dotnet/api/system.data.sqlclient.sqlparametercollection.addwithvalue)

**🔐 Security Resources:**

* [SQL Injection Prevention](https://learn.microsoft.com/en-us/sql/relational-databases/security/sql-injection)
* [Exception Handling Best Practices](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/exceptions/how-to-execute-cleanup-code-using-finally)

## 🎯 Security Audit Challenge

**🔍 Code Security Assessment**

**Your Mission:** Conduct a comprehensive security audit of database operations in your Individual Assignment (IA) and Group Project (GP).

**🔎 Security Checklist:**

* **SQL Injection:** Are all parameters properly sanitized?
* **Connection Security:** Are connection strings secure?
* **Error Handling:** Are database errors handled gracefully?
* **Resource Management:** Are connections properly closed?
* **Input Validation:** Are user inputs validated before database operations?

### Phase 1: Vulnerability Assessment

**🔍 Code Analysis Questions:**

* **Parameter Usage:** Are you using string concatenation or parameterized queries?
* **Exception Handling:** What happens when database operations fail?
* **Resource Disposal:** Are you using `using` statements or manual connection management?
* **Input Validation:** How do you validate user input before database operations?
* **Error Logging:** Are database errors logged for monitoring?

### Phase 2: Secure Implementation

**🛡️ Security Implementation Guide:**

1. **Replace string concatenation** with parameterized queries
2. **Implement proper exception handling** with specific error types
3. **Add input validation** before database operations
4. **Use using statements** for automatic resource disposal
5. **Add logging** for monitoring and debugging

**🎯 Common Refactoring Patterns**

**Before (Vulnerable):**

```csharp
string sql = "UPDATE Users SET Email = '" + email + "' WHERE Id = " + userId;
SqlCommand command = new SqlCommand(sql, connection);
connection.Open();
command.ExecuteNonQuery();
connection.Close();
```

**After (Secure):**

```csharp
string sql = "UPDATE Users SET Email = @email WHERE Id = @userId";
using (SqlCommand command = new SqlCommand(sql, connection))
{
    command.Parameters.AddWithValue("@email", email);
    command.Parameters.AddWithValue("@userId", userId);
    try
    {
        connection.Open();
        int rowsAffected = command.ExecuteNonQuery();
        if (rowsAffected == 0)
            throw new InvalidOperationException("User not found");
    }
    catch (SqlException ex)
    {
        LogError($"Database error updating user {userId}: {ex.Message}");
        throw new DataAccessException("Failed to update user", ex);
    }
}
```

### Phase 3: Team Review & Validation

**🤝 Collaborative Security Review:**

* **Peer code review:** Have teammates review your database code
* **Security testing:** Try to inject malicious input (in a safe environment)
* **Performance testing:** Ensure your secure code performs well
* **Documentation:** Document your security improvements

## 📈 Performance & Monitoring

**⚡ Performance Considerations:**

* **Connection pooling:** Reuse connections efficiently
* **Query optimization:** Use indexes and efficient SQL
* **Batch operations:** Reduce round trips for multiple operations
* **Timeout handling:** Set appropriate timeout values
* **Monitoring:** Track query performance and errors

## 🎯 Learning Outcome Connection

**LO3: Implementation - Database Integration**

Professional database integration demonstrates your ability to:

* **Implement secure applications:** Prevent SQL injection and other vulnerabilities
* **Use databases effectively:** Perform CRUD operations with proper error handling
* **Apply security principles:** Parameterized queries and input validation
* **Write maintainable code:** Proper resource management and error handling

## 🚀 Next Steps

**⏭️ Ready for Web Development?** Continue with [ASP.NET and Bootstrap](aspnet-bootstrap.md) to build web applications that securely integrate with your database. Or continue with [Database Implementation](db-implementation.md) for a more in-depth workshop.

**🔒 Security First Principle:** Make security a habit, not an afterthought. Every database operation should be secure by default. Your users trust you with their data - protect it.

*Security isn't about perfect code - it's about making your application so expensive to attack that attackers move on to easier targets.*
