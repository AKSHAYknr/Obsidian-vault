
---
## 🧵 **1. Daemon Thread in Java**

A **daemon thread** is a **background thread** that provides services to other threads.  
It runs continuously in the background and **does not prevent the JVM from exiting** once all **user (non-daemon)** threads are finished.

### 🔹 **Key Idea**

- JVM **terminates automatically** when all **user threads** finish — even if daemon threads are still running.
    
- Examples:
    
    - Garbage Collector
        
    - Background loggers
        
    - Auto-save threads
        

### 🧩 **How to create a Daemon Thread**

You can mark a thread as daemon **before starting it** using `setDaemon(true)`.

```java
class MyDaemonThread extends Thread {
    public void run() {
        while (true) {
            System.out.println("Daemon thread running...");
            try {
                Thread.sleep(500);
            } catch (InterruptedException e) {
                System.out.println(e);
            }
        }
    }
}

public class DaemonExample {
    public static void main(String[] args) {
        MyDaemonThread t = new MyDaemonThread();
        t.setDaemon(true);  // Must be called before start()
        t.start();

        // Main thread (user thread)
        try {
            Thread.sleep(2000);
        } catch (InterruptedException e) {
            System.out.println(e);
        }

        System.out.println("Main thread finished...");
    }
}
```

### 🧾 **Output**

```
Daemon thread running...
Daemon thread running... 
Daemon thread running... 
Daemon thread running... 
Main thread finished...
```

After the main thread ends, the **daemon thread automatically stops** — JVM shuts down.

### ⚠️ **Important Rules**

- You **must call `setDaemon(true)` before `start()`**.
    
- Daemon threads are **killed abruptly** when JVM exits → no guarantee of cleanup.
    
- `isDaemon()` → returns whether the thread is daemon or not.

