
---
## ⚙️ **2. Thread Priority in Java**

Each thread in Java has a **priority** that helps the **thread scheduler** decide which thread to run first.

### 🔹 **Priority Range**

|Constant|Value|Description|
|---|---|---|
|`Thread.MIN_PRIORITY`|1|Lowest priority|
|`Thread.NORM_PRIORITY`|5|Default priority|
|`Thread.MAX_PRIORITY`|10|Highest priority|

```java
class MyThread extends Thread {
    public void run() {
        System.out.println(Thread.currentThread().getName() + 
                           " Priority: " + Thread.currentThread().getPriority());
    }
}

public class PriorityExample {
    public static void main(String[] args) {
        MyThread t1 = new MyThread();
        MyThread t2 = new MyThread();
        MyThread t3 = new MyThread();

        t1.setPriority(Thread.MIN_PRIORITY);  // 1
        t2.setPriority(Thread.NORM_PRIORITY); // 5
        t3.setPriority(Thread.MAX_PRIORITY);  // 10

        t1.start();
        t2.start();
        t3.start();
    }
}
```

```
Thread-0 Priority: 1
Thread-1 Priority: 5
Thread-2 Priority: 10
```

### ⚠️ **Notes**

- Priority only acts as a **hint** to the OS scheduler — not a guarantee.
    
- The thread scheduler **may or may not** respect the priority depending on OS and JVM.
    
- Default priority for every thread = `5`.