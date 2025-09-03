
---

# 🔹 **Why Loops?**

Loops let us **repeat a block of code** multiple times until a condition is met, or for every element in a collection.

# 🔹 **Types of Loops in Python**

## 1. **for loop**

Used to **iterate over a sequence** (list, tuple, string, range, dictionary, set, etc.).

### Example:

```python
# Loop through a list
fruits = ["apple", "banana", "mango"]
for fruit in fruits:
    print(fruit)

# Loop using range()
for i in range(5):  # 0,1,2,3,4
    print(i)
```

## 2. **while loop**

Runs until a **condition becomes False**.

### Example:

```python
count = 1
while count <= 5:
    print("Count:", count)
    count += 1
```

# 🔹 **Loop Control Statements**

|Statement|Meaning|
|---|---|
|`break`|Exit loop immediately|
|`continue`|Skip the current iteration, go to next|
|`pass`|Placeholder, does nothing (used to avoid syntax error)|
