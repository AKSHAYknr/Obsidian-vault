
---
### 🏷️ Definition

Unsupervised Learning is a type of **machine learning** where the model is trained on **unlabeled data** — meaning there are **no predefined outputs (Y)**.  
The system tries to find **patterns, relationships, or structures** within the data on its own.

### 🎯 Goal

To **discover hidden patterns**, **group similar data points**, or **reduce data dimensions** for better understanding or visualization.

### 🧩 How It Works

- Input data is provided **without labels**.
    
- The algorithm tries to:
    
    - **Cluster** similar data points together, or
        
    - **Reduce dimensions** while preserving essential information.
  
### 🧠 Types of Unsupervised Learning

#### 1️⃣ Clustering

Grouping data points based on similarity.  
📌 **Examples:**

- Customer segmentation (grouping customers by purchasing behavior)
    
- Document clustering (grouping news articles by topic)
    

📘 **Common Algorithms:**

- K-Means Clustering
    
- Hierarchical Clustering
    
- DBSCAN (Density-Based Spatial Clustering)
    
- Gaussian Mixture Models (GMM)
    

---

#### 2️⃣ Association

Finds relationships or rules among variables in large datasets.  
📌 **Examples:**

- Market basket analysis (if a customer buys X, they often buy Y)
    
- Recommendation systems
    

📘 **Common Algorithms:**

- Apriori Algorithm
    
- FP-Growth Algorithm
    

---

#### 3️⃣ Dimensionality Reduction

Reduces the number of features while keeping important patterns intact.  
📌 **Examples:**

- Data visualization in 2D/3D
    
- Noise reduction before supervised learning
    

📘 **Common Techniques:**

- Principal Component Analysis (PCA)
    
- t-SNE (t-Distributed Stochastic Neighbor Embedding)
    
- Autoencoders
    

---

### ⚙️ Steps in Unsupervised Learning

1. **Data Collection**
    
2. **Data Preprocessing**
    
    - Handle missing values
        
    - Normalize or scale features
        
3. **Choose Algorithm Type (Clustering / Association / Reduction)**
    
4. **Train Model**
    
5. **Analyze and Interpret Patterns**
    

---

### 📊 Example — Clustering Customers

|Customer|Age|Income|Spending Score|
|---|---|---|---|
|A|25|40K|80|
|B|40|70K|20|
|C|23|38K|75|

➡️ The model groups **A** and **C** as one cluster (young, high-spending) and **B** in another.

---

### 📈 Evaluation Metrics

Unsupervised models don’t have true labels, so evaluation is based on internal measures:

|Metric|Description|
|---|---|
|Silhouette Score|Measures how similar a point is to its own cluster vs other clusters|
|Davies–Bouldin Index|Measures cluster separation|
|Inertia (for K-Means)|Measures how tight clusters are|

---

### 💡 Advantages

✅ Can work without labeled data  
✅ Finds hidden patterns humans might miss  
✅ Useful for exploratory data analysis