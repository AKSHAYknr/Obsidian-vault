
---

## **1. Network Protocols Overview**

Network protocols are rules and standards that allow computers to communicate over networks. They are typically grouped by layers based on the **OSI model** or **TCP/IP model**.

### **OSI Model Layers & Protocol Examples**

|Layer|Protocols|Purpose|
|---|---|---|
|**Application**|HTTP, HTTPS, FTP, SMTP, DNS|User-level services like web browsing, email, file transfer|
|**Transport**|TCP, UDP|Reliable/unreliable data delivery|
|**Network**|IP, ICMP, ARP|Addressing and routing packets|
|**Data Link**|Ethernet, PPP, Wi-Fi (802.11)|Physical addressing, error detection|
|**Physical**|Ethernet cables, Fiber, Wi-Fi radio|Raw bit transmission|
## **2. Common Protocols**

### **a) HTTP / HTTPS**

- Application layer protocol for web communication.
    
- HTTPS = HTTP + TLS/SSL encryption.
    


```mermaid
sequenceDiagram
    participant Client
    participant Server

    Client->>Server: HTTP GET /index.html
    Server-->>Client: HTML Content
```
### **b) TCP / UDP**

- **TCP:** Reliable, connection-oriented.
    
- **UDP:** Fast, connectionless.
    

**TCP Connection Flow (3-way handshake):**

```mermaid
sequenceDiagram
    participant Client
    participant Server

    Client->>Server: SYN
    Server-->>Client: SYN-ACK
    Client->>Server: ACK
```

### **c) DNS (Domain Name System)**

- Resolves domain names to IP addresses.

```mermaid
sequenceDiagram
    participant Client
    participant DNS_Server

    Client->>DNS_Server: Query example.com
    DNS_Server-->>Client: Return 93.184.216.34
```
### **d) FTP (File Transfer Protocol)**

- Used for transferring files.

```mermaid
sequenceDiagram
    participant Client
    participant FTP_Server

    Client->>FTP_Server: Connect
    FTP_Server-->>Client: Welcome Message
    Client->>FTP_Server: Upload file.txt
    FTP_Server-->>Client: Success
```
