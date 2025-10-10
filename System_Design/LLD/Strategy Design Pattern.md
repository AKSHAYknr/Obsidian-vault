
---
**Type:** Behavioral Pattern  
**Purpose:** Let **different algorithms** be **interchangeable** at runtime.

## **1. Idea (Simple)**

- Imagine you have **multiple ways to do something**.
    
- Instead of hardcoding `if-else` everywhere, **encapsulate each way** in its own class.
    
- Let the **client pick the strategy** they want.

## **2. Key Components**

- **Strategy (interface)** → defines the algorithm.
    
- **ConcreteStrategy (class)** → implements the algorithm.
    
- **Context (class)** → uses a Strategy to perform the task.

## **3. Real-Life Analogy**

- **Payment methods in shopping app**: Credit Card, PayPal, UPI.
    
- Shopping cart **doesn’t care how you pay** → it just uses the selected payment strategy.

```java
interface PaymentStrategy {
    void pay(int amount);
}

class CreditCardPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid " + amount + " with Credit Card");
    }
}

class PayPalPayment implements PaymentStrategy {
    public void pay(int amount) {
        System.out.println("Paid " + amount + " with PayPal");
    }
}

class ShoppingCart {
    private PaymentStrategy strategy;
    void setStrategy(PaymentStrategy strategy) { this.strategy = strategy; }
    void checkout(int amount) { strategy.pay(amount); }
}

// Usage
ShoppingCart cart = new ShoppingCart();
cart.setStrategy(new CreditCardPayment());
cart.checkout(500);
cart.setStrategy(new PayPalPayment());
cart.checkout(1000);
```

## **5. Why Use It?**

- Avoids long `if-else` chains.
    
- Makes code **extensible** → add new strategy without changing old code.
    
- Promotes **composition over inheritance**.