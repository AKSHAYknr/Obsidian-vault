
---
**Yeo–Johnson Transformation** is a **power transformation** similar to Box–Cox but more flexible — it can handle **both positive and negative values**.  
It helps make data **more normal**, **reduces skewness**, and **stabilizes variance**.

### 🎯 Purpose

- To **normalize data** (make it more Gaussian).
    
- To **reduce skewness** and **stabilize variance**.
    
- Works for datasets containing **zero or negative values**, unlike Box–Cox.
    

---

### ⚙️ When to Use

- When the data is **not normally distributed**.
    
- When the dataset contains **zero or negative values**.
    
- When you need to prepare data for algorithms sensitive to skewness (e.g., Linear Regression, PCA).
    

---

### 🚫 When Not to Use

- Rarely unsuitable — it’s a generalization of Box–Cox, so it works in most cases.
    
- Avoid if data has extreme outliers that may distort λ estimation.

### 📊 Example Effect

|Original|Yeo–Johnson (λ auto)|
|---|---|
|-5|-1.80|
|0|0.00|
|5|1.40|
|10|2.20|

→ Data becomes more symmetric and less skewed.

### 🧠 Key Point

Yeo–Johnson transformation is an **enhanced version of Box–Cox** that can handle **both positive and negative data**, making it a **versatile choice** for real-world datasets that aren’t perfectly clean.