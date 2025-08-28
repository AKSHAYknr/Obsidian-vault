
---

In **Java**, the **`Object` class** is the root of the class hierarchy.  
Every class in Java **implicitly** inherits from `Object`, either directly or indirectly.

That means all classes you create automatically have the methods defined in `Object`.

### 📌 Key Points about `Object` class:

1. It is present in the **`java.lang`** package.
    
2. If you don’t explicitly extend another class, your class automatically extends `Object`.
    
3. Provides general-purpose methods that are common to all objects.

### 🔑 Important Methods of `Object` Class

| Method                              | Description                                                                                          |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------- |
| `public String toString()`          | Returns string representation of the object. Usually overridden.                                     |
| `public boolean equals(Object obj)` | Compares two objects for equality. By default, it checks reference equality (same memory location).  |
| `public int hashCode()`             | Returns an integer hash code (used in HashMap, HashSet). Should be overridden with `equals()`.       |
| `protected Object clone()`          | Creates and returns a copy of the object (shallow copy). Class must implement `Cloneable` interface. |
| `protected void finalize()`         | Called by garbage collector before object destruction (deprecated in Java 9+).                       |
| `public Class<?> getClass()`        | Returns the runtime class of the object.                                                             |
| `public void notify()`              | Wakes up a single thread waiting on this object’s monitor.                                           |
| `public void notifyAll()`           | Wakes up all threads waiting on this object’s monitor.                                               |
| `public void wait()`                | Causes thread to wait until another thread calls `notify()`/`notifyAll()`.                           |
