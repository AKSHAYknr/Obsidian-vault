
---
### **S – Single Responsibility Principle (SRP)**

**Definition:** A class should have **only one reason to change**.  
**Meaning:** Each class should do **one thing** and do it well.

### **O – Open/Closed Principle (OCP)**

**Definition:** Software entities (classes, modules, functions) should be **open for extension but closed for modification**.  
**Meaning:** You should **extend behavior without modifying existing code**.

### **L – Liskov Substitution Principle (LSP)**

**Definition:** Subtypes must be substitutable for their base types.  
**Meaning:** A derived class should **behave like its parent class** without breaking functionality.

### **I – Interface Segregation Principle (ISP)**

**Definition:** Clients should not be forced to depend on **interfaces they don’t use**.  
**Meaning:** Prefer **smaller, specific interfaces** over a big, general-purpose one.

### **D – Dependency Inversion Principle (DIP)**

**Definition:**

1. High-level modules should **not depend on low-level modules**. Both should depend on **abstractions**.
    
2. Abstractions should not depend on details. Details should depend on abstractions.


✅ **Summary Table:**

|Principle|Short Description|
|---|---|
|SRP|One class, one responsibility|
|OCP|Open for extension, closed for modification|
|LSP|Subtypes should replace base types seamlessly|
|ISP|Prefer many small interfaces over one large interface|
|DIP|Depend on abstractions, not concrete implementations|