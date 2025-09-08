
---
# 🟢 1. **Undefined**

- A variable is **declared** but not assigned a value.
    
- JavaScript automatically initializes it with **`undefined`**.
    

### Example:

```js
var x;
console.log(x); // undefined
```

Here:

- `x` is declared but not initialized → JS assigns `undefined`.

👉 So, **`undefined` means variable exists, but has no value yet.**

# 🟢 2. **Not Defined**

- A variable is **not declared at all** in the scope.
    
- Accessing it throws a **ReferenceError**.

```js
console.log(y); // ❌ ReferenceError: y is not defined
```

Here:

- `y` was never declared.
    
- JavaScript cannot find it in memory.

✅ **In short:**

- **`undefined`** → variable exists but has no value.
    
- **`not defined`** → variable doesn’t exist at all in current scope.
