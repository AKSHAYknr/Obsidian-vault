
---
# 🔹 What is Exception Handling?

An **exception** is an **unexpected event** that occurs during program execution and disrupts normal flow.  
**Exception Handling** is the process of handling such events gracefully without crashing the program.

---

# 🔹 Why Use Exception Handling?

1. Prevent program from crashing.
    
2. Handle errors gracefully.
    
3. Separate error-handling code from normal code.
    
4. Provide meaningful error messages.
    

---

# 🔹 Types of Exceptions

### 1️⃣ **Checked Exceptions**

- Checked **at compile time**.
    
- Must be either **handled (try-catch)** or **declared with `throws`**.
    
- Example: `IOException`, `SQLException`, `ClassNotFoundException`.

### 2️⃣ **Unchecked Exceptions (Runtime Exceptions)**

- Occur **at runtime**.
    
- Not checked by compiler.
    
- Example: `NullPointerException`, `ArrayIndexOutOfBoundsException`, `ArithmeticException`.

### 3️⃣ **Errors**

- Serious problems beyond program control.
    
- Example: `OutOfMemoryError`, `StackOverflowError`.
    
- Should not be handled normally.

# 🔹 Exception Handling Keywords

1. **try** → block of code that may throw exception.
    
2. **catch** → handles the exception.
    
3. **finally** → block that always executes (cleanup code).
    
4. **throw** → used to explicitly throw an exception.
    
5. **throws** → declares exceptions a method might throw.