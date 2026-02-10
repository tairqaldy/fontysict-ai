# Exception Handling

# ⚠️ Exception Handling

Building robust applications that gracefully handle errors

## 🎯 Why Exception Handling Matters

**🏦 Real-World Scenario:** Imagine you're building a bank application, and a user tries to withdraw money from an account with insufficient funds. Without proper exception handling, your entire application might crash, leaving the user confused and frustrated.

Exception handling is your safety net. It allows you to:

#### 🛡️ Prevent Application Crashes

Keep your application running even when unexpected errors occur

#### 💬 Provide Meaningful Error Messages

Help users understand what went wrong and what they can do about it

#### 🔄 Gracefully Handle Unexpected Scenarios

Manage edge cases and maintain application flow

#### 📊 Log and Track Issues

Monitor application health and identify recurring problems

## 🔍 Understanding Exceptions

**📘 Key Concept:** In .NET, an exception is more than just an error – it's an **object** that contains critical information about what went wrong during program execution.

When an unexpected event occurs (like dividing by zero, accessing a null reference, or trying to read a non-existent file), .NET creates an exception object with details about the error.

### Common Exception Triggers:

* `NullReferenceException` - Accessing an object that is null
* `ArgumentException` - Invalid method arguments
* `IOException` - Input/Output related errors
* `DivideByZeroException` - Mathematical division by zero
* `FormatException` - Invalid string conversion

## 💻 Exception Handling in Practice

### Bank Account Example

public class BankAccount
{
    public decimal Balance { get; private set; }

    public void Withdraw(decimal amount)
    {
        try
        {
            // Validate withdrawal conditions
            if (amount < 0)
                throw new ArgumentException("Withdrawal amount cannot be negative");

    if (amount > Balance)
                throw new InsufficientFundsException("Insufficient funds for withdrawal");

    Balance -= amount;
            Console.WriteLine($"Withdrawal successful. New balance: {Balance}");
        }
        catch (ArgumentException ex)
        {
            // Handle invalid input
            Console.WriteLine($"Input Error: {ex.Message}");
            LogError(ex);
        }
        catch (InsufficientFundsException ex)
        {
            // Handle specific banking scenario
            Console.WriteLine($"Transaction Failed: {ex.Message}");
            NotifyUser(ex.Message);
        }
        catch (Exception ex)
        {
            // Catch any unexpected exceptions
            Console.WriteLine($"Unexpected error: {ex.Message}");
            LogCriticalError(ex);
        }
        finally
        {
            // Always executed, useful for cleanup
            Console.WriteLine("Withdrawal process completed");
        }
    }
}

// Custom exception for specific banking scenario
public class InsufficientFundsException : Exception
{
    public InsufficientFundsException(string message) : base(message) { }
}

**💡 Code Breakdown:** This example shows how to handle specific exceptions differently, provide meaningful error messages, and ensure cleanup code always runs in the `finally` block.

## 🏆 Exception Handling Best Practices

#### 🎯 Be Specific

Catch specific exceptions before general ones. This allows for targeted error handling.

#### 📝 Provide Context

Include meaningful error messages that help users understand what went wrong.

#### 📊 Log Errors

Always log exceptions for debugging and monitoring application health.

#### 🏗️ Use Custom Exceptions

Create domain-specific exceptions when standard ones don't fit your business logic.

**⚠️ Critical Rule:** **Never swallow exceptions!** Don't catch exceptions without handling them properly. Empty catch blocks hide problems and make debugging impossible.

## 📚 Learning Resources

**💡 Study Strategy:** Start with the Microsoft documentation for comprehensive coverage, then explore best practices for professional development.

### 📖 Official Documentation

* **Fundamentals:** [Microsoft Docs: Exception Handling**Links to an external site.**](https://docs.microsoft.com/en-us/dotnet/standard/exceptions/) - Comprehensive guide to .NET exception handling
* **Language Reference:** [.NET Exception Handling Reference**Links to an external site.**](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/exception-handling-statements) - Syntax and language features
* **Professional Development:** [Best Practices for Exceptions**Links to an external site.**](https://learn.microsoft.com/en-us/dotnet/standard/exceptions/best-practices-for-exceptions) - Industry standards and guidelines

### 🔗 Related Course Materials

* [Debugging Essentials in C#](https://fhict.instructure.com/courses/15759/pages/debugging-essentials-in-c-number-identifying-and-fixing-code-errors) - Tools and techniques for finding and fixing errors
* [How to write effective unit tests?](https://fhict.instructure.com/courses/15759/pages/how-to-write-effective-unit-tests) - Testing exception scenarios

*Part of the Software Design & Engineering course | Fontys ICT*
