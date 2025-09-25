
---
## **1. HashMap Internal Working (Java)**

### **A. Structure**

- **HashMap<K,V>** stores key-value pairs.
    
- Internally, it uses:

```java
HashMap<Integer, String> map = HashMap<>();
```

### **B. How It Works**

#### **1. Put Operation**

1. Compute **hash of the key**: `hash = key.hashCode()`.
    
2. Compute **bucket index**: `index = hash % array.length`.
    
3. Check if bucket is empty:
    
    - If empty → insert Node.
        
    - If not empty → iterate linked list / tree:
        
        - If key exists → replace value.
            
        - Else → append new Node at the end (or in tree if threshold exceeded).
            

#### **2. Get Operation**

1. Compute hash and bucket index.
    
2. Traverse the bucket:
    
    - Compare keys using `equals()`.
        
    - Return value if found, else `null`.

### **C. Handling Collisions**

- Uses **chaining** with **linked list** for multiple keys mapping to the same bucket.
    
- Since **Java 8**, if linked list exceeds 8 nodes → convert to **balanced tree (Red-Black Tree)** for faster lookup (`O(log n)` instead of `O(n)`).

### **D. Resizing**

- HashMap resizes when **load factor exceeds threshold** (default load factor = 0.75).
    
- Resize doubles the array and **rehashes all keys**.

### **E. Key Points**

| Aspect           | Notes                                                       |
| ---------------- | ----------------------------------------------------------- |
| Not synchronized | Not thread-safe                                             |
| Null keys        | Allows 1 null key                                           |
| Null values      | Allows multiple null values                                 |
| Time complexity  | O(1) average, O(n) worst case (before Java 8 treeification) |
## **2. Concurrent HashMap (Java)**

### **A. Structure**

- Thread-safe version of HashMap.
    
- Internally uses **segment-based locking (Java 7)** or **bucket-level locking (Java 8)**.
    
- Java 8+ uses **CAS operations and synchronized blocks** only for contention.

```java
ConcurrentHashMap<String, Integer> map = new ConcurrentHashMap<>();
```

### **B. How It Works**

#### **1. Put Operation**

1. Compute hash → bucket index.
    
2. Use **CAS (Compare-And-Swap)** or **lock the bucket**.
    
3. If bucket is empty → insert.
    
4. If bucket exists → traverse linked list / tree:
    
    - Replace value if key exists, else append.
        

#### **2. Get Operation**

- **Lock-free read**: reads happen without locking.
    
- Uses **volatile/atomic variables** to ensure visibility across threads.
    

#### **3. Resizing**

- Resize happens **gradually and thread-safely**.
    
- Segments or bins are resized independently to avoid global lock.

### **C. Key Points**

|Aspect|Notes|
|---|---|
|Thread-safe|Yes, concurrent read/write supported|
|Null keys/values|**Does not allow null keys or values**|
|Time complexity|O(1) average, thread-safe|
|Read operation|Lock-free for better performance|
|Write operation|Uses bucket-level locks / CAS|
### **3. Comparison HashMap vs ConcurrentHashMap**

|Feature|HashMap|ConcurrentHashMap|
|---|---|---|
|Thread-safe|No|Yes|
|Null key/value allowed|Yes|No|
|Read operation|Not synchronized|Lock-free / safe|
|Write operation|Not synchronized|Bucket-level lock / CAS|
|Performance|Fast (single-thread)|Slightly slower under contention|
|Internal structure|Array + Linked List / Tree|Array + Linked List / Tree + Locks|
