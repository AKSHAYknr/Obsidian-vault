
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

**When to use :** When the reversal is between two given positions (Left, Right) in the given linked list.

	steps
		- Create one dummy node that points to head node (keep track of head).
		- Create a prev pointer and set that to left-1.
		- Reverse from left to right.

**Key Template :**

```java
ListNode reverseBetweenIndices(ListNode head){
	ListNode dummy = new ListNode(0);
	dummy.next = head;
	ListNode prev = dummy;
	
	for(int i = 1; i < left; i++){
		prev = prev.next;
	}
	
	ListNode curr = prev.next;
	for(int i = 0; i < right - left; i++){
		ListNode temp = curr.next;
		curr.next = temp.next;
		temp.next = prev.next;
		prev.next = temp;
	}
	return dummy.next;
}
```

LeetCode Problems :

[LC 92. Reverse Linked List II](https://leetcode.com/problems/reverse-linked-list-ii/)
[LC 61. Rotate List](https://leetcode.com/problems/rotate-list/)

---

### **5. Find Middle Node**

**When to use** : Splitting the list into two halves, palindrome check, binary operations.

**Key Template :**

```java
ListNode middleNode(ListNode head){
	ListNode slow = head, fast = head;
	while(fast != null && fast.next != null){
		slow = slow.next;
		fast = fast.next.next;
	}
	return slow;
}
```

[LC 876. Middle of the Linked List](https://leetcode.com/problems/middle-of-the-linked-list/)

---

### **6. Delete Nth Node From End Of The List**

Used to delete the Nth node from end of a list.

**Key Template :**

```java
ListNode removeNthFromEnd(ListNode head, int n){
	ListNode dummy = new ListNode(0);
	ListNode slow = dummy, fast = dummy;
	
	for(int i = 0; i < n+1; i++){
		fast = fast.next;
	}
	
	while(fast != null){
		fast = fast.next;
		slow = slow.next;
	}
	
	slow.next = slow.next.next;
	return dummy.next;
}
```

[LC 19. Remove Nth Node From End of List](https://leetcode.com/problems/remove-nth-node-from-end-of-list/)

