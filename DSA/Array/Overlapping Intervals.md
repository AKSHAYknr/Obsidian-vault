
---
Intervals problems often involve sorting by start (or end) time, then merging, detecting overlaps, or inserting in the correct position.

#### 1.Merge Intervals


```java
public int[][] mergeIntervals(int[][] intervals) {
    Arrays.sort(intervals, (a, b) -> a[0] - b[0]); // sort by start
    List<int[]> merged = new ArrayList<>();
    merged.add(intervals[0]);

    for (int i = 1; i < intervals.length; i++) {
        int[] curr = intervals[i];
        int[] last = merged.get(merged.size() - 1);

        if (last[1] >= curr[0]) { // overlap exists
            last[1] = Math.max(last[1], curr[1]);
        } else { // no overlap
            merged.add(curr);
        }
    }

    return merged.toArray(new int[merged.size()][]);
}
```

[56. Merge Intervals](https://leetcode.com/problems/merge-intervals/)

#### 2.Insert Interval


```java
class Solution {
    public int[][] insert(int[][] intervals, int[] newInterval) {
	    //If not in sorted order, sort by start time
    
        List<int[]> result = new ArrayList<>();
        int i = 0, n = intervals.length;

        // 1️⃣ Add all intervals that end before the new interval starts
        while (i < n && intervals[i][1] < newInterval[0]) {
            result.add(intervals[i]);
            i++;
        }

        // 2️⃣ Merge all intervals that overlap with the new interval
        while (i < n && intervals[i][0] <= newInterval[1]) {
            // Update start and end to merge overlap region
            newInterval[0] = Math.min(newInterval[0], intervals[i][0]);
            newInterval[1] = Math.max(newInterval[1], intervals[i][1]);
            i++;
        }
        result.add(newInterval);

        // 3️⃣ Add all intervals that start after the merged new interval
        while (i < n) {
            result.add(intervals[i]);
            i++;
        }

        // 4️⃣ Convert list to array and return
        return result.toArray(new int[result.size()][]);
    }
}
```

[57. Insert Interval](https://leetcode.com/problems/insert-interval/)

#### 3. Non Overlapping Interval


```java
public int nonOverLapping(int[][] intervals){
	// Sort by end time
	Arrays.sort(intervals, (a, b) -> a[1] - b[1]);
	int count = 0;
	int[] last = intervals[0];
	
	for(int i = 1; i < intervals.length; i++){
		int[] curr = intervals[i];
		if(curr[0] < last[1]){
			count++;
		}else{
			last = curr;
		}
	}
	return count;
}
```

[435. Non-overlapping Intervals](https://leetcode.com/problems/non-overlapping-intervals/)



#### 4. Interval List Intersections (Two-Pointer Approach)


```java
public int[][] intervalIntersection(int[][] firstList, int[][] secondList) {
    if (firstList.length == 0 || secondList.length == 0) 
        return new int[0][0];

    List<int[]> ans = new ArrayList<>();
    int i = 0, j = 0;

    while (i < firstList.length && j < secondList.length) {
        int[] first = firstList[i];
        int[] second = secondList[j];

        int start = Math.max(first[0], second[0]);
        int end = Math.min(first[1], second[1]);

        if (start <= end) {
            ans.add(new int[]{start, end});
        }

        if (first[1] < second[1]) {
            i++;
        } else {
            j++;
        }
    }

    return ans.toArray(new int[ans.size()][]);
}
```

[986. Interval List Intersections](https://leetcode.com/problems/interval-list-intersections/)


📝 Interval Problems Summary

| Problem                     | Sorting / Order             | Approach / Pattern                                   | Time Complexity | Space Complexity |
| --------------------------- | --------------------------- | ---------------------------------------------------- | --------------- | ---------------- |
| Merge Intervals             | Sort by start               | Merge overlapping intervals                          | O(n log n)      | O(n)             |
| Insert Interval             | Sort by start (if unsorted) | Add non-overlapping → merge overlaps → add remaining | O(n)            | O(n)             |
| Non-overlapping Intervals   | Sort by end                 | Greedy: remove overlaps while scanning by end        | O(n log n)      | O(1)             |
| Interval List Intersections | Lists sorted by start       | Two-pointer scan → compute overlaps                  | O(n + m)        | O(1)             |
