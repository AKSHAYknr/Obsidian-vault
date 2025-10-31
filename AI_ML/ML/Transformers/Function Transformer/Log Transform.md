
---
**Log Transformation** is a feature scaling and normalization technique where you apply the **logarithmic function** to numerical data to **reduce skewness** and **stabilize variance**.

It is commonly used to make data more **normally distributed**, which helps many machine learning models perform better.

---

### ⚙️ Formula

	x′=log⁡(x) 

or (to handle zeros)

	x′=log⁡(x+1)

_(This version is called `log1p` in NumPy — “log of one plus x”)_

---

### 🎯 Purpose

- To **reduce right skewness** (long tail on the right).
    
- To **handle large value ranges**.
    
- To **stabilize variance** and improve model performance.
    
- To make patterns more visible in data visualization.
    

---

### 🧩 When to Use

- When your numerical data has **positive skewness**.
    
- When features have **very large values** compared to others.
    
- When model assumptions (like linear regression) require **normally distributed errors**.
    

---

### 🚫 When Not to Use

- When data contains **zero or negative values** (since log is undefined for ≤ 0).
    
- For categorical or already-normalized data.

### 📊 Effect Example

|Original Value|After Log Transform|
|---|---|
|10|2.30|
|1000|6.90|
|100000|11.51|

→ Large differences shrink after transformation, reducing skew.

### 🧠 Key Point

Log transformation **compresses large values** and **expands small ones**, making distributions more balanced and model-friendly.