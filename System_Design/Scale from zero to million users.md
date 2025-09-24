
---

## **Stage 1: Single Server Architecture**

**Goal:** Launch quickly, minimal infrastructure.

**Components:**

1. **Client:** Browser or mobile app.
    
2. **Single Server:**
    
    - **Application / API:** Handles business logic and HTTP requests.
        
    - **Database:** Stores all persistent data.
        
3. **Optional Cache:** For very hot data (Redis or Memcached), but not always necessary at this stage.
    

**Characteristics:**

- All services on **one machine** (vertical scaling if needed).
    
- Low cost, easy to deploy.
    
- Simple to maintain.
    
- Bottleneck is the single server → cannot handle millions yet.

```mermaid
graph LR
    Client -->|Request| Server[Single Server]
    
    subgraph Server
        App[Application / API]
        DB[(Database)]
        App -->|Query| DB
        DB -->|Result| App
    end
    
    App -->|Response| Client
```

## **Stage 2: Separate App and Database Servers**

**Goal:**

- Reduce load on a single server.
    
- Allow the application and database to scale independently.
    

**Components:**

1. **Client** – browser or mobile app.
    
2. **Application Server** – handles business logic and HTTP requests.
    
3. **Database Server** – stores persistent data, can scale vertically or horizontally.

```mermaid
graph LR
    Client -->|Request| AppServer[Application Server]
    
    subgraph AppServer
        App[Application / API]
    end
    
    subgraph DBServer
        DB[(Database)]
    end
    
    App -->|Query| DB
    DB -->|Result| App
    App -->|Response| Client
```

## **Stage 3: Load Balancer + Multiple Application Servers**

**Goal:**

- Distribute traffic across multiple app servers (horizontal scaling).
    
- Prevent single point of failure at the application layer.
    
- Keep the database as a single source of truth.

```mermaid
graph LR
    Client[Client] --> LB[Load Balancer]
    LB --> App1[Application Server 1]
    LB --> App2[Application Server 2]
    LB --> App3[Application Server 3]
    App1 --> DB[(Database)]
    App2 --> DB
    App3 --> DB
```

## **Stage 4: Database Replication**

**Flow:**

- Client → Load Balancer → Application Servers → Databases
    
- **Primary DB** (handles writes).
    
- **Read Replicas** (handle read queries, reducing load on primary).

```mermaid
graph TD
    Client[Client] --> LB[Load Balancer]
    LB --> App1[Application Server 1]
    LB --> App2[Application Server 2]
    LB --> App3[Application Server 3]

    %% Database cluster grouping
    subgraph DBCluster[Database Cluster]
        PrimaryDB[(Primary / Master DB)]
        ReadDB1[(Read Replica / Slave 1)]
        ReadDB2[(Read Replica / Slave 2)]
    end

    %% Replication flow
    PrimaryDB --> ReadDB1
    PrimaryDB --> ReadDB2

    %% Write path (all apps write to master)
    App1 -->|Write Queries| PrimaryDB
    App2 -->|Write Queries| PrimaryDB
    App3 -->|Write Queries| PrimaryDB

    %% Read path (apps can load balance between replicas)
    App1 -->|Read Queries| ReadDB1
    App2 -->|Read Queries| ReadDB2
    App3 -->|Read Queries| ReadDB1
    App3 -->|Read Queries| ReadDB2
```


## **Stage 5: Adding Caching Layer**

**Flow:**

1. **Client → Load Balancer → App Servers**.
    
2. App Servers first check **Cache (Redis/Memcached)**.
    
    - If data is found → return result (fast).
        
    - If not → query the Database (Primary/Replicas), then update Cache.
        
3. Database cluster still handles writes (Primary) and reads (Replicas).

```mermaid
graph TD
    Client[Client] --> LB[Load Balancer]
    LB --> App1[Application Server 1]
    LB --> App2[Application Server 2]
    LB --> App3[Application Server 3]

    App1 --> Cache[(Cache: Redis/Memcached)]
    App2 --> Cache
    App3 --> Cache

    Cache --> PrimaryDB[(Primary / Master DB)]

    subgraph DBCluster[Database Cluster]
        PrimaryDB
        ReadDB1[(Read Replica 1)]
        ReadDB2[(Read Replica 2)]
        PrimaryDB --> ReadDB1
        PrimaryDB --> ReadDB2
    end
```


## **Stage 6: Add CDN Layer**

**What it does:**

- Serves **static content** (images, CSS, JS) from servers close to users.
    

**Why it matters for scaling:**

1. **Reduces load on backend servers** → apps handle more dynamic requests.
    
2. **Improves response time** → faster for users worldwide.
    
3. **Handles traffic spikes** → prevents origin servers from being overwhelmed.

```mermaid
graph TD
    Client[Client] --> CDN[CDN - Static Content]
    CDN --> LB[Load Balancer]

    LB --> App1[Application Server 1]
    LB --> App2[Application Server 2]
    LB --> App3[Application Server 3]

    App1 --> Cache[(Cache: Redis/Memcached)]
    App2 --> Cache
    App3 --> Cache

    Cache --> PrimaryDB[(Primary / Master DB)]

    subgraph DBCluster[Database Cluster]
        PrimaryDB
        ReadDB1[(Read Replica 1)]
        ReadDB2[(Read Replica 2)]
        PrimaryDB --> ReadDB1
        PrimaryDB --> ReadDB2
    end
```

