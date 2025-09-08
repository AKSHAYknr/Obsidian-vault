
---

# 🟢 1. `window` Object

- In browsers, the **`window`** object is the **global object**.
    
- All global variables and functions automatically become properties of `window`.
    
- It represents the **browser window** (tabs, alerts, storage, timers, etc.).

```js
var a = 10;
console.log(window.a); // 10

function greet() {
  console.log("Hello");
}
window.greet(); // "Hello"
```

# 🟢 2. `this` Keyword

The value of `this` depends on **how and where** a function is called (context).

# 🟢 In Short

- **`window`** → Global object in browsers.
    
- **`this`** → Refers to the execution context:
    
    - Global scope → `window` (browser) or `global` (Node).
        
    - Object method → the object itself.
        
    - Arrow function → takes `this` from outer scope.
        
    - Constructor → the new object created.
        
    - With `call/apply/bind` → manually defined.

