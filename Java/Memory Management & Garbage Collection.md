
---

## 🔹 Memory Management in Java

Java manages memory automatically (unlike C/C++ where developers must allocate and free memory manually).

### 1. **Memory Areas in JVM**

When you run a Java program, the JVM divides memory into different parts:

1. **Heap Memory (Runtime Data Area)**
    
    - Where objects and their instance variables are stored.
        
    - Divided into:
        
        - **Young Generation** (new objects, includes Eden + Survivor spaces)
            
        - **Old (Tenured) Generation** (long-living objects)
            
        - **Permanent Generation / Metaspace (Java 8+)** (class metadata, method definitions)
            
2. **Stack Memory**
    
    - Stores local variables, method calls, and references.
        
    - Each thread has its own stack.
        
    - Automatically freed when method ends.
        
3. **Method Area (Metaspace in Java 8+)**
    
    - Stores class-level information: class definitions, static variables, method bytecode.
        
4. **PC Register**
    
    - Keeps track of which instruction the thread is currently executing.
        
5. **Native Method Stacks**
    
    - Stores native method (non-Java) calls.

## 🔹 Garbage Collection (GC) in Java

Since memory is finite, Java has a **Garbage Collector** to automatically free unused memory.

### 1. **What is Garbage?**

- Any object that is no longer referenced in the program.
    
- Example:
```java
String str = new String("Hello");
str = null;
```

### 2. **How GC Works**

- The GC identifies objects that are **not reachable** by any live thread or static reference.
    
- It then reclaims that memory for reuse.
    

### 3. **Garbage Collection Process**

- **Mark** → GC marks all reachable objects.
    
- **Sweep** → Removes all unreferenced objects.
    
- **Compact** → Rearranges memory to avoid fragmentation.
    

This is called **Mark-Sweep-Compact Algorithm**.

### 4. **Types of Garbage Collectors in Java**

- **Serial GC** → For small apps, single-threaded.
    
- **Parallel GC** → Multi-threaded, improves throughput.
    
- **CMS (Concurrent Mark Sweep) GC** → Low-latency applications.
    
- **G1 (Garbage First) GC** → Default in Java 9+, balances throughput + low pause times.

1. **Heap Memory Layout**
┌─────────────────────────── JVM Heap ───────────────────────────┐
│                                                                                                                     │
│   Young Generation              Old Generation (Tenured)                              │
│   ┌──────────────┐              ┌───────────────────────────┐                  │
│   │   Eden Space    │               |        Long-lived Objects            |                   │
│   ├──────────────┤              └───────────────────────────┘                  │
│   │ Survivor S0       │              Metaspace (Class Metadata)                          │
│   ├──────────────┤                                                                                     │
│   │ Survivor S1       │                                                                                     │
│   └──────────────┘                                                                                     │
└────────────────────────────────────────────────────────────────┘

- **Eden Space** → new objects are created here.
    
- **Survivor Spaces (S0, S1)** → objects that survive minor collections move here.
    
- **Old Generation** → objects that survive long enough are promoted here.
    
- **Metaspace** → stores class definitions, method metadata.

✅ So in short:
- **Young Gen (Eden + Survivor)** → Minor GC (fast, frequent)
    
- **Old Gen** → Major GC (slow, occasional)
    
- **Mark-Sweep-Compact** ensures memory is reused efficiently.