
---
`ColumnTransformer` is a powerful **data preprocessing tool** in **scikit-learn** that allows you to **apply different transformations to different columns** of your dataset in a single step.

It’s especially useful when working with **mixed data types** — such as numerical and categorical features — which need different preprocessing techniques (like scaling and encoding).

### 🧠 **Purpose**

Different columns often require different preprocessing:

|Feature Type|Example|Transformation|
|---|---|---|
|Numerical|Age, Salary|Scaling (Standardization / Normalization)|
|Categorical|Gender, Country|Encoding (One-Hot / Ordinal)|

Instead of applying these transformations separately, you can use **ColumnTransformer** to do all of them together — neatly and efficiently.

**Parameters:**

- `transformers`: list of tuples, each containing:
    
    1. Name (string)
        
    2. Transformer object (like `OneHotEncoder()`, `StandardScaler()`, etc.)
        
    3. Columns to apply on (list or index)
        
- `remainder`:
    
    - `'drop'` (default) → removes unlisted columns
        
    - `'passthrough'` → keeps them unchanged

### 📊 **Result**

After transformation:

- The `'Country'` column → becomes 3 one-hot encoded columns
    
- `'Age'` and `'Salary'` → become standardized
    
- Other columns (if any) → passed through (unchanged)