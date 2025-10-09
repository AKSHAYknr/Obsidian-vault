
---
The **ThreadPoolExecutor Framework** in Java is a powerful part of the **`java.util.concurrent`** package that manages a pool of threads for executing multiple tasks efficiently. Instead of creating a new thread for every task (which is costly), it **reuses existing threads**, improving performance and resource utilization — especially in high-load or server-side applications.

---

## 🧠 Why Use a Thread Pool?

Creating threads is **expensive** in terms of memory and CPU time.  
A **ThreadPoolExecutor**:

- Reuses existing threads (reduces overhead)
    
- Limits the number of concurrent threads
    
- Manages queued tasks
    
- Provides flexibility and control (timeouts, priorities, etc.)
    

---

## 🧩 Core Classes Involved

- **`Executor`** — Base interface for executing tasks.
    
- **`ExecutorService`** — Sub-interface that adds methods for managing task lifecycle (shutdown, submit, etc.)
    
- **`ThreadPoolExecutor`** — Core implementation of a thread pool.
    
- **`Executors`** — Utility class with factory methods to create common thread pools.

```java
import java.util.concurrent.ExecutorService;
import java.util.concurrent.Executors;

public class ThreadPoolExample {
    public static void main(String[] args) {
        // Create a fixed thread pool with 3 threads
        ExecutorService executor = Executors.newFixedThreadPool(3);

        for (int i = 1; i <= 5; i++) {
            int taskId = i;
            executor.execute(() -> {
                System.out.println("Task " + taskId + " is running on " +
                                   Thread.currentThread().getName());
                try {
                    Thread.sleep(2000);
                } catch (InterruptedException e) {
                    e.printStackTrace();
                }
                System.out.println("Task " + taskId + " completed");
            });
        }

        executor.shutdown(); // Stop accepting new tasks
    }
}
```

## 🛠️ ThreadPoolExecutor Constructor

```java
ThreadPoolExecutor(    
	 int corePoolSize,     
	 int maximumPoolSize,     
	 long keepAliveTime,     
	 TimeUnit unit,     
	 BlockingQueue<Runnable> workQueue,     
	 ThreadFactory threadFactory,     
	 RejectedExecutionHandler handler 
);
```

### Parameters Explained

| Parameter           | Description                                               |
| ------------------- | --------------------------------------------------------- |
| **corePoolSize**    | Minimum number of threads kept alive even if idle         |
| **maximumPoolSize** | Max number of threads that can exist in the pool          |
| **keepAliveTime**   | Time idle threads above `corePoolSize` are kept alive     |
| **unit**            | Time unit for `keepAliveTime`                             |
| **workQueue**       | Queue for storing waiting tasks                           |
| **threadFactory**   | Creates new threads (you can customize names, priority)   |
| **handler**         | Strategy when a task is rejected (pool full + queue full) |

## 🧩 Common Executor Types (via `Executors`)

|Method|Description|
|---|---|
|`newFixedThreadPool(n)`|Fixed number of threads|
|`newCachedThreadPool()`|Creates new threads as needed, reuses idle ones|
|`newSingleThreadExecutor()`|One thread — tasks execute sequentially|
|`newScheduledThreadPool(n)`|For delayed or periodic tasks|

## ✅ Best Practices

- Always **shutdown()** the executor to free resources.
    
- Use **`awaitTermination()`** if you need to wait for completion.
    
- Use **bounded queues** to prevent memory leaks.
    
- Prefer using **factory methods from `Executors`** for simplicity.
    
- For high control → use `ThreadPoolExecutor` directly.

