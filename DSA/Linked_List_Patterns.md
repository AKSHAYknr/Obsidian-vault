
---
# 🟢 Pattern 1: Two Pointers (Slow & Fast)

### 📌 When to use

- Detect if a cycle exists in the list
    
- Find the middle of the list
    
- Check if a list is a palindrome
    
- Problems involving relative positions
    

📝 Key Template

```java
ListNode slow = head, fast = head;
while (fast != null && fast.next != null) {
    slow = slow.next;       // move 1 step
    fast = fast.next.next;  // move 2 steps
    
    if (slow == fast) { 
        // cycle detected
    }
}
```

🧩 Example Problems

[141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
[142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)
[876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)
[234. Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)

---
# 🟢 Pattern 2: Dummy Node 

### 📌 When to use

- Simplify handling of edge cases (like head deletion)
    
- Remove nth node from the end
    
- Merge two sorted lists
    
- Reverse between indices

📝 Key Template

```java
ListNode dummy = new ListNode(0);
dummy.next = head;
ListNode prev = dummy;

// operate using prev, dummy helps avoid null checks
return dummy.next;
```

🧩 Example Problems

[19. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)
[21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
[92. Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/)

---
# 🟢 Pattern 3: Reversal Pattern

### 📌 When to use

- Reverse the whole list
    
- Reverse in groups of k
    
- Reverse between two indices
    

📝 Key Template

```java
ListNode prev = null, curr = head;
while (curr != null) {
    ListNode next = curr.next;
    curr.next = prev;
    prev = curr;
    curr = next;
}
return prev; // new head
```

🧩 Example Problems

[206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)
[92. Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/)
[25. Reverse Nodes in k-Group](https://leetcode.com/problems/reverse-nodes-in-k-group/)

---
# 🟢 Pattern 4: Merge Pattern

### 📌 When to use

- Merge two or k sorted lists
    
- Sort list using merge sort

📝 Key Template

```java
ListNode dummy = new ListNode(0), tail = dummy;
while (l1 != null && l2 != null) {
    if (l1.val < l2.val) {
        tail.next = l1;
        l1 = l1.next;
    } else {
        tail.next = l2;
        l2 = l2.next;
    }
    tail = tail.next;
}
tail.next = (l1 != null) ? l1 : l2;
return dummy.next;
```

🧩 Example Problems

[21. Merge Two Sorted Lists](https://leetcode.com/problems/merge-two-sorted-lists/)
[23. Merge k Sorted Lists](https://leetcode.com/problems/merge-k-sorted-lists/)
[148. Sort List](https://leetcode.com/problems/sort-list/)

---

# 🟢 Pattern 5: Cycle Handling

### 📌 When to use

- Detect cycle
    
- Find cycle start node
    
- Find cycle length

📝 Key Template

```java
ListNode slow = head, fast = head;
while (fast != null && fast.next != null) {
    slow = slow.next;
    fast = fast.next.next;
    if (slow == fast) { // cycle found
        slow = head;
        while (slow != fast) {
            slow = slow.next;
            fast = fast.next;
        }
        return slow; // start of cycle
    }
}
return null;
```

🧩 Example Problems

[141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
[142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)

---
