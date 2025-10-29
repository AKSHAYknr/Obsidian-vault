
---
Pandas Profiling (renamed to **YData Profiling**) is an automated **Exploratory Data Analysis (EDA)** tool that generates an **interactive report** summarizing a dataset’s key statistics and patterns.
### 📊 What It Provides

- **Dataset overview:** shape, variable types, missing values
    
- **Variable statistics:** mean, std, unique values, zero counts
    
- **Correlations:** Pearson, Spearman, Kendall
    
- **Missing values heatmap**
    
- **Interactions:** scatter matrices between variables
    
- **Sample data preview**
    
- **Duplicate row detection**
    
- **Warnings:** alerts about skewness, high cardinality, etc.
    

### ⚡ Key Parameters

|Parameter|Description|
|---|---|
|`title`|Title of the generated report|
|`explorative`|Enables deeper analysis and visuals|
|`minimal=True`|Creates a lighter version of the report|
|`samples`|Number of rows to display in sample preview|

---

### 🧩 Tips

- Use in early EDA to get a **complete picture** of your data quickly.
    
- Works well with Pandas DataFrames.
    
- Can export to **HTML** for sharing with others.
    
- Restart Jupyter kernel if `ModuleNotFoundError` occurs after install.
    

---

### 📁 Example Workflow

1. Load dataset
    
2. Generate profiling report
    
3. Review summary statistics
    
4. Identify missing values/outliers
    
5. Use insights to guide further EDA or preprocessing