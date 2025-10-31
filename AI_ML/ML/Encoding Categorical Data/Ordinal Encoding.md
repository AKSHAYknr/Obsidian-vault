
---
**Ordinal Encoding** is a categorical encoding technique where **each category is assigned a unique integer value** based on its **order or ranking**.  
It is used when categorical variables have a **natural order or hierarchy** between their categories.

---

### 🧠 **Formula / Concept**

Each category → assigned a number that reflects its **rank**.

Example:

|Size|Encoded|
|---|---|
|Small|1|
|Medium|2|
|Large|3|

Here, the numbers **1 < 2 < 3** indicate that _Large_ > _Medium_ > _Small_ in size or importance.

---

### 🎯 **When to Use Ordinal Encoding**

Use **Ordinal Encoding** when:

- The categorical feature has a **meaningful order** or **ranking** between categories.
    
- The distance between categories **matters or implies progression**.
    
- You want the model to **capture the relationship** between ordered categories.