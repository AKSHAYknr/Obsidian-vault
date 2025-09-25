[[TinyURL.excalidraw]]

---
## **1. Requirements Gathering**

**Functional Requirements (FR):**

- Shorten a given long URL
    
- Redirect from short URL to long URL
    
- Optional: track click analytics
    

**Non-Functional Requirements (NFR):**

- High availability & low latency for redirects
    
- Handle high QPS (reads > writes)
    
- Scalable to millions of URLs
    

**Constraints / Assumptions:**

- Average URL length ~200 chars
    
- Short URL length: 6–8 chars,  combinations of 62 chars (a-z | A-Z | 0-9).
    
- Traffic: 100M+ redirects per day

---
## **2. URL Shortening Strategy (Explicitly)**

**Chosen Strategy:**

- **Base62 encoding of sequential ID + random character**
    
    - Ensures uniqueness across distributed servers
        
    - Compact & URL-friendly
        
    - Harder to predict than pure sequential IDs
        

**Flow:**

1. Generate a **unique numeric ID** (auto-increment / distributed ID generator)
    
2. Encode ID in **Base62** → produces short string (e.g., `dnh`)
    
3. Append a **random character** for unpredictability (optional)
    
4. Check **DB for collision** → retry if needed
    

**Alternative / Optional Strategies:**

- Random string generation (check DB for collisions)
    
- Hash of long URL (deterministic, optional)
    

**Reasoning:**

- Handles **high scale**
    
- Avoids **hotspots**
    
- Minimizes **collision risk**
    
- Maintains **short and user-friendly URL**

---
## **3. High-Level Architecture**

**Components:**

1. Client: Browser / Mobile app
    
2. API Gateway / Load Balancer
    
3. Application Servers (Shorten & Redirect API)
    
4. Database: stores short → long URL mapping
    
5. Cache (Redis / Memcached): fast redirect lookups
    
6. Optional Analytics Service: collects click data asynchronously
    

**Flow:**

- **Shorten URL:** Client → API → App → DB → return short URL
    
- **Redirect:** Client → App → Cache → DB → redirect

---

## **4. Data Modeling**

**Entity:** URL Mapping

| Field      | Type      | Notes                  |
| ---------- | --------- | ---------------------- |
| short_url  | string    | Primary key, 6–8 chars |
| long_url   | string    | Original URL           |
| created_at | timestamp | Optional               |

**Indexes:**

- Primary key on `short_url`
    
- Optional index on `long_url` for duplicate detection
    

**Database Choice:**

- SQL (e.g., MySQL) for consistency or NoSQL (e.g., DynamoDB) for scalability
    

**Sharding Strategy:**

- Hash `short_url` to distribute across multiple DB shards


---
## **5. APIs / Interfaces**

**1. Shorten URL:**

```json
POST /shorten 
Body: { "long_url": "https://example.com" } 
Response: { "short_url": "https://tiny.ly/abc123" }
```

**2. Redirect URL:**

```json
GET /{short_url} Redirects to the original long URL
```

**Optional:** Analytics API

```json
GET /analytics/{short_url} Returns click count, geo, device
```

**Other Considerations:**

- Auth not required for public shortening
    
- Rate limiting to prevent abuse

---
## **6. Scalability & Performance**

- **Read-heavy optimization:**
    
    - Store frequently accessed URLs in **Redis** for O(1) redirect
        
- **Horizontal scaling:**
    
    - Multiple app servers behind load balancer
        
- **Database scaling:**
    
    - Sharding by hash of short URL
        
- **Asynchronous analytics:**
    
    - Kafka queue → analytics service for click logging


---
## **7. Reliability & Availability**

- Replicate DB for high availability
    
- Multi-region deployment for global traffic
    
- Health checks on app servers
    
- Monitoring & alerting (Prometheus / Grafana)
    

---

## **8. Consistency & Concurrency**

- Strong consistency for URL mapping (short → long)
    
- Use **atomic DB inserts** to avoid collisions
    
- Optionally use **distributed lock** when generating short URLs