
---

## ✅ Concrete Class in Java

A **concrete class** is a regular Java class that has a complete implementation.

- It contains fields (variables), methods, and constructors.
    
- It can be instantiated using the `new` keyword.
    
- It may or may not extend another class or implement an interface.

```java
public class Dog {
    // field
    private String name;

    // constructor
    public Dog(String name) {
        this.name = name;
    }

    // method
    public void bark() {
        System.out.println(name + " says Woof!");
    }

    // main method
    public static void main(String[] args) {
        Dog dog = new Dog("Tommy");  // creating object of concrete class
        dog.bark();
    }
}
```

👉 In short:  
A **concrete class** = A **normal class** in Java that you can create an object of and use directly.