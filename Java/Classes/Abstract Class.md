
---

An **abstract class** is a class that is declared with the keyword `abstract`.

- It **cannot be instantiated** (you can’t do `new AbstractClass()` directly).
    
- It can have:
    
    - **Abstract methods** (without body, just declaration).
        
    - **Concrete methods** (with body, normal methods).
        
- It is used as a **blueprint** for other classes.

```java
abstract class ClassName {
    // abstract method (no body)
    abstract void method1();

    // concrete method (with body)
    void method2() {
        System.out.println("This is a concrete method");
    }
}
```

## 🔑 Key Points about Abstract Classes

1. **Cannot be instantiated** directly.
    
2. Can have **constructors, fields, methods (abstract + concrete)**.
    
3. A subclass must **implement all abstract methods**, or else it must also be declared abstract.
    
4. Used when you want to **provide a base class with partial implementation**.