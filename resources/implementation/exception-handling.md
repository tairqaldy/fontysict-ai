# Exception Handling

> Source: Canvas > Resources > Implementation > Exception Handling
> Last updated: 2026-02-10
> Status: complete

# ⚠️ Exception Handling

Building robust applications that gracefully handle errors

## 🎯 Why Exception Handling Matters

**🏦 Real-World Scenario:** Imagine you're building a bank application, and a user tries to withdraw money from an account with insufficient funds. Without proper exception handling, your entire application might crash, leaving the user confused and frustrated.

Exception handling is your safety net. It allows you to:

#### 🛡️ Prevent Application Crashes

Keep your application running even when unexpected errors occur.

#### 💬 Provide Meaningful Error Messages

Help users understand what went wrong and what they can do about it.

#### 🔄 Gracefully Handle Unexpected Scenarios

Manage edge cases and maintain application flow.

#### 📊 Log and Track Issues

Monitor application health and identify recurring problems.

## 🔍 Understanding Exceptions

**📘 Key Concept:** In .NET, an exception is more than just an error – it's an **object** that contains critical information about what went wrong during program execution.

When an unexpected event occurs (like dividing by zero, accessing a null reference, or trying to read a non-existent file), .NET creates an exception object with details about the error.

### Common Exception Triggers:

* `NullReferenceException` – accessing an object that is null
* `ArgumentException` – invalid method arguments
* `IOException` – input/output related errors
* `DivideByZeroException` – mathematical division by zero
* `FormatException` – invalid string conversion

## 💻 Exception Handling in Practice

### Bank Account Example

```csharp
public class BankAccount
{
    public decimal Balance { get; private set; }

    public void Withdraw(decimal amount)
    {
        try
        {
            if (amount < 0)
                throw new ArgumentException("Withdrawal amount cannot be negative");

            if (amount > Balance)
                throw new InsufficientFundsException("Insufficient funds for withdrawal");

            Balance -= amount;
        }
        catch (ArgumentException ex)
        {
            // Handle invalid input
        }
        catch (InsufficientFundsException ex)
        {
            // Handle specific banking scenario
        }
        catch (Exception ex)
        {
            // Catch any unexpected exceptions
        }
        finally
        {
            // Always executed, useful for cleanup
        }
    }
}

public class InsufficientFundsException : Exception
{
    public InsufficientFundsException(string message) : base(message) { }
}
```

**💡 Code Breakdown:** This example shows how to handle specific exceptions differently, provide meaningful error messages, and ensure cleanup code always runs in the `finally` block.

## 🏆 Exception Handling Best Practices

* Catch specific exceptions before general ones.
* Provide meaningful error messages and context.
* Always log exceptions.
* Use custom exceptions for domain-specific scenarios.
* **Never swallow exceptions** with empty catch blocks.

## 📚 Learning Resources

* `https://docs.microsoft.com/en-us/dotnet/standard/exceptions/`
* `https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/exception-handling-statements`
* `https://learn.microsoft.com/en-us/dotnet/standard/exceptions/best-practices-for-exceptions`

