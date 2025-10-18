
---
### 1. **Fixed-size window**

- The window size is **constant**.
    
- Typically used when you must consider **every subarray (or substring)** of a **specific length `k`**.
    

📘 **Common Use Cases:**

- Maximum/minimum/average sum of subarray of size `k`
    
- Find first negative/positive number in every window of size `k`

🧮 **Pattern template:**

```java
int left = 0;
int right = 0
while(right < nums.length) {
    // expand window
    // when window size reached k
    if (right - left + 1 == k) {
        // process the window (e.g., max, sum, etc.)
        // slide the window ahead
        left++;
    }
    right++;
}
```

[643. Maximum Average Subarray I](https://leetcode.com/problems/maximum-average-subarray-i/)

[1004. Max Consecutive Ones III](https://leetcode.com/problems/max-consecutive-ones-iii/)

### 2. **Dynamic (Variable-size) window**

- The window size **changes dynamically** based on a condition.
    
- You expand the window by moving `end` and **shrink** it from the left (`start`) when a condition is violated.


📘 **Common Use Cases:**

- Longest substring/subarray meeting a condition
    
- Smallest subarray meeting a condition
    
- Distinct characters or sum constraints


🧮 **Pattern template:**

```java
int left = 0;
int right = 0;
while(right < nums.length){
    // expand window with arr[right]
    
    while (/* condition violated */) {
        // shrink from left
        start++;
    }

    // check/update answer
}
```

[209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)

[845. Longest Mountain in Array](https://leetcode.com/problems/longest-mountain-in-array/)

[674. Longest Continuous Increasing Subsequence](https://leetcode.com/problems/longest-continuous-increasing-subsequence/)



