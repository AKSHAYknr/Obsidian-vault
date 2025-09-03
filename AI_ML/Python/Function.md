
---
## 🔹 What is a Function?

A **function** is a block of reusable code that performs a specific task.  
It helps in:

- Reducing code duplication
    
- Increasing readability
    
- Easier debugging and testing
## 🔹 Defining a Function

In Python, we use the `def` keyword:

```python
def function_name(parameters):
    """Optional docstring explaining the function"""
    # code block
    return result
```

## 🔹 Types of Functions in Python

1. **Built-in functions** → Already available in Python  
    Examples: `print()`, `len()`, `sum()`, `max()`, `min()`, `type()`
    
2. **User-defined functions** → Functions you create yourself
    
3. **Lambda functions (anonymous functions)** → Short, one-line functions
```python
square = lambda x: x * x
print(square(5))  # Output: 25
```

4. **Recursive functions** → A function that calls itself
```python
def factorial(n):
	if(n == 0 or n == 1):
		return 1
	else:
		return n * factorial(n-1)
		
print(factorial(5)) # output = 120
```
## 🔹 Function Parameters

```python
def add(num1, num2)
	return num1 + num2
	
print(add(2, 3)) # output = 5
```
