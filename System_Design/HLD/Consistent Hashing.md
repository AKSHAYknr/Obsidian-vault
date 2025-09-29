
---
Consistent hashing is a **technique used in distributed systems** to distribute data across a cluster of nodes in a way that **minimizes reorganization when nodes are added or removed**. It’s widely used in systems like **distributed caches (Redis, Memcached), databases, and load balancers**.

### **Consistent Hashing Concept**

1. **Hash both nodes and keys:**
    
    - Map each **node** (server) to a point on a **hash ring** (0 to 2³²-1 for 32-bit hash, for example).
        
    - Map each **key** to a point on the same hash ring.
        
2. **Assign key to node:**
    
    - Go clockwise on the ring from the key's hash until you find the **first node**.
        
    - That node is responsible for the key.
        
3. **Minimal remapping:**
    
    - Adding or removing a node only affects keys **between the previous node and the new node on the ring**, not all keys.

### **Enhancements**

1. **Virtual Nodes (V-Nodes)**
    
    - Each physical server is represented by **multiple points** on the hash ring.
        
    - This ensures **more uniform distribution** of keys and avoids hotspots.
        
2. **Hash functions:**
    
    - Must be **consistent** and **uniform** (e.g., MD5, SHA-1, or CRC32).

```mathematica
Hash Ring (0 → 2^32-1):

        Node A
         |
         |
Node D---+---Node B
         |
         |
        Node C

Keys: k1, k2, k3, k4

- k1 → Node B
- k2 → Node C
- k3 → Node D
- k4 → Node A
```

- If Node B is removed, only k1 moves to Node C; other keys are untouched.
### **Applications**

- **Distributed caches:** Memcached, Redis Cluster.
    
- **Load balancing:** Route requests based on consistent hashing.
    
- **Distributed databases:** Cassandra, DynamoDB.
