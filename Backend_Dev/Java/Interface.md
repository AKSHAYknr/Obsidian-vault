
---
## 🔹 What is an Interface in Java?

An **interface** in Java is like a **contract** that defines a set of **abstract methods (without implementation)** that a class must implement.

It is used to achieve **abstraction** and **multiple inheritance**.

## 🔹 Key Points:

1. Declared using the `interface` keyword.
    
2. Can contain:
    
    - **Abstract methods** (before Java 8).
        
    - **Default methods** (from Java 8).
        
    - **Static methods** (from Java 8).
        
    - **Private methods** (from Java 9).
        
3. All methods in an interface are implicitly:
    
    - `public abstract` (unless default/static/private).
        
4. All variables are implicitly:
    
    - `public static final` (constants).
        
5. A class uses `implements` keyword to implement an interface.
    
6. A class can implement **multiple interfaces** (solves multiple inheritance issue).

```java
// Interface
interface Animal {
    void sound();  // abstract method
    void sleep();
}

// Implementing interface
class Dog implements Animal {
    @Override
    public void sound() {
        System.out.println("Dog barks");
    }

    @Override
    public void sleep() {
        System.out.println("Dog sleeps");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();
        a.sound();
        a.sleep();
    }
}
```

## 🔹 Difference: Abstract Class vs Interface

| Feature     | Abstract Class                          | Interface                                               |
| ----------- | --------------------------------------- | ------------------------------------------------------- |
| Methods     | Can have abstract + concrete methods    | Only abstract (till Java 7), default & static (Java 8+) |
| Variables   | Instance & static variables             | Only `public static final` (constants)                  |
| Inheritance | Single inheritance                      | Multiple inheritance supported                          |
| Constructor | Can have constructors                   | Cannot have constructors                                |
| Use Case    | When classes share **state + behavior** | When classes share **only behavior contract**           |

## 🔹 Summary

- **Default methods** → To add new methods in interfaces **without breaking old code** (backward compatibility).
    
- **Static methods** → To keep **utility/helper methods** inside the interface itself, instead of separate utility classes.

- **Java 8**: Added `default` & `static` methods → but caused code duplication issues.
    
- **Java 9**: Introduced `private` methods → so interfaces can have **reusable internal helper methods** without polluting the public API.