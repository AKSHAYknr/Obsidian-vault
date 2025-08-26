
---

## 1. What is Python?

- Python is a popular, high-level programming language.
    
- It’s known for its easy-to-read syntax and versatility.
    
- Used in web development, data analysis, automation, AI, and more.
    

---

## 2. Python Syntax

- Python uses indentation (spaces) to define blocks of code (no curly braces { } like in some other languages).
    
- Every line that is “inside” something (like a function or a loop) is indented, usually with 4 spaces.

```python
if 5 > 3:
	print("5 is greater than 3")
	
```


---
## 3. Variables

- Variables store information.
    
- You don’t need to declare the type; Python figures it out.

```python
x = 10 # integer 
name = "Sam" # string (text) 
pi = 3.14 # float (decimal) 
is_happy = True # boolean (True/False)
```


---

## 4. Printing Output

- Use the `print()` function to display output.

```python
name = "akshay"
print(name)
```

---

## 5. Data Types

Python has several built-in data types. Here are the common ones you'll use often:

- **int**: Integer numbers (e.g., 5, -3)
    
- **float**: Decimal numbers (e.g., 3.14, -0.001)
    
- **str**: Strings or text (e.g., "Hello", 'Python')
    
- **bool**: Boolean values (True or False)
    

You can check the type of a variable using the `type()` function:

```python
x = 10
print(type(x))
```

---
## 6. Taking User Input

Use the `input()` function to get input from the user (it always returns a string).

```python
name = input("Enter your name : ")
print("Hello " + name)
```

If you want a number from the user, convert the input string to an integer or float:

```python
age = int(input("Enter your age"))
print("You are", age, "old")
```

---
## 7. Basic Operations

You can perform operations on numbers and strings, such as:

- Arithmetic: `+`, `-`, `*`, `/`, `//` (floor division), `%` (modulus), `**` (power)
    
- String concatenation: `"Hello " + "World"`
    
- Repeating strings: `"Hi" * 3` (outputs "HiHiHi")

