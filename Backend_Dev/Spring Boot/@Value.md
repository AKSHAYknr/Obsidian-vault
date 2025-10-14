
---
- `@Value` is a **Spring annotation** used to **inject values into fields, methods, or constructor parameters**.
    
- Values can come from:
    
    - **`application.properties` / `application.yml`**
        
    - **System environment variables**
        
    - **Expression values** (SpEL – Spring Expression Language)

application.properties :

```
app.s3_bucket_name
```


```java
@value("${app.s3_bucket_name}")
private String bucketName;
```