
---
### ✅ Pattern

- Initialize two pointers:
    
    - `left = 0` (start of array)
        
    - `right = n-1` (end of array)
        
- While `left < right`:
    
    - Perform checks/comparisons involving `arr[left]` and `arr[right]`
        
    - Move pointers inward depending on condition:
        
        - Increase `left` → when we need a larger value / to skip smaller ones
            
        - Decrease `right` → when we need a smaller value / to skip larger ones


```java
int left = 0, right = arr.length-1;
while(left < right){
	if(condition){
		//do the operation
		left++;
		right--;
	}
}
```

### 🧩 Common Problem Types

- **Sorted Array problems** (clue: "array is sorted")
    
- **Target Sum / Pair problems**
    
    - Example: "Find two numbers that sum to X"
        
- **Comparison from ends**
    
    - Example: Palindrome check in string/array
        
- **Min/Max value pairs**
    
    - Example: Container With Most Water
        
- **Removing/Skipping elements**
    
    - Example: Move zeros, remove duplicates (slight variation)

### 🧩 Common Problem Types

- **Sorted Array problems** (clue: "array is sorted")
    
- **Target Sum / Pair problems**
    
    - Example: "Find two numbers that sum to X"
        
- **Comparison from ends**
    
    - Example: Palindrome check in string/array
        
- **Min/Max value pairs**
    
    - Example: Container With Most Water
        
- **Removing/Skipping elements**
    
    - Example: Move zeros, remove duplicates (slight variation)
        

---

### 📌 Key Clues (when to apply two-pointers)

- Problem statement mentions **sorted array**
    
- Need to find **pair(s) or triplets** satisfying a condition
    
- Need to **compare leftmost and rightmost elements**
    
- Need to **shrink the search space** from both sides
    
- Asked to solve in **O(n)** instead of O(n²) (hint: two pointers reduce nested loops)
    

---

### ⚡ Example Problems

[167. Two Sum II - Input Array Is Sorted](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/)

[15. 3Sum](https://leetcode.com/problems/3sum/)

[16. 3Sum Closest](https://leetcode.com/problems/3sum-closest/)

[26. Remove Duplicates from Sorted Array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

[977. Squares of a Sorted Array](https://leetcode.com/problems/squares-of-a-sorted-array/)

---

### 📝 Notes

- If array is **unsorted** → consider sorting first (but note O(n log n)).
    
- Always check **duplicates** (common in sum problems).
    
- Can extend to **3 pointers** (like 3Sum) by fixing one pointer and applying two-pointers on the rest.