
---
## 1. **Syntax Error**

🔹 **When it happens:**  
A syntax error occurs when your code **violates JavaScript grammar rules** — the interpreter cannot even parse the code.

🔹 **Example:**

```js
console.log("Hello World"   // missing closing parenthesis
```

## 2. **Type Error**

🔹 **When it happens:**  
A type error occurs when an operation is performed on a **value of the wrong type** or when you try to use a value in an invalid way.

🔹 **Example:**

```js
let num = 5;
num.toUpperCase();  // ❌ numbers don’t have toUpperCase()
```

## 3. **Reference Error**

🔹 **When it happens:**  
A reference error happens when you try to **access a variable that doesn’t exist** (not declared or out of scope).

🔹 **Example:**

```js
console.log(myVar);   // ❌ myVar was never declared
```

## ✅ Summary

|Error Type|When It Happens|Example|
|---|---|---|
|**SyntaxError**|Code violates JS grammar (won’t run at all)|`if (true {}`|
|**TypeError**|Wrong type usage|`"abc" is not a function`|
|**ReferenceError**|Accessing undeclared/unreachable variable|`console.log(x)`|
