
---
**Definition:**  
Min-Max Scaling (also called **Normalization**) rescales features to a fixed range — usually **[0, 1]** — without changing the shape of the distribution.

### 📘 **Formula**

	X′= (X−Xmin​​) / (Xmax​−Xmin)​ 

Where:

- XXX = Original value
    
- XminX_{min}Xmin​ = Minimum value of the feature
    
- XmaxX_{max}Xmax​ = Maximum value of the feature
    
- X′X'X′ = Scaled value (between 0 and 1)

### 🎯 **Purpose**

- To ensure all features contribute **equally** to the model.
    
- Prevents large-scale features (like salary or income) from dominating small-scale ones (like age or ratings).
    
- Commonly used in **neural networks** and **distance-based algorithms** (e.g., KNN, K-Means).

### 🧩 **Example**

|Age|Salary|
|---|---|
|20|20,000|
|40|80,000|
|60|120,000|

For Age = 40:

(40−20)/(60−20)=0.5(40 - 20) / (60 - 20) = 0.5(40−20)/(60−20)=0.5

For Salary = 80,000:

(80000−20000)/(120000−20000)=0.6(80000 - 20000) / (120000 - 20000) = 0.6(80000−20000)/(120000−20000)=0.6

✅ Normalized values → Age = 0.5, Salary = 0.6

### ⚖️ **Key Points**

- Output range: **[0, 1]** (can be customized with `feature_range=(a, b)` in scikit-learn).
    
- Sensitive to **outliers** — extreme values can compress other values near 0.
    
- Use when you know **min and max** values or data is bounded.