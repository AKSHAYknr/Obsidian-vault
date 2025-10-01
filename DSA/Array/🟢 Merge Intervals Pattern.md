
---
## **Pattern Overview**

The **Merge Intervals** pattern deals with problems involving **intervals or ranges**, where we need to combine, compare, or optimize overlapping intervals.

- Input usually comes as pairs `[start, end]`.
    
- Goal is often to **merge overlapping intervals**, **insert new intervals**, **find gaps**, or **count overlaps**.
    
- Sorting intervals by start time is almost always the first step.
    

---

## **How to Identify**

Look for problems that mention:

- A list of intervals (time slots, ranges, meetings, etc.)
    
- Overlapping intervals, conflicts, or gaps.
    
- Questions like:
    
    - Merge all overlapping intervals.
        
    - Insert a new interval and merge.
        
    - Count how many intervals overlap.
        
    - Find free time or gaps between intervals.
        

**Clues:**

- Input like `[[1,3],[2,6],[8,10],[15,18]]`
    
- Mention of “sort by start time” or “merge overlapping ranges.”
    

---

## **Steps / Common Approach**

1. **Sort intervals** by start time (`interval[0]`).
    
2. Initialize a result list with the first interval.
    
3. Iterate through intervals:
    
    - If the current interval **overlaps** with the last interval in the result:
        
        - Merge them: `last.end = max(last.end, current.end)`
            
    - Else:
        
        - Append the interval to the result list.
            
4. Return the merged intervals list.
    

**Time Complexity:**

- Sorting: `O(n log n)`
    
- Iteration: `O(n)`
    
- Total: `O(n log n)`

