
---
**Amazon Elastic Compute Cloud (EC2)** is a web service that provides **resizable virtual servers (instances)** in the cloud.  
It lets you run applications without managing physical hardware. You can scale up or down depending on traffic.

---

### 🔹 Key Concepts

1. **Instance**
    
    - A virtual server running your application.
        
    - Can run Linux, Windows, or custom AMIs (Amazon Machine Images).
        
2. **AMI (Amazon Machine Image)**
    
    - A preconfigured template that contains an OS and optional software.
        
3. **Instance Types**
    
    - Various configurations for CPU, memory, storage, and networking.
        
    - Examples:
        
        - `t2.micro` → small, low cost, general-purpose
            
        - `m5.large` → balanced compute and memory
            
        - `c6g` → compute-optimized
            
4. **Security Groups**
    
    - Acts as a firewall controlling inbound and outbound traffic.
        
5. **Key Pair**
    
    - SSH keys to securely access your EC2 instance.
        
6. **Elastic IP**
    
    - Static public IP address you can assign to an instance.
        

---

### 🔹 Features

- **Scalable** → Launch more instances as traffic grows.
    
- **Flexible** → Choose OS, CPU, memory, storage, networking.
    
- **Reliable** → Supports multiple Availability Zones.
    
- **Integrates with AWS services** → S3, RDS, Lambda, CloudWatch.
    
- **Pay-as-you-go** → Only pay for what you use.
    

---

### 🔹 Common Use Cases

- Web servers
    
- Microservices backend
    
- Batch processing / data analysis
    
- Dev/test environments
    
- Hosting custom applications