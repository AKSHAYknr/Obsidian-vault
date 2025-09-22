
---
## 🔹 1. Before ES6 (2015)

- JavaScript only had **`var`** for variable declarations.
    
- Issues with `var`:
    
    - Function-scoped (not block-scoped).
        
    - Hoisted (declared at the top of scope).
        
    - Could be redeclared (leading to bugs).
        

👉 To fix these, **`let`** and **`const`** were introduced in ES6.

## 🔹 2. `let` (block-scoped variable)

- Used for **variables that can change**.
    
- Block-scoped → only accessible inside `{ }`.
    
- Cannot be redeclared in the same scope.
    
- Hoisted, but **not initialized** → Temporal Dead Zone (TDZ).

```js
let x = 10;
if (true) {
    let x = 20; // different variable (block scope)
    console.log(x); // 20
}
console.log(x); // 10
```

## 🔹 3. `const` (block-scoped constant)

- Used for **constants** → variables that should not be reassigned.
    
- Must be **initialized at declaration**.
    
- Block-scoped.
    
- Cannot be redeclared in the same scope.

```js
const pi = 3.14
console.log(pi)
// pi = 3.14159; ❌ Error: Assignment to constant variable
```

✅ **Best Practice**

- Use `const` **by default**.
    
- Use `let` **only when you need to reassign**.
    
- Avoid `var` in modern JavaScript.