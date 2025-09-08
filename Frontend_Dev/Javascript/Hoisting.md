
---

# 🟢 What is Hoisting?

👉 **Hoisting** means that during the **creation phase** of the Execution Context, **JavaScript moves variable and function declarations to the top of their scope (memory is reserved before execution starts).**

- But! Only **declarations** are hoisted, not **initializations/assignments**.

# 🟢 In Short

1. **Variables with `var`** → hoisted but initialized as `undefined`.
    
2. **Variables with `let` & `const`** → hoisted but in **TDZ** (can’t use before declaration).
    
3. **Function declarations** → hoisted fully (safe to call before definition).
    
4. **Function expressions / arrow functions** → hoisted as variables (so not callable before definition).
