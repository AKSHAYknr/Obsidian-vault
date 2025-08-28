
---
## 1. **List**

- A **list** is a **mutable** (can be changed) ordered collection of items.
    
- Items can be of **different data types**.
    
- Defined using **square brackets `[]`**.

A **list** has many methods because it can be changed.

```python
my_list = [1,2,3,4]
```

### 🔹 Adding / Inserting

- `append(x)` → Adds element at the **end**
    
```python
my_list.append(5)  # [1, 2, 3, 2, 4, 5]
```
    
- `insert(i, x)` → Inserts at index `i`
    
```python
my_list.insert(1, 10)  # [1, 10, 2, 3, 2, 4, 5]
```
    
- `extend(iterable)` → Add multiple elements
    
```python
my_list.extend([6, 7])  # [1, 10, 2, 3, 2, 4, 5, 6, 7]
```

### 🔹 Removing

- `remove(x)` → Removes first occurrence of `x`
    
```python
my_list.remove(2)  # [1, 10, 3, 2, 4, 5, 6, 7]
```
    
- `pop([i])` → Removes and returns item at index (last if not specified)
    
```python
my_list.pop()  # removes 7 my_list.pop(2) # removes element at index 2
```
    
- `clear()` → Removes all elements
    
```python
my_list.clear()  # []
```

### 🔹 Searching & Counting

- `index(x)` → Returns index of first occurrence
    
```python
[10, 20, 30].index(20)  # 1
```
    
- `count(x)` → Counts occurrences of value
    
```python
[1, 2, 2, 3].count(2)  # 2
```

### 🔹 Sorting & Reversing

- `sort()` → Sorts list (ascending by default)
    
```python
nums = [3, 1, 4, 2] 
nums.sort()   # [1, 2, 3, 4]
nums.sort(reverse=True) # [4, 3, 2, 1]
```
    
- `reverse()` → Reverses list
    
```python
nums.reverse()
```

### 🔹 Copying

- `copy()` → Shallow copy of list
    
```python
new_list = nums.copy()
```

## 2. **Tuple**

- A **tuple** is an **immutable** (cannot be changed) ordered collection of items.
    
- Defined using **parentheses `()`**.
    
- Faster than lists and often used for **fixed data**.

A **tuple** has only **two methods** because it cannot be changed.

```python
my_tuple = (1, 2, 2, 3, 4)
```

- `count(x)` → Counts occurrences of `x`
    
```python
my_tuple.count(2)  # 2
```
    
- `index(x)` → Returns index of first occurrence
    
```python
my_tuple.index(3)  # 3
```

