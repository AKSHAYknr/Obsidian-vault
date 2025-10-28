
---
EDA is the process of **understanding your dataset** before modeling.  
You:

- Explore the structure, patterns, and relationships in data.
    
- Detect anomalies, missing values, or outliers.
    
- Summarize key statistics.
    
- Visualize trends.
    

## 🔹 **1. Univariate Analysis**

**Definition:**  
It means analyzing **one variable at a time** to understand its **distribution, range, and behavior**.

**Goal:**  
To understand what values a variable can take and how frequently.

### 🔸 Types

1. **Numerical Variables (Continuous or Discrete)**
    
    - Examples: `age`, `salary`, `temperature`
        
    - **Techniques:**
        
        - 📊 **Histogram** – to see data distribution.
            
        - 📈 **Boxplot** – to detect outliers.
            
        - 📉 **Density Plot / KDE Plot** – to see smooth distribution curve.
            
        - 📋 **Descriptive statistics** – mean, median, mode, variance, std. deviation, min, max.
            
    
    **Example insights:**
    
    - Is `salary` normally distributed or skewed?
        
    - Are there any outliers in `age`?
        
2. **Categorical Variables**
    
    - Examples: `gender`, `department`, `city`
        
    - **Techniques:**
        
        - 🧮 **Frequency table / value counts**
            
        - 📊 **Bar chart / countplot** – to show frequency of each category.
            
        - 🥧 **Pie chart** – to show proportion of categories.
            
    
    **Example insights:**
    
    - What percentage of employees are male vs female?
        
    - Which department has the highest number of people?
        

## 🔹 **2. Bivariate Analysis**

**Definition:**  
It means analyzing **two variables together** to understand **relationships** or **correlations** between them.

**Goal:**  
To see how one variable affects or is related to another.

### 🔸 Types (based on variable types)

|Variable 1|Variable 2|Common Methods|Example|
|---|---|---|---|
|Numerical|Numerical|Scatter plot, correlation coefficient, regression line|Height vs Weight|
|Categorical|Numerical|Box plot, Violin plot, Bar chart (mean of num var by category)|Gender vs Salary|
|Categorical|Categorical|Cross-tabulation, Stacked bar chart, Heatmap|Department vs Gender|

### 🔸 Examples

1. **Numerical vs Numerical**
    
    - Plot a **scatter plot** to see relationship.
        
    - Calculate **correlation (Pearson, Spearman)**.
        
    - Example: Is `experience` positively correlated with `salary`?
        
2. **Categorical vs Numerical**
    
    - Use **boxplot or violin plot**.
        
    - Example: Compare average `income` by `education level`.
        
3. **Categorical vs Categorical**
    
    - Use **contingency tables** or **stacked bar charts**.
        
    - Example: Relationship between `gender` and `purchased_product`.
        

## 🧩 Summary Table

|Type|Variables|Goal|Examples|Visualization|
|---|---|---|---|---|
|**Univariate**|1|Understand distribution|`age`, `gender`|Histogram, Countplot, Boxplot|
|**Bivariate**|2|Find relationships|`salary vs experience`, `gender vs income`|Scatter, Boxplot, Heatmap|

## ⚡ Practical Tip

- Always start with **Univariate Analysis** (understand each column).
    
- Then move to **Bivariate Analysis** (see how columns interact).
    
- Finally, use **Multivariate Analysis** (3+ variables) if needed — like pair plots or regression.