
---
**Label Encoding** converts **categorical values (text labels)** into **numerical values** by assigning each unique category a **unique integer**.  
It is one of the simplest and most commonly used encoding techniques for categorical data.

---

### 🧠 **Concept**

Each category is mapped to an integer value:

|Color|Encoded|
|---|---|
|Red|0|
|Blue|1|
|Green|2|

This allows algorithms to process categorical values numerically.

---

### 🎯 **When to Use Label Encoding**

Use **Label Encoding** when:

- The categorical data is **ordinal** (has an inherent order).
    
- Or when using **tree-based models** (e.g., Decision Tree, Random Forest) that are not sensitive to numeric relationships between encoded values.