
---
## 🔹 What is an Immutable Class?

- An **immutable class** is a class whose objects **cannot be changed** once created.
    
- All fields are **final** and private.
    
- No **setter methods** (only getters).
    
- If a field is mutable (like `Date`, `List`, `Map`), return a **defensive copy** instead of the original object.
    

👉 Most famous immutable class in Java = `String`.

---

## 🔹 Rules to Create an Immutable Class

1. Declare the class as `final` (optional, but prevents subclassing).
    
2. Make all fields `private` and `final`.
    
3. Don’t provide setters.
    
4. Initialize fields via constructor.
    
5. If a field is mutable, return a **copy** in getters (not the original reference).

```java
public final class Student{
	private final int id;
    private final String name;

    // Constructor
    public Student(int id, String name) {
        this.id = id;
        this.name = name;
    }
    
	 // Only getters, no setters
    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }	
}
```

🔹 Immutable Class with Mutable Field (`List`)

```java
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;

public final class Student {
    private final int id;
    private final String name;
    private final List<String> subjects; // Mutable field

    // Constructor
    public Student(int id, String name, List<String> subjects) {
        this.id = id;
        this.name = name;
        // Defensive copy to protect internal list
        this.subjects = new ArrayList<>(subjects);
    }

    public int getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    // Getter returns unmodifiable copy
    public List<String> getSubjects() {
        return Collections.unmodifiableList(subjects);
    }

    @Override
    public String toString() {
        return "Student{id=" + id + ", name='" + name + "', subjects=" + subjects + "}";
    }
}
```

## 🔹 Why Use Immutable Classes?

1. **Thread-safe** → no synchronization needed.
    
2. **Cache-friendly** → can safely reuse.
    
3. **Security** → cannot be altered once created.
    
4. Used in **keys for Map, Set** (because hashCode won’t change).
    
## 🔹 Examples of Immutable Classes in Java

- `String`
    
- Wrapper classes (`Integer`, `Double`, `Boolean`, etc.)
    
- `LocalDate`, `LocalTime`, `LocalDateTime` (Java 8 Date-Time API)