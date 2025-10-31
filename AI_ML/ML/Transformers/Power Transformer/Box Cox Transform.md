
---
**Box-Cox Transformation** is a **power transformation** used to make data **more normally distributed** by stabilizing variance and reducing skewness.  
It applies a mathematical function parameterized by a value λ\lambdaλ (lambda).

### 🎯 Purpose

- To **reduce skewness** and make data **more Gaussian (normal)**.
    
- To **stabilize variance** across different ranges.
    
- To improve model performance, especially for linear regression and parametric models.
    

---

### ⚙️ When to Use

- When your data is **positively skewed**.
    
- When all feature values are **strictly positive (x > 0)**.
    
- When you want to **normalize continuous numerical data** before modeling.
    

---

### 🚫 When Not to Use

- If data contains **zero or negative values** → Box-Cox cannot handle them.
    
- Use **Yeo-Johnson** transformation instead (it supports negative values).

### 📊 Example Effect

|Original|Box-Cox (λ auto)|
|---|---|
|1|0.00|
|2|0.77|
|3|1.15|
|10|2.30|

→ Large values are compressed, and small values are slightly expanded — reducing right skew.

---

### 🧠 Key Point

Box-Cox transformation **learns the best power (λ)** automatically to make data as close to a **normal distribution** as possible — ideal for improving the performance of algorithms that assume normality.