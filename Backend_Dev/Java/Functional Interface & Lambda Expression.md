
---
# 🔹 Functional Interface

### ✅ Definition:

A **functional interface** is an interface that has **exactly one abstract method**.

- It **may** contain multiple `default` or `static` methods.
    
- Annotated with `@FunctionalInterface` (optional, but recommended).
    

👉 Functional interfaces are the foundation of **lambda expressions**.

```java
@FunctionalInterface
interface Greeting{
	void sayHello(String name); // only one abstract method
}
```

# 🔹 Lambda Expression

### ✅ Definition:

A **lambda expression** is a short way to provide an implementation for a functional interface.  
It eliminates the need for **anonymous classes**.

**Syntax:**

```java
(parameters) -> { body }
```

🔸 Example Without Lambda (Old Way):

```java
Greeting g = new Greeting(){
	@override
	void sayHello(String name){
		System.out.println(name);
	}
};
g.sayHello("Akshay")
```

🔸 Example With Lambda:

```java
Greeting g = (name) -> System.out.println("Hello, " + name);
g.sayHello("Akshay");
```

# 🔹 Built-in Functional Interfaces (Java 8+)

Java provides many functional interfaces in `java.util.function` package. Some important ones:

|Interface|Abstract Method|Example Usage|
|---|---|---|
|`Runnable`|`run()`|Multithreading|
|`Callable<T>`|`call()`|Return result in thread|
|`Predicate<T>`|`test(T t)` → boolean|Filtering (true/false)|
|`Consumer<T>`|`accept(T t)`|Consuming input|
|`Supplier<T>`|`get()`|Supplying values|
|`Function<T,R>`|`apply(T t)` → R|Transforming input|
# 🔹 Why Functional Interfaces + Lambdas?

1. **Cleaner code** → replaces bulky anonymous classes.
    
2. **Functional programming style** → concise & expressive.
    
3. **Useful in Streams API** (filter, map, reduce).
    
4. **Better readability** & maintainability.
    

✅ In short:

- **Functional Interface** = "Contract with one abstract method."
    
- **Lambda Expression** = "Quick way to implement that method inline."