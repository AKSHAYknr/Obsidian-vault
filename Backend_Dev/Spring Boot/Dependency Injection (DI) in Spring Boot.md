
---
**Dependency Injection (DI)** is a **design pattern** used by Spring to **manage object creation and their dependencies** automatically.  
Instead of classes creating their own dependencies, **Spring injects them** — improving **loose coupling** and **testability**.

🧱 Types of Dependency Injection in Spring Boot

|Type|Description|Example|Recommended?|
|---|---|---|---|
|**Constructor Injection**|Dependencies passed via constructor.|`public UserService(EmailService e)`|✅ Best practice|
|**Field Injection**|Uses `@Autowired` directly on fields.|`@Autowired private EmailService e;`|⚠️ Not recommended (hard to test)|
|**Setter Injection**|Uses setter method with `@Autowired`.|`setEmailService(EmailService e)`|👌 Sometimes used for optional deps|

🪄 Key Annotations Summary

|Annotation|Purpose|
|---|---|
|`@Autowired`|Marks a dependency to be injected automatically.|
|`@Qualifier`|Specifies which bean to inject when multiple exist.|
|`@Primary`|Marks one bean as the default candidate for injection.|
|`@Component`, `@Service`, `@Repository`, `@Controller`|Marks a class as a Spring-managed bean.|
