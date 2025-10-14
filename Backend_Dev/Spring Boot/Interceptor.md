
---
#### 🔹 **What is an Interceptor?**

An **interceptor** in Spring Boot is used to **intercept HTTP requests and responses** before they reach the controller or after the controller executes — similar to filters but more Spring-aware.

---

#### 🔹 **Use Cases**

- Logging incoming requests
    
- Checking authentication/authorization
    
- Modifying request/response objects
    
- Measuring execution time

#### 🔹 **Interceptor Lifecycle**

| Method              | Triggered When                | Purpose                 |
| ------------------- | ----------------------------- | ----------------------- |
| `preHandle()`       | Before Controller             | Authentication, logging |
| `postHandle()`      | After Controller, before View | Modify response, model  |
| `afterCompletion()` | After View rendered           | Cleanup, logging        |

### ⚔️ **Filters vs Interceptors**

| Feature                 | **Filter**                                                  | **Interceptor**                                                             |
| ----------------------- | ----------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Part of**             | Servlet specification (javax / jakarta)                     | Spring MVC framework                                                        |
| **Interface**           | `javax.servlet.Filter`                                      | `org.springframework.web.servlet.HandlerInterceptor`                        |
| **Executes**            | Before and after **servlet / dispatcher**                   | Before and after **controller method**                                      |
| **Access Level**        | Low-level (request, response, headers, body)                | High-level (handler/controller info, model)                                 |
| **Use Case**            | Authentication, logging raw requests, CORS, compression     | Business logic validation, modifying model/response, execution time logging |
| **Order of Execution**  | Runs **before interceptors**                                | Runs **after filters**, before controller                                   |
| **Can modify**          | Raw request/response body                                   | Request attributes and model data                                           |
| **Configuration**       | Declared using `@Component` or via `FilterRegistrationBean` | Registered via `WebMvcConfigurer.addInterceptors()`                         |
| **Framework Awareness** | Not aware of Spring beans directly                          | Can use Spring Beans (fully managed by Spring)                              |