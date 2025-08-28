
---

#### **Nested Class**

In Java, a **nested class** is simply a class defined inside another class.  
It helps logically group classes that are only used in one place, increases encapsulation, and can make your code more readable.

## Types of Nested Classes in Java

### 1. **Static Nested Class**

- Declared with `static` keyword inside another class.
    
- Can access only **static members** of the outer class.
    
- Works like a normal top-level class but scoped inside the outer class.

```java
class Outer {
    static int x = 10;

    // Static nested class
    static class Nested {
        void display() {
            System.out.println("Static nested class: x = " + x);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer.Nested obj = new Outer.Nested(); // no need of Outer object
        obj.display();
    }
}
```

### 2. **Non-Static Inner Class**

- Associated with an instance of the outer class.
    
- Can access both **static and non-static members** of the outer class.
    
- Needs an object of the outer class to be created

```java
class Outer {
    private String msg = "Hello from Outer!";

    // Inner class
    class Inner {
        void display() {
            System.out.println("Inner class: " + msg);
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Outer outer = new Outer();
        Outer.Inner inner = outer.new Inner(); // needs outer object
        inner.display();
    }
}
```

### 3. **Local Inner Class**

- Defined **inside a method** of the outer class.
    
- Can access method’s local variables only if they are `final` or _effectively final_.

```java
class Outer {
    void outerMethod() {
        int num = 42; // effectively final

        class LocalInner {
            void display() {
                System.out.println("Local inner class: num = " + num);
            }
        }

        LocalInner inner = new LocalInner();
        inner.display();
    }
}

public class Main {
    public static void main(String[] args) {
        new Outer().outerMethod();
    }
}
```

### 4. **Anonymous Inner Class**

- A class without a name, defined and instantiated in one place.
    
- Mostly used for **implementing interfaces** or **abstract classes** quickly.

```java
interface Greeting {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        // Anonymous inner class
        Greeting greet = new Greeting() {
            public void sayHello() {
                System.out.println("Hello from Anonymous Inner Class!");
            }
        };

        greet.sayHello();
    }
}
```
