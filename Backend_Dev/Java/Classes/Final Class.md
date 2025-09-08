
---
## 🔹 What is a `final class`?

- A **class declared with `final`** keyword cannot be **extended** (i.e., no inheritance).
    
- It can still:
    
    - Have constructors
        
    - Contain methods and fields
        
    - Be instantiated like normal
        

👉 This is used when you want to make a class **non-inheritable**.

```java
final class Vehicle {
    public void display() {
        System.out.println("This is a vehicle.");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehicle v = new Vehicle();
        v.display();
    }
}
```

✅ Works fine.

## 🔹 Why Use `final class`?

1. **Security** → Prevents altering sensitive classes (e.g., `String`, `Integer` are final in Java).
    
2. **Immutability** → Often used with immutable classes.
    
3. **Design choice** → To ensure class behavior cannot be changed via inheritance.