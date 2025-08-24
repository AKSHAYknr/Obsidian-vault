
---
### **1. Traversal of Linked List**

**When to use :** Any time you need to iterate through nodes (printing, counting, searching, etc.)

**Key Template :**

```java
void traverse(ListNode head){
	while(head != null){
		//perfom operation on head.val;
		head = head.next;
	}
}
```

**LeetCode Problems :**

[LC 1290. Convert Binary Number in a Linked List to Integer](https://leetcode.com/problems/convert-binary-number-in-a-linked-list-to-integer/)


---

### **2. Reverse a Linked List (Entire List)**

**When to use :** Reversing for palindrome check, merging, or manipulation.

**Key Template :**

```java
ListNode reverse(ListNode head){
	ListNode prev = null;
	while(head != null){
		ListNode next = head.next; // save next node
		head.next = prev; // reverse
		prev = head; // move prev forward
		head = next; // move head forward
	}
	return prev;
}
```

**LeetCode Problems :**

[LC 206. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)

[LC 234. Palindrome Linked List](https://leetcode.com/problems/palindrome-linked-list/)


---

### **3. Cycle Detection In Linked List**

**When to use :** To detect infinite loops or repeated path (Floyd's Cycle Detection Algorithm)

**Key Template :**

```Java
boolean detectCycle(ListNode head){
	ListNode slow = head, fast = head;
	while(fast != null && fast.next != null){
		slow = slow.next; // move one step
		fast = fast.next.next; // move two steps
		if(slow == fast) return true; // when equal there is a cycle
	}
	return false;
}
```

**LeetCode Problems :**

[LC 141. Linked List Cycle](https://leetcode.com/problems/linked-list-cycle/)
[LC 142. Linked List Cycle II](https://leetcode.com/problems/linked-list-cycle-ii/)


---

### **4. Reverse Linked List Between two Indices**

When to use