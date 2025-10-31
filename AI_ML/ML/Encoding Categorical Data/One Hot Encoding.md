
---
**One-Hot Encoding** is a categorical encoding technique that converts **categorical values into binary (0/1) columns**, where each category is represented as a separate feature (column).

This ensures that there is **no ordinal relationship** between categories — all are treated equally.

---

### 🧠 **Concept**

|Color|Red|Blue|Green|
|---|---|---|---|
|Red|1|0|0|
|Blue|0|1|0|
|Green|0|0|1|
|Blue|0|1|0|

Each original category is transformed into a **new column** with `1` indicating presence and `0` absence.

---

### 🎯 **When to Use**

Use **One-Hot Encoding** when:

- The categorical variable is **nominal** (no inherent order between categories).  
    Examples:
    
    - Gender → Male, Female
        
    - Color → Red, Blue, Green
        
    - Country → India, USA, UK
        
- The model is **linear or distance-based** (e.g., Linear Regression, Logistic Regression, KNN, SVM).