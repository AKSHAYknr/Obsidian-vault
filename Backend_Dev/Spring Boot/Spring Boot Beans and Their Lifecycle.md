
---
A **Bean** in Spring Boot is an **object managed by the Spring IoC (Inversion of Control) Container**.  
It’s created, configured, and managed automatically by Spring at runtime.

💡 In simple terms:

 A **bean** is a Java object that Spring instantiates, injects dependencies into, and manages the lifecycle of.

🧱 1️⃣ **Using Stereotype Annotations**

Spring can automatically detect and register classes as beans when you use **stereotype annotations**.

🔹 Common Annotations

|Annotation|Purpose|
|---|---|
|`@Component`|Generic Spring-managed bean.|
|`@Service`|Used in the **service layer** for business logic.|
|`@Repository`|Used in the **data access layer** (also handles exceptions).|
|`@Controller` / `@RestController`|Used in the **web layer** for handling HTTP requests.|

⚙️ 2️⃣ **Using `@Bean` Annotation in a Configuration Class**

You can also manually define beans inside a **`@Configuration`** class using the **`@Bean`** annotation.  
This is useful when:

- You need to **control bean creation** manually.
    
- You’re **instantiating third-party classes** (not annotated with `@Component`).


**How Spring Manages Beans**

Spring uses the **ApplicationContext (IoC container)** to:

1. Create the bean (instantiation).
    
2. Inject dependencies (wiring).
    
3. Manage its full lifecycle (init → ready → destroy).

Lifecycle Stages :

|Phase|Description|
|---|---|
|**1. Instantiation**|Spring creates the bean instance (using reflection).|
|**2. Populate Properties**|Injects dependencies (`@Autowired`, `@Value`, etc.).|
|**3. BeanNameAware / BeanFactoryAware**|(Optional) Beans can access their name or factory.|
|**4. Pre-Initialization**|BeanPostProcessors (e.g. `@PostConstruct`) run before initialization.|
|**5. Initialization**|Custom init logic via `@PostConstruct` or `InitializingBean`.|
|**6. Post-Initialization**|BeanPostProcessors can modify or wrap the bean.|
|**7. Ready for Use**|Bean is fully initialized and used in the app.|
|**8. Destruction**|Before container shutdown, cleanup methods run (`@PreDestroy`, `DisposableBean`).|

