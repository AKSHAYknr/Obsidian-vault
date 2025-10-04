
---
**Amazon S3** is a **scalable object storage service** that allows you to store and retrieve **any amount of data** from anywhere on the web. It’s highly durable, available, and secure, making it one of the most widely used AWS services.

---

### 🔹 Key Concepts

1. **Buckets**
    
    - Containers for storing objects (files, images, videos, backups).
        
    - Each bucket has a **unique name globally**.
        
2. **Objects**
    
    - The actual data stored in S3.
        
    - Consists of **file data**, **metadata**, and a **unique key (name)**.
        
3. **Keys**
    
    - Unique identifier for each object in a bucket.
        
    - Essentially, the “path” or filename of the object.
        
4. **Regions**
    
    - Buckets are created in specific AWS regions for **low latency and compliance**.
        

---

### 🔹 Key Features

- **Durability** → 99.999999999% (11 nines)
    
- **Scalability** → Virtually unlimited storage
    
- **Access Control** → IAM policies, bucket policies, ACLs
    
- **Versioning** → Keep multiple versions of an object
    
- **Lifecycle Rules** → Automatically move data to cheaper storage tiers (Glacier)
    
- **Encryption** → Server-side (SSE) or client-side encryption for security
    

---

### 🔹 Common Use Cases

- **File storage** → Images, videos, documents
    
- **Backup & restore** → Database snapshots, system backups
    
- **Static website hosting** → Hosting HTML/CSS/JS websites
    
- **Data lake / Big data storage** → Store raw data for analytics
    
- **Application integration** → Microservices store/retrieve files



