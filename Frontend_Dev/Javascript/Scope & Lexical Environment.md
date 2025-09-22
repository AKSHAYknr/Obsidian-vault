
---
## 🔹 What is Scope?

- **Scope** defines the **current context of execution**, i.e., where variables are accessible.
    
- In JavaScript, we have:
    
    - **Global Scope** → accessible everywhere.
        
    - **Function Scope** → variables inside a function are only accessible inside it.
        
    - **Block Scope** (ES6 `let`, `const`) → variables are only accessible inside `{}`.

## 🔹 What is Scope Chain?

- When you try to **access a variable**, JavaScript first looks **in the current scope**.
    
- If not found, it goes **one level up (parent scope)**.
    
- This continues until:
    
    - The variable is found, or
        
    - The **global scope** is reached.
        
- If still not found → `ReferenceError`.
    

👉 This “chain of scopes” is called the **Scope Chain**.

```js
let a = "I am global";

function outer() {
    let b = "I am outer";

    function inner() {
        let c = "I am inner";
        console.log(a); // ✅ Found in global scope
        console.log(b); // ✅ Found in outer scope
        console.log(c); // ✅ Found in inner scope
    }

    inner();
}

outer();
```

### Execution flow:

- `inner()` looks for `a`:
    
    - Not in **inner scope** → goes to **outer scope** → not found → goes to **global scope** → ✅ found.
        
- `b` is found in **outer scope**.
    
- `c` is found in **inner scope**.

## 🔹 What is Lexical Environment?

A **Lexical Environment** is a data structure that holds:

1. **Variable environment** (local variables declared in that scope).
    
2. **Reference to its outer (parent) lexical environment**.
    

👉 In simple terms:  
Every time you create a function or a block, JavaScript creates a **lexical environment** that contains variables and knows **where to look next** if those variables are not found (the parent environment).

## 🔹 Lexical = "By Position in Code"

- "Lexical" means **where something is written in the code**.
    
- A function’s lexical environment is determined by **where it is physically placed in the source code**, not where it’s called from.


## 🔹 Important Notes

1. Inner functions can access **outer variables**, but **outer functions cannot access inner variables**.
    
2. Scope chain works **lexically** (based on code placement), not dynamically (based on where a function is called).

