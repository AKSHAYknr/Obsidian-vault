
---
# 🔹 1. LinkedHashMap

- A subclass of **HashMap**.
    
- Maintains a **doubly linked list** of entries.
    
- Preserves **insertion order** (or **access order** if configured).
    
- Provides `O(1)` performance for `get()`, `put()`, and `remove()`.
    

### Example:

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        LinkedHashMap<Integer, String> map = new LinkedHashMap<>();
        map.put(3, "C");
        map.put(1, "A");
        map.put(2, "B");

        System.out.println(map); // {3=C, 1=A, 2=B} -> insertion order preserved
    }
}
```

# 🔹 2. TreeMap

- Implements **NavigableMap** (a SortedMap).
    
- Stores keys in **sorted order** (natural ordering or custom `Comparator`).
    
- Based on **Red-Black Tree**.
    
- Provides `O(log n)` time for `get()`, `put()`, and `remove()`.
    

### Example:

```java
import java.util.*;

public class Main {
    public static void main(String[] args) {
        TreeMap<Integer, String> map = new TreeMap<>();
        map.put(3, "C");
        map.put(1, "A");
        map.put(2, "B");

        System.out.println(map); // {1=A, 2=B, 3=C} -> sorted order
    }
}
```

# 🔹 3. Key Differences

|Feature|**LinkedHashMap**|**TreeMap**|
|---|---|---|
|**Ordering**|Insertion order (or access order if enabled)|Sorted order of keys (natural or custom comparator)|
|**Implementation**|Hash table + linked list|Red-Black Tree|
|**Performance**|`O(1)` for `get`, `put`, `remove`|`O(log n)` for `get`, `put`, `remove`|
|**Null keys**|1 null key allowed|❌ No null keys|
|**Null values**|Allowed|Allowed|
|**Use Case**|Maintain insertion order with fast lookups|Maintain sorted map of keys|

# 🔹 4. When to Use?

- **LinkedHashMap** → When you need **fast access + maintain insertion order** (e.g., implementing **LRU cache**).
    
- **TreeMap** → When you need **keys sorted** (e.g., leaderboard, dictionary-like features).