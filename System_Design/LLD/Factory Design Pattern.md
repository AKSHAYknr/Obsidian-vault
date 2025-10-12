
---

## Overview

The Factory pattern is a **creational design pattern** that provides an interface for creating objects without specifying their exact classes. It encapsulates object creation logic and promotes loose coupling by eliminating the need to bind application-specific classes into the code.

Types of Factory Patterns :

1. **Simple Factory** (not a formal pattern, but widely used)
2. **Abstract Factory** (formal GoF pattern)

```mermaid
classDiagram
    class Client {
        +main()
    }
    
    class SimpleFactory {
        +createProduct(type) Product
    }
    
    class Product {
        <<interface>>
        +operation()
    }
    
    class ConcreteProductA {
        +operation()
    }
    
    class ConcreteProductB {
        +operation()
    }
    
    Client --> SimpleFactory
    SimpleFactory --> Product
    Product <|.. ConcreteProductA
    Product <|.. ConcreteProductB
```

Abstract Factory Pattern :

The Abstract Factory pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes.

```mermaid
classDiagram
    class AbstractFactory {
        <<interface>>
        +createProductA() AbstractProductA
        +createProductB() AbstractProductB
    }
    
    class ConcreteFactory1 {
        +createProductA() AbstractProductA
        +createProductB() AbstractProductB
    }
    
    class ConcreteFactory2 {
        +createProductA() AbstractProductA
        +createProductB() AbstractProductB
    }
    
    class AbstractProductA {
        <<interface>>
        +operationA()
    }
    
    class AbstractProductB {
        <<interface>>
        +operationB()
    }
    
    class ProductA1 {
        +operationA()
    }
    
    class ProductA2 {
        +operationA()
    }
    
    class ProductB1 {
        +operationB()
    }
    
    class ProductB2 {
        +operationB()
    }
    
    AbstractFactory <|.. ConcreteFactory1
    AbstractFactory <|.. ConcreteFactory2
    AbstractProductA <|.. ProductA1
    AbstractProductA <|.. ProductA2
    AbstractProductB <|.. ProductB1
    AbstractProductB <|.. ProductB2
    ConcreteFactory1 ..> ProductA1
    ConcreteFactory1 ..> ProductB1
    ConcreteFactory2 ..> ProductA2
    ConcreteFactory2 ..> ProductB2
```


