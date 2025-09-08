
---
## 🔹 What is a Generic Class in Java?

A **generic class** is a class that can work with **different data types** without writing separate code for each type.  
It uses **type parameters** (like `<T>`, `<E>`, `<K, V>`) that get replaced with actual types when the object is created.

Think of it as a **template** for classes.

```java
class ClassName<T> {
    // T can be used as a data type inside this class
    private T data;

    // constructor
    public ClassName(T data) {
        this.data = data;
    }

    // getter
    public T getData() {
        return data;
    }

    // setter
    public void setData(T data) {
        this.data = data;
    }
}
```

Here:

- `T` is a **type parameter** (can be replaced with `Integer`, `String`, `Double`, or even custom classes).
    
- You can use multiple type parameters like `<K, V>` for key-value pairs.

```java
class Pair<K, V> {
    private K key;
    private V value;

    public Pair(K key, V value) {
        this.key = key;
        this.value = value;
    }

    public void display() {
        System.out.println("Key: " + key + " , Value: " + value);
    }
}
```

## 🔹 Why Use Generics?

1. **Code Reusability** → Write once, use for any type.
    
2. **Type Safety** → No need for casting; compiler checks types.
    
3. **Readability & Maintainability** → Clear, consistent code.
