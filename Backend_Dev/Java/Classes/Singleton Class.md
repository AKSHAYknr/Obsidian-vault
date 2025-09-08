
---
## 🔹 What is a Singleton Class?

- A **design pattern** where only **one object (instance)** of the class is created in the JVM.
    
- Ensures **global access point** to that object.
    
- Commonly used for **logging, caching, configuration, DB connections**, etc.
    
## 🔹 Key Features

1. **Private constructor** → prevents direct object creation using `new`.
    
2. **Static reference** → holds the single instance.
    
3. **Public static method** → provides a way to access the instance.

```java
class Singleton {
    // Step 1: Create a static reference
    private static Singleton instance;

    // Step 2: Make constructor private
    private Singleton() {
        System.out.println("Singleton object created");
    }

    // Step 3: Provide a global access point
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}

public class Main {
    public static void main(String[] args) {
        Singleton obj1 = Singleton.getInstance();
        Singleton obj2 = Singleton.getInstance();

        System.out.println(obj1 == obj2); // true (both point to same object)
    }
}
```

🔹 Example 2: Thread-Safe Singleton (Lazy Initialization)

```java
class Singleton {
    private static Singleton instance;

    private Singleton() {}

    public static synchronized Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

🔒 Here `synchronized` ensures that only one thread creates the object.

🔹 Example 3: Bill Pugh Singleton (Best Practice)

```java
class Singleton {
    private Singleton() {}

    // Inner static helper class
    private static class SingletonHelper {
        private static final Singleton INSTANCE = new Singleton();
    }

    public static Singleton getInstance() {
        return SingletonHelper.INSTANCE;
    }
}
```

## 🔹 Real-World Uses

- Database connection pool (`DriverManager`)
    
- Logging frameworks
    
- Configuration managers
    
- Caches