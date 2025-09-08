
---

# 🔹 What is a Constructor?

- A **constructor** is a special method used to **initialize objects**.
    
- It has the **same name as the class**.
    
- It has **no return type** (not even `void`).
    
- It is called **automatically** when an object is created with `new`.

```java
class Car {
    String brand;
    int year;

    // 1. No-arg constructor
    Car() {
        this.brand = "Unknown";
        this.year = 0;
        System.out.println("No-arg constructor called");
    }

    // 2. Parameterized constructor
    Car(String brand, int year) {
        this.brand = brand;
        this.year = year;
        System.out.println("Parameterized constructor called");
    }

    // 3. Copy constructor (manual)
    Car(Car other) {
        this.brand = other.brand;
        this.year = other.year;
        System.out.println("Copy constructor called");
    }

    void display() {
        System.out.println("Brand: " + brand + ", Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        // Calls no-arg constructor
        Car car1 = new Car();
        car1.display();

        // Calls parameterized constructor
        Car car2 = new Car("Tesla", 2024);
        car2.display();

        // Calls copy constructor
        Car car3 = new Car(car2);
        car3.display();
    }
}
```

# 🔹 Constructor Chaining in Java

👉 **Constructor chaining** means **calling one constructor from another constructor** within the same class or parent class.  
This helps **reuse initialization code** and avoid duplication.

## 1. **Using `this()` → Call another constructor in the same class**

- `this()` must be the **first statement** inside a constructor.
    
- Useful when multiple constructors share common initialization.

```java
class Student {
    String name;
    int age;
    String course;

    // Constructor 1
    Student() {
        this("Unknown", 0, "Not Assigned");  // Calls parameterized constructor
        System.out.println("No-arg constructor called");
    }

    // Constructor 2
    Student(String name, int age) {
        this(name, age, "Not Assigned");  // Calls Constructor 3
        System.out.println("Two-arg constructor called");
    }

    // Constructor 3
    Student(String name, int age, String course) {
        this.name = name;
        this.age = age;
        this.course = course;
        System.out.println("Three-arg constructor called");
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age + ", Course: " + course);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student(); // starts from no-arg
        s1.display();

        Student s2 = new Student("Akshay", 22); // starts from 2-arg
        s2.display();
    }
}
```

## 2. **Using `super()` → Call parent class constructor**

- `super()` must also be the **first statement** in the child constructor.
    
- It is used to **initialize parent class variables** before child class initialization.
    
- If you don’t explicitly call it, Java automatically inserts `super()` (calling parent’s **no-arg constructor**).

```java
class Vehicle {
    String brand;

    Vehicle(String brand) {
        this.brand = brand;
        System.out.println("Vehicle constructor called");
    }
}

class Car extends Vehicle {
    int year;

    Car(String brand, int year) {
        super(brand);  // Calls Vehicle constructor
        this.year = year;
        System.out.println("Car constructor called");
    }

    void display() {
        System.out.println("Brand: " + brand + ", Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Car c = new Car("Tesla", 2024);
        c.display();
    }
}
```
