
---

#Overview

The Observer pattern is a **behavioral design pattern** where an object (Subject) maintains a list of dependents (Observers) and notifies them automatically of any state changes.

#Pattern Structure


```mermaid
classDiagram
    class Subject {
        <<interface>>
        +registerObserver(Observer)
        +removeObserver(Observer)
        +notifyObservers()
    }
    
    class Observer {
        <<interface>>
        +update()
    }
    
    class ConcreteSubject {
        -List~Observer~ observers
        -state
        +registerObserver(Observer)
        +removeObserver(Observer)
        +notifyObservers()
        +getState()
        +setState()
    }
    
    class ConcreteObserverA {
        -subject
        +update()
    }
    
    class ConcreteObserverB {
        -subject
        +update()
    }
    
    Subject <|.. ConcreteSubject
    Observer <|.. ConcreteObserverA
    Observer <|.. ConcreteObserverB
    ConcreteSubject o-- Observer : notifies
```

