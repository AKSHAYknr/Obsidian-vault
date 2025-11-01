
---
**Uniform Binning**, also known as **Equal Width Binning**, is a _discretization technique_ used to convert continuous numerical values into discrete bins (intervals) of **equal width**.  
Each bin spans the same range of values, even if some bins contain more or fewer samples.
### ⚙️ How It Works

1. Determine the **minimum** and **maximum** value of the feature.
    
2. Decide the **number of bins** (`n_bins`).
    
3. Calculate the **bin width** using:
    
    Bin Width=(max−min) / n_bins
1. Divide the range into equal-width intervals (bins).
    
2. Assign each data point to its corresponding bin based on its value.

### 🧮 Example

For values:  
`[1, 2, 5, 6, 7, 9, 12, 15]` and `n_bins = 3`

- Range: `1 → 15`
    
- Bin width = `(15 - 1) / 3 = 4.67`
    

|Bin|Range|Values|
|---|---|---|
|1|[1.0, 5.67)|1, 2, 5|
|2|[5.67, 10.33)|6, 7, 9|
|3|[10.33, 15.0]|12, 15|

### 📊 Key Points

- Each bin has **equal range**, not equal number of samples.
    
- Works well for **numeric features** with uniform spread.
    
- Simple and fast to apply.
    
- May lead to **uneven bin densities** if data is skewed.

### 🧠 Use Cases

- Feature discretization for tree-based models
    
- Simplifying continuous variables for interpretability
    
- Creating grouped categories for visualization (e.g., histograms)