
---
**Reciprocal Transformation** is a mathematical transformation where each value xxx in the dataset is replaced with its **reciprocal (1/x)**.  
It is used to **reduce right skewness** and **handle large numeric ranges** similar to log transformation.

	x′ = 1 / x

### 🎯 Purpose

- To **reduce right-skewed distributions**.
    
- To **compress large values** and **spread smaller ones**.
    
- To make relationships more **linear** for regression-based models.

### ⚙️ When to Use

- When data is **positively skewed** (long tail on the right).
    
- When data values are **strictly positive and nonzero**.
    
- When large values dominate the dataset.

### 🚫 When Not to Use

- When data contains **zeros or negative values** (since 1/0 and 1/negative are invalid for most modeling cases).
    
- When the scale of data is already normalized.

### 📊 Example Effect

|Original|Reciprocal (1/x)|
|---|---|
|1|1.00|
|2|0.50|
|10|0.10|
|100|0.01|

→ Large values shrink significantly, helping normalize the distribution.

### 🧠 Key Point

Reciprocal transformation **inverts the scale of values**, giving more weight to smaller observations and helping correct **right-skewed** distributions — but must be used carefully to avoid division errors.