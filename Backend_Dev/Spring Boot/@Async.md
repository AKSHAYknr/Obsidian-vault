
---
- `@Async` is used to **run a method asynchronously** — i.e., in a **separate thread**, not blocking the main thread.

- It helps improve performance by executing time-consuming tasks (like sending emails, making API calls, etc.) in the background.

⚙️ How It Works

- When a method is marked with `@Async`, Spring creates a **proxy** and executes it in a **ThreadPoolTaskExecutor**.
 
- The method runs **asynchronously** only if it’s called **from another bean**, not from the same class (because of proxy-based nature).

```java
@EnableAsync
@SpringBootApplication
public class MyApp {
    public static void main(String[] args) {
        SpringApplication.run(MyApp.class, args);
    }
}
```

```java
@Service
public class EmailService {

    @Async
    public void sendEmail(String to, String message) {
        // Long running task
        System.out.println("Sending email to: " + to);
    }
}
```

```java
@RestController
public class MailController {

    @Autowired
    private EmailService emailService;

    @PostMapping("/send")
    public String sendMail(@RequestParam String to) {
        emailService.sendEmail(to, "Hello from Async!");
        return "Request received!";
    }
}
```

⚡ Return Types Supported

- `void`
    
- `Future<T>`
    
- `CompletableFuture<T>`

```java
@Async
public CompletableFuture<String> processData() {
    Thread.sleep(3000);
    return CompletableFuture.completedFuture("Done!");
}
```

⚙️ Custom Executor

You can define a custom thread pool:

```java
@Configuration
@EnableAsync
public class AsyncConfig implements AsyncConfigurer {

    @Override
    public Executor getAsyncExecutor() {
        ThreadPoolTaskExecutor executor = new ThreadPoolTaskExecutor();
        executor.setCorePoolSize(3);
        executor.setMaxPoolSize(5);
        executor.setQueueCapacity(100);
        executor.initialize();
        return executor;
    }
}
```

⚠️ Important Notes (Explained)

- **Public method** → `@Async` works only on public methods; private ones bypass Spring proxies.
    
- **Different bean call** → Async won’t trigger if you call the method from the **same class**, because proxies aren’t applied internally.
    
- **Spring-managed bean** → Works only if the class is created by Spring (`@Service`, `@Component`, etc.), not via `new`.
    
- **Exception handling** → Exceptions in async methods run on a separate thread, so they don’t bubble up; handle them using `AsyncUncaughtExceptionHandler`.

