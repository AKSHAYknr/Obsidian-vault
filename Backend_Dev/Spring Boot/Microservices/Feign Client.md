
---
# Microservice Communication using Feign Client

**Feign** is a **declarative HTTP client** developed by Netflix and integrated into Spring Cloud.  
It simplifies communication between microservices by automatically generating the HTTP calls from Java interfaces.

## Key Features of Feign

- Declarative and type-safe HTTP client.  
- Reduces boilerplate compared to `RestTemplate` or `WebClient`.  
- Can be integrated with **Eureka** for service discovery.  
- Supports **fallbacks** for resilience (with Hystrix or Resilience4j).  

## 1. Add Dependencies

```xml
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-openfeign</artifactId>
</dependency>
```



