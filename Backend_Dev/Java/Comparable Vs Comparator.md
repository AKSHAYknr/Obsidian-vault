
---
# 🔹 Comparable in Java

### ✅ Definition

- `Comparable` is an **interface** in `java.lang` package.
    
- It is used to define the **natural ordering** of objects.
    
- A class implements `Comparable` and overrides `compareTo()`.
    

### ✅ Method

`int compareTo(T o);`

- Returns **negative** → current object < given object
    
- Returns **zero** → equal
    
- Returns **positive** → current object > given object.

```java
class Student implements Comparable<Student> {
    int id;
    String name;

    Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    @Override
    public int compareTo(Student other) {
        return this.id - other.id; // sort by id
    }
}

public class Main {
    public static void main(String[] args) {
        List<Student> list = new ArrayList<>();
        list.add(new Student(2, "Akshay"));
        list.add(new Student(1, "John"));
        list.add(new Student(3, "Priya"));

        Collections.sort(list); // uses compareTo

        for (Student s : list) {
            System.out.println(s.id + " " + s.name);
        }
    }
}
```

# 🔹 Comparator in Java

### ✅ Definition

- `Comparator` is an **interface** in `java.util` package.
    
- Used to define **custom ordering** (different from natural ordering).
    
- Useful when:
    
    1. Class doesn’t implement `Comparable`.
        
    2. You want multiple sorting criteria.
        

### ✅ Method

`int compare(T o1, T o2);`

```java
import java.util.*;

class Student {
    int id;
    String name;

    Student(int id, String name) {
        this.id = id;
        this.name = name;
    }
}

class NameComparator implements Comparator<Student> {
    public int compare(Student s1, Student s2) {
        return s1.name.compareTo(s2.name); // sort by name
    }
}

public class Main {
    public static void main(String[] args) {
        List<Student> list = new ArrayList<>();
        list.add(new Student(2, "Akshay"));
        list.add(new Student(1, "John"));
        list.add(new Student(3, "Priya"));

        Collections.sort(list, new NameComparator());

        for (Student s : list) {
            System.out.println(s.id + " " + s.name);
        }
    }
}
```

# 🔹 Key Differences

| Feature          | Comparable                          | Comparator                           |
| ---------------- | ----------------------------------- | ------------------------------------ |
| Package          | `java.lang`                         | `java.util`                          |
| Method           | `compareTo(Object o)`               | `compare(Object o1, Object o2)`      |
| Sorting order    | Defines **natural order**           | Defines **custom order**             |
| Modifies class   | Class must implement it             | No need to modify class              |
| Multiple sorting | Only **one natural order** possible | Can define **multiple comparators**  |
| Example use      | Sort students by `id` (default)     | Sort students by `name`, `age`, etc. |
# 🔹 Summary

- **Use `Comparable`** → when you want a **default / natural ordering** (e.g., sort by ID).
    
- **Use `Comparator`** → when you want **custom / multiple ordering** (e.g., sort by name, then age).