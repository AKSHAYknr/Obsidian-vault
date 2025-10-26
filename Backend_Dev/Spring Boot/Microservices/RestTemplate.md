
---
# Microservice Communication using RestTemplate

In a **microservices architecture**, services often need to communicate with each other.  
One way to achieve **synchronous communication** in Spring Boot is using `RestTemplate`.

---

## What is `RestTemplate`?

`RestTemplate` is a **Spring class** used to make HTTP requests (GET, POST, PUT, DELETE) to other services.  
It is **blocking** and synchronous.

---

## Adding `RestTemplate` Bean

```java
@Configuration
public class AppConfig {

    @Bean
    public RestTemplate restTemplate() {
        return new RestTemplate();
    }
}
```


### GET Request

```java
@Autowired private RestTemplate restTemplate;  
public User getUserById(Long id) {     
	String url = "http://user-service/users/" + id;     
	User user = restTemplate.getForObject(url, User.class);     
	return user;
}
```

- `getForObject(url, class)` → returns response body.
    
- `getForEntity(url, class)` → returns **ResponseEntity** (body + status + headers).