
---
Binary Search is an efficient algorithm to **find a target element in a sorted array** by repeatedly dividing the search space in half.  
It has a **time complexity of O(log n)**.

### ⚙️ **When to Use**

✅ The array (or search space) must be **sorted**.  
✅ You need to **find an element** or **determine if it exists** efficiently.  
✅ Often used in searching, optimization, and decision problems.

```java
int binarySearch(int[] nums, int target) {
    int left = 0;
    int right = nums.length - 1;

    while (left <= right) {
        int mid = left + (right - left) / 2;

        if (nums[mid] == target) {
            return mid; // Target found
        } else if (nums[mid] < target) {
            left = mid + 1; // Search right half
        } else {
            right = mid - 1; // Search left half
        }
    }

    return -1; // Target not found
}
```



