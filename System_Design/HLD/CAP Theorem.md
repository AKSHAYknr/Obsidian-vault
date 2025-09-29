
---
## **1. What is CAP Theorem?**

**CAP Theorem** (Brewer’s Theorem) states that in a **distributed data system**, you can only guarantee **two out of three** properties at the same time:

|Letter|Meaning|
|---|---|
|**C – Consistency**|Every read receives the **most recent write** or an error.|
|**A – Availability**|Every request receives a **response (success or failure)**, without guarantee it is the most recent.|
|**P – Partition Tolerance**|The system continues to operate **despite network partitions** (communication failures between nodes).|

**Key:** You **cannot achieve all three simultaneously** in a distributed system.

## **2. Trade-offs**

- **CP (Consistency + Partition tolerance):**
    
    - Example: HBase, MongoDB (with strong consistency)
        
    - May reject requests during partition to maintain consistency.
        
- **AP (Availability + Partition tolerance):**
    
    - Example: CouchDB, Cassandra (eventual consistency)
        
    - Always available, may return stale data during partition.
        
- **CA (Consistency + Availability):**
    
    - Works only if **no network partition occurs**
        
    - Rare in distributed systems.

### **Key Points**

- **Partition tolerance is unavoidable** in real distributed systems because networks **can fail anytime**.
    
- CAP theorem says that **in the presence of a partition**, you must **choose between consistency (C) and availability (A)**:
    
    - **CP system:** Consistency over availability → some requests may fail during partition.
        
    - **AP system:** Availability over consistency → all requests succeed, but data might be temporarily inconsistent.


