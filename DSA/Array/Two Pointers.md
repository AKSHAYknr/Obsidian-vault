
---
#### 🔁 **Opposite-End Two Pointer Pattern**

💡 **Idea**

Use **two pointers** starting from **opposite ends** of a collection (usually a **sorted array** or **string**) and move them **toward each other** based on some condition.

⚙️ **Template** :

```java
int left = 0;
int right = arr.length - 1;

while (left < right) {
    // Do some work with arr[left] and arr[right]

    if (condition) {
        left++;
    } else {
        right--;
    }
}
```

🧮 Example Problems

- [ ] [167. Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)
- [ ] [11. Container With Most Water](https://leetcode.com/problems/container-with-most-water/)
- [ ] [125. Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)
- [ ] [344. Reverse String](https://leetcode.com/problems/reverse-string/)
- [ ] [15. 3Sum](https://leetcode.com/problems/3sum/)

⚡ **Time Complexity:** `O(n)`

💾 **Space Complexity:** `O(1)`

### 💬 Tip

Use **Opposite-End Two Pointers** when you can leverage **sorted order**  
or **symmetry** to efficiently reduce the search range from both ends.


---

 #### 🧠 DNF Sorting Algorithm (Dutch National Flag)

💡 **Idea**

Used to **sort arrays with three categories** (e.g., 0s, 1s, 2s) using **three pointers** — `low`, `mid`, and `high`. Partition given array into two parts using `low` and `high` pointer.

⚙️ Template :

```java
int low = 0, mid = 0, high = arr.length - 1; 
while (mid <= high) {     
	if (arr[mid] == 0) 
		swap(arr, low++, mid++);     
	else if (arr[mid] == 1) 
		mid++;     
	else 
		swap(arr, mid, high--); }
```


```java
int low = 0; int high = 0;
while(high < nums.length){
	if(nums[high] % 2 == 0){ // condition based on question
		swap(arr, low, high)
		low++;
	}
	high++;
}
```


⚡ **Time Complexity:** `O(n)`

💾 **Space Complexity:** `O(1)`

🧮 Example Problems

[75. Sort Colors](https://leetcode.com/problems/sort-colors/)

[905. Sort Array By Parity](https://leetcode.com/problems/sort-array-by-parity/)

[26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

[283. Move Zeroes](https://leetcode.com/problems/move-zeroes/)


💡 When to Use

When elements fall into **three groups** (e.g., small/mid/large, 0/1/2).


---


