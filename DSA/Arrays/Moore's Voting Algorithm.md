
---

 Idea :

Used to find the **majority element** (element appearing more than `n/2` times) in an array — in **O(n)** time and **O(1)** space.

⚙️ Algorithm

1. **Select a candidate** and keep a **count**.
    
2. Traverse array:
    
    - If `count == 0`, pick new candidate.
        
    - If current element == candidate → `count++`
        
    - Else → `count--`
        
3. Candidate after traversal is the **potential majority**.
    
4. (Optional) Verify it actually appears > n/2 times.

⚙️ **Template** :

```java
public int majorityElement(int[] nums){
	int count = 0; int candidate = 0;
	for(int num : nums){
		if(count == 0){
			candidate = num;
			count++;
		}else if(candidate == num){
			count++;
		}else{
			count--;
		}
	}
	return candidate;
}
```

🕒 Complexity

- Time: O(n)
    
- Space: O(1)

🧮 Example Problems

[169. Majority Element](https://leetcode.com/problems/majority-element/)
