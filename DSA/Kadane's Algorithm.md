
---
💡 Intuition

- At each index, decide whether to:
    
    - **Extend** the current subarray (if current sum + element > element)
        
    - **Start a new subarray** from the current element (if element > current sum + element)
        
- Keep track of the **maximum sum seen so far**.

Essentially:  
👉 "If the running sum becomes negative, drop it and start fresh."

⚙️ Algorithm :

```java
public int maxSubArray(int[] nums) {
    int currSum = nums[0];
    int maxSum = nums[0];
    
    for (int i = 1; i < nums.length; i++) {
        currSum = Math.max(nums[i], currSum + nums[i]);
        maxSum = Math.max(maxSum, currSum);
    }
    return maxSum;
}
```

📈 Time & Space Complexity

- **Time:** O(n)
    
- **Space:** O(1)

[53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)

