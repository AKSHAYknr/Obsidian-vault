
---
## 🔹 What is the Temporal Dead Zone?

- The **TDZ** is the time between **when a variable is hoisted** and **when it is actually initialized**.
    
- Variables declared with **`let`** and **`const`** are **hoisted** (moved to the top of their scope), but they are **not initialized with a default value** (`undefined`) like `var`.
    
- Accessing them **before initialization** → `ReferenceError`.

👉 In simple terms:  
**The variable exists, but you can’t use it yet.**

```js
console.log(a); // ❌ ReferenceError (TDZ)
let a = 5;
console.log(a); // ✅ 5
```

Explanation:

- `a` is hoisted, but uninitialized → TDZ until `let a = 5;` executes.

```js
console.log(a); // ❌ ReferenceError (TDZ)
const a = 10;
console.log(a); // ✅ 10
```

👉 Same TDZ behavior as `let`.  
Difference: `const` **must** be initialized at declaration.

✅ **Summary**

- TDZ = the "forbidden zone" between variable hoisting and initialization.
    
- Applies to `let` and `const`.
    
- Avoids accidental use of variables before they’re ready.
