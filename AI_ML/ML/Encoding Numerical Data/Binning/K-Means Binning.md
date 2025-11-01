
---
**K-Means Binning** (or **Clustering-based Discretization**) is a method that uses the **K-Means clustering algorithm** to group continuous data into discrete bins.

Instead of dividing data by equal width or equal frequency, K-Means Binning creates **bins based on data similarity** — each bin corresponds to one cluster.

### ⚙️ How It Works

1. Choose the number of bins `k` (same as number of clusters).
    
2. Run the **K-Means clustering** algorithm on the feature values.
    
3. The algorithm finds `k` cluster centroids and assigns each data point to the **nearest centroid**.
    
4. Each cluster forms a **bin** — values within the same cluster belong to the same discrete interval.
    

### 🧮 Example

Given data:  
`[1, 2, 5, 6, 7, 9, 12, 15]` and `k = 3`

After applying K-Means:

- Cluster 1 → `[1, 2]`
    
- Cluster 2 → `[5, 6, 7, 9]`
    
- Cluster 3 → `[12, 15]`
    

So, the bins are formed **based on natural groupings in the data**, not fixed width or quantiles.

### 📊 Key Points

- Bins are **formed by clusters**, not fixed ranges or quantiles.
    
- Works well for **non-linear** or **multi-modal** data distributions.
    
- More **data-driven** and **adaptive** than Uniform or Quantile binning.
    
- May produce **uneven bin sizes** depending on data spread.