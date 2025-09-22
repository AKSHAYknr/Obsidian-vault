
---
# 🔹 What is Reflection in Java?

**Reflection** in Java is a feature that allows a program to **inspect and manipulate classes, methods, fields, and constructors at runtime** — even if you don’t know their names at compile time.

It is part of the package:

`import java.lang.reflect.*;`

# 🔹 What Can Reflection Do?

1. Get information about classes, interfaces, methods, and fields.
    
2. Create new objects, call methods, or access fields **at runtime**.
    
3. Modify private fields or methods (breaking encapsulation).
    
4. Useful for frameworks (Spring, Hibernate, JUnit, etc.).

# 🔹 Important Reflection Classes

|Class|Purpose|
|---|---|
|`Class<T>`|Represents classes & interfaces|
|`Field`|Represents class fields (variables)|
|`Method`|Represents methods|
|`Constructor<T>`|Represents constructors|
|`Modifier`|Used to check modifiers (public, private, static, etc.)|

# 🔹 Common Uses of Reflection

1. **Frameworks** → Spring, Hibernate use reflection to inject dependencies & map objects to DB tables.
    
2. **Testing** → JUnit uses reflection to run test methods dynamically.
    
3. **Serialization/Deserialization** → Convert objects to JSON/XML and back.
    
4. **IDE & Tools** → Eclipse/IntelliJ use reflection for code assistance.
    

# 🔹 Limitations / Disadvantages

1. **Performance overhead** → slower than normal method calls.
    
2. **Security risk** → can break encapsulation (`setAccessible(true)`).
    
3. **Complex code** → harder to maintain.
    
# 🔹 Summary

- **Reflection** lets you **analyze and modify classes, methods, fields at runtime**.
    
- Powered by classes in `java.lang.reflect` package.
    
- Very powerful, but should be used carefully (only when necessary).