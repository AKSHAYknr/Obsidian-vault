
---
#Overview

The Decorator pattern is a **structural design pattern** that allows you to attach new behaviors to objects dynamically by placing these objects inside special wrapper objects called decorators. It provides a flexible alternative to subclassing for extending functionality.

```mermaid
classDiagram
    class Component {
        <<interface>>
        +operation()
    }
    
    class ConcreteComponent {
        +operation()
    }
    
    class Decorator {
        <<abstract>>
        -Component wrappedObj
        +operation()
    }
    
    class ConcreteDecoratorA {
        +operation()
        +addedBehavior()
    }
    
    class ConcreteDecoratorB {
        +operation()
        +addedBehavior()
    }
    
    Component <|.. ConcreteComponent
    Component <|.. Decorator
    Component --o Decorator : wraps
    Decorator <|-- ConcreteDecoratorA
    Decorator <|-- ConcreteDecoratorB
```
