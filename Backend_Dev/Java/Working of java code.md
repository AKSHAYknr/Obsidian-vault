
---
When you write and run a Java program, this is what happens:

1. **Write Code (.java file)**  
    You write Java code in a file with `.java` extension.  

Example:

```java
public class Main {
	public static void main(String[] args){
		System.out.println("Hello java");
	}
}
```

**2. Compilation (javac)**  
The **Java Compiler** (`javac`) converts `.java` file into **bytecode** stored in a `.class` file.

- Human-readable code → Bytecode (not machine-specific).

**3. Execution (java command)**

- The **JVM (Java Virtual Machine)** loads the `.class` file.
    
- The **Class Loader** loads required classes.
    
- **Bytecode Verifier** checks for security & correctness.
    
- The **Interpreter/JIT Compiler** converts bytecode into **native machine code**.
    
- The CPU executes the machine code.

# 🔹 JDK, JRE, JVM (The Difference)

## 1. **JVM (Java Virtual Machine)**

- It is the **engine** that runs Java bytecode.
    
- Converts bytecode → machine code.
    
- Platform dependent (different JVMs for Windows, Linux, etc.).
    
- Responsibilities:
    
    - Class loading
        
    - Bytecode verification
        
    - Execution (Interpreter + JIT)
        
    - Memory management (Garbage Collection)
        

---

## 2. **JRE (Java Runtime Environment)**

- Provides **everything needed to run** a Java program.
    
- Includes:
    
    - JVM
        
    - Core libraries (java.lang, java.util, etc.)
        
    - Supporting files
        
- ❌ Does NOT contain compiler (`javac`) → cannot develop, only run programs.
    

👉 JRE = JVM + Libraries

---

## 3. **JDK (Java Development Kit)**

- Full **development kit** for Java.
    
- Includes:
    
    - JRE (so you can run programs)
        
    - JVM
        
    - Development tools (javac compiler, debugger, jar, javadoc, etc.)
        
- ✅ Used by developers to **write, compile, and run** Java programs.
    

👉 JDK = JRE + Development tools