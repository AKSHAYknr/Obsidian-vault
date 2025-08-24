
---
### **1. Fixed Size Sliding Window**

Used when the window size is fixed/constant - *maximum subarray of k-length subarray*.

**Key Features:**

- Two pointers (==start== and ==end==).

- Window size is always ==k==.

- Ideal for sums, average, max/min.

**Template:**

```java
public int fixedWindow(int[] nums, int k){
	int maxSum = 0, windowSum = 0;

	for(int i = 0; i < nums.length; i++){
		windowSum += nums[i];

		if(i >= k - 1){
			maxSum = Math.max(maxSum, windowSum)
			windowSum -= nums[i - k + 1];
		}
	}
	return maxSum;
}
```


---

### **2. Variable-Size Sliding Window (Shrinking Window)**

Used when the window size changes based on constraints - *smallest substring with x property*.

**Key Features**

- Expand right until condition met.

- Shrink left while still meeting condition.

- Often requires a HashMap or a frequency array.

**Template:**

```java
public int variableWindow(String s) {
	Map<Character, Integer> window = new HashMap<>();
	int left = 0, right = 0;
	int result = Integer.MAX_VALUE;

	while(right < s.length()){
		char c = s.charAt(right);
		window.put(c, window.getOrDefault(c, 0) + 1);
		right++;

		while(/* condition satisfied */){
			result = Math.min(result, right - left);

			// shrink the window
			char leftChar = s.charAt(left);
			window.put(leftChar, window.get(leftChar) - 1);
			if(window.get(leftChar) == 0) window.remove(leftChar);
			left++;
		}
	}
	return result == Integer.MAX_VALUE ? 0 : result;
}
```


|                                                              **Problem**                                                              |                                    **Description**                                     |        **Pattern**        |
| :-----------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------: | :-----------------------: |
|                      [LC 76. Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/)                       |       Find smallest substring which is having all the chars from another string.       | Variable window + HashMap |
| [LC 3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/) |                 Find the longest substring without repeating letters.                  | Variable window + HashMap |
|                         [LC 567. Permutation in String](https://leetcode.com/problems/permutation-in-string/)                         | Given two strings check if the permutation of first string available in second string. |  Fixed window + HashMap   |
|                 [LC 438. Find All Anagrams in a String](https://leetcode.com/problems/find-all-anagrams-in-a-string/)                 |     Given two strings p, s return all the starting indices of anagrams of p in s.      |  Fixed window + HashMap   |
|                     [LC 209. Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)                     |        Return the minimal length subarray whose sum is equal to a given target.        |      Variable window      |

