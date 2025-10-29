
---
Standardization is a **feature scaling technique** that transforms data so that each feature has:

- **Mean (μ) = 0**
    
- **Standard Deviation (σ) = 1**

It ensures that all features contribute **equally** to model training, especially for algorithms sensitive to feature magnitude (e.g., Linear Regression, SVM, KNN, PCA).

### 🧮 Formula

X′ = X−μ​​ / **σ**

Where:

- **X** = original feature value
    
- **μ** = mean of the feature
    
- **σ** = standard deviation of the feature
    
- **X'** = standardized value

### 📊 1. **Mean (μ) = 0**

- The **mean (μ)** is the _center_ of the distribution — where most values cluster.
    
- A mean of **0** means the data is centered around **zero**.
### 📈 2. **Standard Deviation (σ) = 1**

- The **standard deviation (σ)** measures _how spread out_ the data is.
    
- A σ of **1** means that about:
    
    - **68%** of data lies within 1 standard deviation of the mean (−1 to +1),
        
    - **95%** within 2 standard deviations (−2 to +2),
        
    - **99.7%** within 3 standard deviations (−3 to +3).

### 📈 When to Use

- When features have **different scales** or units
    
- For **distance-based algorithms** (KNN, SVM, PCA, Logistic Regression)
    
- When data is **normally distributed**

### ⚠️ When _Not_ to Use

- When using **tree-based models** (e.g., Decision Tree, Random Forest, XGBoost) — these are **scale-invariant**