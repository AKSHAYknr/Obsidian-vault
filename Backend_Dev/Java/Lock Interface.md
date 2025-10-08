
---
It’s one of the most powerful concurrency tools in Java — giving **more control** and **flexibility** than `synchronized`.

---

## 🔒 **1. What is the Lock Interface?**

The `Lock` interface provides a **thread synchronization mechanism** similar to `synchronized`,  
but with **explicit control** over acquiring and releasing locks.

👉 In short:

> `Lock` = Manual version of `synchronized`, but with more capabilities.

## 🧠 **2. Why Use Lock Instead of synchronized?**

|Limitation of `synchronized`|`Lock` Solution|
|---|---|
|Automatically acquires/releases|You control when to lock/unlock|
|Cannot attempt a non-blocking lock|`tryLock()` lets you attempt|
|Cannot respond to interrupts while waiting|`lockInterruptibly()` allows it|
|Only one condition per monitor|Multiple conditions via `newCondition()`|
|No fairness policy|Supports fair locking (`new ReentrantLock(true)`)|

## ⚙️ **3. Lock Interface — Main Methods**

|Method|Description|
|---|---|
|`void lock()`|Acquires the lock, blocks if unavailable|
|`void unlock()`|Releases the lock|
|`boolean tryLock()`|Tries to acquire lock without waiting|
|`boolean tryLock(long time, TimeUnit unit)`|Waits for specified time|
|`void lockInterruptibly()`|Acquires lock unless the thread is interrupted|
|`Condition newCondition()`|Creates a `Condition` for thread coordination|

```java
import java.util.concurrent.locks.Lock;
import java.util.concurrent.locks.ReentrantLock;

class SharedResource {
    private final Lock lock = new ReentrantLock();

    public void printNumbers() {
        lock.lock();  // acquire lock manually
        try {
            for (int i = 1; i <= 5; i++) {
                System.out.println(Thread.currentThread().getName() + " -> " + i);
                Thread.sleep(500);
            }
        } catch (InterruptedException e) {
            e.printStackTrace();
        } finally {
            lock.unlock();  // always release lock in finally
        }
    }
}

public class LockExample {
    public static void main(String[] args) {
        SharedResource resource = new SharedResource();

        Thread t1 = new Thread(resource::printNumbers, "Thread-1");
        Thread t2 = new Thread(resource::printNumbers, "Thread-2");

        t1.start();
        t2.start();
    }
}
```

### 🧾 Output:

```
Thread-1 -> 1 
Thread-1 -> 2 
Thread-1 -> 3 
Thread-1 -> 4 
Thread-1 -> 5 
Thread-2 -> 1 
Thread-2 -> 2 
Thread-2 -> 3 
Thread-2 -> 4 
Thread-2 -> 5
```
## 🧠 **8. Types of Lock Implementations**

|Implementation|Description|
|---|---|
|`ReentrantLock`|Most common, allows a thread to re-acquire its own lock|
|`ReentrantReadWriteLock`|Has separate read and write locks — multiple readers or one writer|
|`StampedLock`|Optimized for high concurrency (Java 8+) — provides optimistic reads|
