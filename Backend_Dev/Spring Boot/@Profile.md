
---

- `@Profile` is a **Spring annotation** used to **conditionally register beans** based on the **active Spring profile**.
    
- Useful for **environment-specific configurations**: `dev`, `test`, `prod`, etc.

```java
@Service
@Profile("dev")
public class DevDatabaseService implements DatabaseService {
    @Override
    public void connect() {
        System.out.println("Connecting to DEV database");
    }
}
```

**Behavior:**

- Bean is **registered only if `dev` profile is active**.
    
- Otherwise, Spring ignores it.

```
spring.profiles.active=dev
```

```yaml
spring:
  profiles:
    active: dev
```

## ⚙️ Key Points

- `@Profile` works with **beans, services, repositories, or configuration classes**.
    
- Useful for **switching implementations based on environment** without code changes.
    
- Can be combined with `@ConditionalOnProperty` for more advanced conditional bean creation.

**Use Case:**

- `dev` profile → local DB, mock services
    
- `test` profile → testing DB
    
- `prod` profile → production DB, real services.

