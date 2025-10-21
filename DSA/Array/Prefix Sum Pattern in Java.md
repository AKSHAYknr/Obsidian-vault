
---
⚡ What is Prefix Sum?

A **Prefix Sum** stores **cumulative totals** of elements in an array, allowing you to find the **sum of any subarray in O(1)** time after an O(n) preprocessing step.

🧠 Formula:
prefix[i] = prefix[i - 1] + arr[i];

To get sum from index `l` to `r`:

sum = prefix[r] + prefix[l-1];

1️⃣ Basic Prefix Sum

```java
int[] arr = {2, 4, 5, 7, 8};
int[] prefix = new int[arr.length];
prefix[0] = arr[0];
for (int i = 1; i < arr.length; i++)
    prefix[i] = prefix[i - 1] + arr[i];

// Sum of [1..3]
int l = 1, r = 3;
int sum = prefix[r] - (l > 0 ? prefix[l - 1] : 0);
System.out.println(sum); // 16
```

[303. Range Sum Query - Immutable](https://leetcode.com/problems/range-sum-query-immutable/)

2️⃣ Subarray Sum Equals K (Prefix Sum + HashMap)

```java
 static int subarraySum(int[] nums, int k) {
        Map<Integer, Integer> map = new HashMap<>();
        map.put(0, 1);
        int count = 0, sum = 0;

        for (int num : nums) {
            sum += num;
            if (map.containsKey(sum - k))
                count += map.get(sum - k);
            map.put(sum, map.getOrDefault(sum, 0) + 1);
        }
        return count;
    }
```

[560. Subarray Sum Equals K](https://leetcode.com/problems/subarray-sum-equals-k/)

3. 2D Prefix Sum (Matrix)

```java
int m = mat.length, n = mat[0].length;
int[][] prefix = new int[m + 1][n + 1];
for (int i = 1; i <= m; i++)
    for (int j = 1; j <= n; j++)
        prefix[i][j] = mat[i-1][j-1] + prefix[i-1][j] + prefix[i][j-1] - prefix[i-1][j-1];

int r1 = 2, c1 = 1, r2 = 4, c2 = 3;
int sum = prefix[r2+1][c2+1] - prefix[r1][c2+1] - prefix[r2+1][c1] + prefix[r1][c1];
```

[304. Range Sum Query 2D - Immutable](https://leetcode.com/problems/range-sum-query-2d-immutable/)

