
---

# 🔹 **Dictionaries in Python**

A **dictionary** is a collection of **key-value pairs**.  
It is **unordered (Python 3.6+ maintains insertion order), mutable, and indexed by keys**.

```python
# Creating a dictionary
student = {
    "name": "Akshay",
    "age": 24,
    "course": "Python"
}

print(student["name"])      # Access by key → Akshay
print(student.get("age"))   # Safer way to access → 24
```

### ⚡ Features:

- **Keys** must be unique and immutable (string, number, tuple).
    
- **Values** can be anything (list, dict, int, etc).
    
- Supports fast lookups by key.

# ✅ Summary Table

|Method|Description|
|---|---|
|`dict.get(key,default)`|Returns value if key exists, else default|
|`dict.keys()`|Returns all keys|
|`dict.values()`|Returns all values|
|`dict.items()`|Returns list of (key, value) pairs|
|`dict.update({...})`|Updates or adds multiple items|
|`dict.pop(key)`|Removes key and returns its value|
|`dict.popitem()`|Removes last inserted key-value|
|`dict.clear()`|Empties dictionary|
|`dict.copy()`|Shallow copy|
|`dict.fromkeys(keys, value)`|Creates dict with given keys and same default value|
|`dict.setdefault(key, default)`|Gets value, inserts default if key not found|

# 🔹 **Sets in Python**

A **set** is an **unordered collection of unique elements**.  
It is mutable but does **not allow duplicates**.

```python
# Creating sets
numbers = {1, 2, 3, 4, 4, 5}
print(numbers)   # {1, 2, 3, 4, 5} → duplicates removed

empty_set = set()   # ✅ Correct way
```

### ⚡ Features:

- No duplicate elements.
    
- Unordered (no indexing).
    
- Very fast membership checking.

# 📘 **Python Set Methods – Summary Table**

|Method|Description|
|---|---|
|**add(x)**|Adds element `x` to the set|
|**update(iterable)**|Adds multiple elements from another iterable (list, set, tuple, etc.)|
|**remove(x)**|Removes element `x`; **raises error** if not found|
|**discard(x)**|Removes element `x`; **no error** if not found|
|**pop()**|Removes & returns a random element|
|**clear()**|Removes all elements (empty set)|
|**union(other)** / `a \| b`|Returns a new set with elements from both sets|
|**intersection(other)** / `a & b`|Returns common elements of both sets|
|**difference(other)** / `a - b`|Returns elements in first set but not in second|
|**symmetric_difference(other)** / `a ^ b`|Returns elements in either set but not both|
|**intersection_update(other)**|Keeps only common elements (updates in-place)|
|**difference_update(other)**|Removes elements of another set from current set|
|**symmetric_difference_update(other)**|Keeps only non-common elements (updates in-place)|
|**issubset(other)**|Checks if current set is a subset of another|
|**issuperset(other)**|Checks if current set is a superset of another|
|**isdisjoint(other)**|Checks if two sets have no elements in common|
|**copy()**|Returns a shallow copy of the set|