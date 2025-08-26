
---
## **1. Opposite Ends (Start & End Pointers)**

Used for : Sorted arrays, finding pairs/sums, checking palindrome.

**Key Template :**

```java
int left = 0, int right = arr.length-1;
while(left < right){
	int sum = arr[left] + arr[right];
	if(sum == target){
		return new int[]{left, right};
	}else if(sum > target){
		right--;
	}else{
		left++;
	}
}
```

**LeetCode Problems :**

- [LC 167 . Two Sum || - Input array is sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
- [LC 125 . Valid Palindrome](https://leetcode.com/problems/valid-palindrome/description/)
- [LC 344. Reverse String](https://leetcode.com/problems/reverse-string/description/)

## **2. Same Direction (Sliding Window)**

Used for : Contiguous Subarrays, substrings, optimization problems.

**Key Template :**

```java
int left = 0, right = 0;
while(right < s.length()){
	// Expand the window
	window.add(s.charAt(right));
	right++;

	// Shrink the window when needed
	while(window condition not met){
		window.remove(s.charAt(left));
	}
	// Update result if needed
	result = Math.max(result , right - left);
}
```

**LeetCode Problems** :

- [LC 3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
- [LC 76. Minimum Window Substring](https://leetcode.com/problems/minimum-window-substring/description/)
- [LC 438. Find All Anagrams In A String](https://leetcode.com/problems/find-all-anagrams-in-a-string/description/)

## **3. Fast And Slow Pointers (Cycle Detection)**

Used for : Linked lists, cycle detection, middle of list.

**Key Template :**

```java
ListNode slow = head, fast = head;
while(fast != null && fast.next != null){
	slow = slow.next;
	fast = fast.next.next;
	if(slow == fast){
		return true; // cycle detected
	}
}
```

**LeetCode Problems :**

- [LC 141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/description/)
- [LC 876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)
- [LC 234. Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)

## **4. Partitioning (Dutch National Flag / In-place Swaps)**

Used for : Sorting 0s/1s/2s. partitioning arrays.

Key Template :

```java
int low = 0; mid = 0; high = arr.length-1;
while(mid <= high){
	if(arr[mid] == 0){
		swap(arr, low, mid);
		low++, mid++;
	}else if(arr[mid] == 1){
		mid++;
	}else{
		swap(arr, mid, high);
		high--;
	}
}
```

LeetCode Problems :

- [LC 75. Sort Colors](https://leetcode.com/problems/sort-colors/)
- [LC 283. Move Zeroes](https://leetcode.com/problems/move-zeroes/)
- [LC 26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

## **5.Merging Two Sorted Arrays / Lists**

Used For : Merge steps, sorted list manipulation.

**Key Template :**

```java
int i = 0, j = 0;
while(i < arr1.length && j < arr2.length){
	if(arr1[i] < arr2[i]){
		result.add(arr1[i++]);
	}else{
		result.add(arr2[j++]);
	}
}
```

LeetCode Problems :

- [LC 88. Merge Sorted Array](https://leetcode.com/problems/merge-sorted-array/)
- [LC 21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
- [LC 977. Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)


| **Pattern**              | **Use Case Examples**                                         |
| ------------------------ | ------------------------------------------------------------- |
| Opposite Ends            | Sorted arrays, <br>two-sum, palindrome check                  |
| Same Direction (Sliding) | Subarrays, <br>longest/shortest substrings                    |
| <br>Fast & Slow          | Cycles, <br>Middle node, Loop detection, <br>Palindrome check |
| Partitioning             | Dutch Flag, <br>Move Zeros, Deduplication                     |
| Merging                  | Combine sorted arrays or lists                                |
