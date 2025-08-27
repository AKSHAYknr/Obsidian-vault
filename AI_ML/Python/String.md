
---

A string in python is a sequence of characters, string is normally initialized using single quote (' '), double quotes (" "), and triple quotes to print multiple lines(""" """). **Strings are immutable that is once created its contents cannot be modified**.

**Creating a string :**

```python
str = 'akshay'
str1 = "akshay"
str2 = """Hi my name is akshay,
		Iam a software engineer."""	
```

### 🔹 What is string slicing?

Slicing in Python lets you extract parts of a string (substring) using **index ranges**.

**Indexing :**

```
Forward:   0   1   2   3   4   5
           P   Y   T   H   O   N
Backward: -6  -5  -4  -3  -2  -1
```

**To find the length of a string :**

```python
text = "Python"
print(len(text))   # 6
```

**Slicing syntax :**

```
sl = name[ind_start, ind_end]
```

```python
str = "Akshay"
print(str[0:3]) # return Aks
print(str[1:3]) # return ks
print(str[0:-1]) # return Akshay, negetive slicing
print(str[:4]) # is same as print(str[0:4])
print(str[-4:-1]) #is same as print(str[2:5])
```

**Slicing with step :**

```python
str = "HelloWorld"
print(str[0:6:2]) # the last parameter is step, so it will jump.
```

1. Case conversion
    

```python
print(s.upper())   # "  HELLO WORLD  " 
print(s.lower())   # "  hello world  "
```

2. Remove spaces from both ends
    

```python
print(s.strip())   # "Hello World"
```
   
3. EndsWith
	

```python
str = "hello"
str.endsWith("llo") # tells if the string ends with "llo" if yes return true
```

4. Count
	

```python
str = "akshay"
print(str.count(a)) # count the given character in a string
```

5. Capitalize
	

```python
str = "akshay"
print(str.capitalize()) # capitalize first character of a given string
```

6. Find
	

```python
s = "hello world"
index = s.find(world) # return the starting index of the searched word
```

7. Replace
	

```python
s = "hello world"
replaced_string = s.replace("world", "python") # replace old word with given word
```



