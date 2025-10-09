
---
In **Java**, the `join()` method is used in multithreading to **pause the execution of the current thread** until the thread on which `join()` is called has finished executing.

```java
thread.join();
```

- Here, the **current thread** will wait until the `thread` (on which `join()` is called) **finishes execution**.

### 🧠 **How it works**

When you start multiple threads, they all run **concurrently**.  
But sometimes, you might want one thread to **wait for another** before continuing.

That’s where `join()` comes in.

```java
class MyThread extends Thread {
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(Thread.currentThread().getName() + " - " + i);
            try {
                Thread.sleep(500); // Sleep for 0.5 sec
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}

public class JoinExample {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();
        MyThread t3 = new MyThread();

        t1.start();
        try {
            // Wait for t1 to finish before starting t2
            t1.join();
        } catch (InterruptedException e) {
            System.out.println(e);
        }

        t2.start();
        try {
            // Wait for t2 to finish before starting t3
            t2.join();
        } catch (InterruptedException e) {
            System.out.println(e);
        }

        t3.start();
    }
}
```

```mathematica
Thread-0 - 1
Thread-0 - 2
Thread-0 - 3
Thread-0 - 4
Thread-0 - 5
Thread-1 - 1
Thread-1 - 2
Thread-1 - 3
Thread-1 - 4
Thread-1 - 5
Thread-2 - 1
Thread-2 - 2
Thread-2 - 3
Thread-2 - 4
Thread-2 - 5
```

Without `join()`, all threads would run **concurrently**, and output would be **interleaved**.

### ⚙️ **Variants of `join()`**

| Method                         | Description                              |
| ------------------------------ | ---------------------------------------- |
| `join()`                       | Waits indefinitely until the thread dies |
| `join(long millis)`            | Waits for specified milliseconds         |
| `join(long millis, int nanos)` | Waits for specified time + nanoseconds   |

### 💡 **Key Points**

- `join()` ensures **order of execution** among threads.
    
- It can throw **InterruptedException** → must handle with try-catch.
    
- It’s often used in **synchronization** when you want one thread to complete before others continue.

