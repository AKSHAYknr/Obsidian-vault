
---
### **1. 1D Prefix Sum - Subarray Sum**

Used to compute sum of subarrays in constant time.

**Key Template :**

```java
int[] prefix = new int[n];
prefix[0] = arr[0];
for(int i = 1; i < n; i++){
	prefix[i] = prefix[i - 1] + nums[i];
}
// subarray sum of [l..r] = prefix[r] - prefix[l-1]
```

**LeetCode Problems :**

- [LC 560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)
- [LC 724. Find Pivot Index](https://leetcode.com/problems/find-pivot-index/)
- [LC 303. Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/)

### **2. Prefix Sum with HashMap - Subarrays with target sum**

Used when tracking count of sums up to current index for any subarray with given sum

**Key Template :**

```java
Map<Integer, Integer> map = new HashMap<>();
map(0, 1);
int sum = 0, count = 0;
for(int num : nums){
	sum += num;
	if(map.containsKey(sum - k)){
		count += map.get(sum - k);
	}
	map.put(sum, map.getOrDefault(sum, 0) + 1);
}
```

**LeetCode Problems :**

- [LC 560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)
- [LC 974. Subarray Sums Divisible by K](https://leetcode.com/problems/subarray-sums-divisible-by-k/)
- [LC 523. Continuous Subarray Sum](https://leetcode.com/problems/continuous-subarray-sum/)
- [LC 525. Contiguous Array](https://leetcode.com/problems/contiguous-array/)
