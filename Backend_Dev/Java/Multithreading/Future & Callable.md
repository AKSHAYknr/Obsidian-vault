
---
# 🧩 1. The Problem (Why Callable & Future exist)

Before Java 5, we only had **`Runnable`** for multithreading.

But `Runnable` has **two major limitations**:

1. It **cannot return a value**.
    
2. It **cannot throw checked exceptions**.
    

That made it hard to get results back from threads.

So Java 5 introduced **`Callable<V>`** and **`Future<V>`** to solve this.

# ⚙️ 2. Callable — a Task That Returns a Result

**`Callable`** is an interface (like `Runnable`), but it:

- Returns a value.
    
- Can throw checked exceptions.

# 🧠 3. Future — a Handle to Get the Result Later

A **`Future<V>`** represents the result of a computation that will finish **in the future**.

When you submit a `Callable` to an **ExecutorService**, you get back a **Future**.

You can:

- Check if the task is done (`isDone()`)
    
- Wait and get the result (`get()`)
    
- Cancel it (`cancel()`)

```java
import java.util.concurrent.*;

public class FutureExample {
    public static void main(String[] args) throws Exception {
        ExecutorService executor = Executors.newSingleThreadExecutor();

        Callable<Integer> task = () -> {
            System.out.println("Calculating...");
            Thread.sleep(2000);
            return 42;
        };

        Future<Integer> future = executor.submit(task);

        System.out.println("Task submitted, doing other work...");

        // You can check task status
        while (!future.isDone()) {
            System.out.println("Task not completed yet...");
            Thread.sleep(500);
        }

        // Get the result (blocks until task finishes)
        Integer result = future.get();
        System.out.println("Task completed! Result: " + result);

        executor.shutdown();
    }
}
```

# 🧰 4. Key Methods in Future

| Method                                 | Description                                         |
| -------------------------------------- | --------------------------------------------------- |
| `V get()`                              | Waits for the task to complete and returns result   |
| `V get(long timeout, TimeUnit unit)`   | Waits up to timeout, else throws `TimeoutException` |
| `boolean isDone()`                     | Checks if computation is finished                   |
| `boolean isCancelled()`                | Checks if cancelled                                 |
| `boolean cancel(boolean mayInterrupt)` | Tries to cancel the task                            |

# 🧩 6. Relationship Between Callable and Future

|Concept|Purpose|
|---|---|
|**Callable**|Defines a task that returns a result (`call()` method)|
|**Future**|Represents the result of that task, accessible later|
|**ExecutorService**|Runs the task and gives you the `Future`|

➡️ You **submit** a `Callable` to an ExecutorService → it **returns a `Future`**.

# 📘 7. When to Use Callable & Future

✅ **Use when:**

- You need to **execute a task asynchronously** (in another thread)
    
- You want to **get a result back** from that task
    
- You want to **handle exceptions** from that task
    
- You might need to **cancel** or **check progress**
    

# ⚠️ 8. Limitations of Future

While `Future` is great, it has some drawbacks:

- `get()` **blocks** until the result is ready.
    
- You **cannot chain** tasks (no callbacks).
    
- You **cannot combine** multiple async tasks easily.
    

That’s why Java 8 introduced **`CompletableFuture`**, which provides:

- Non-blocking async execution
    
- Task chaining (`thenApply`, `thenCombine`, etc.)
    
- Better error handling