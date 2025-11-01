
---
**Quantile Binning**, also called **Equal Frequency Binning**, is a _discretization technique_ that divides continuous data into bins such that **each bin contains (roughly) the same number of data points**.

Unlike **Uniform Binning**, the **range (width)** of each bin may vary — but the **number of samples per bin** remains approximately equal.

### ⚙️ How It Works

1. Sort all data values in ascending order.
    
2. Decide the **number of bins** (`n_bins`).
    
3. Split the data based on **quantiles (percentiles)** — for example:
    
    - 4 bins → quartiles (25%, 50%, 75%, 100%)
        
    - 10 bins → deciles (10%, 20%, …, 100%)
        
4. Assign each data point to a bin according to its quantile interval.
    

### 🧮 Example

For data:  
`[1, 2, 5, 6, 7, 9, 12, 15]` and `n_bins = 4`

Sorted values → `[1, 2, 5, 6, 7, 9, 12, 15]`

Since we want 4 bins, each bin will have **2 values** (8 ÷ 4 = 2):

|Bin|Range (approx.)|Values|
|---|---|---|
|1|1 – 2|[1, 2]|
|2|5 – 6|[5, 6]|
|3|7 – 9|[7, 9]|
|4|12 – 15|[12, 15]|

👉 Each bin has equal **frequency** (2 samples), but different **value ranges**.

### 📊 Key Points

- Each bin has **roughly the same number of samples**.
    
- **Bin widths are not uniform** — depend on data distribution.
    
- Handles **skewed data** better than uniform binning.
    
- Helps balance class representation in discretized features.