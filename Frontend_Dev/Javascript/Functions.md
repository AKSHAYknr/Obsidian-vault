
---
In JavaScript, **functions are "first-class citizens" (or first-class functions)**.  
This means functions are treated like any other value (numbers, strings, objects).

👉 In other words, you can:

1. **Assign functions to variables**
    
2. **Pass functions as arguments to other functions**
    
3. **Return functions from other functions**
    
4. **Store functions in data structures (arrays, objects, maps, etc.)**

#### 🔹 Function Statement (aka Function Declaration)

```js
function greet(){
	console.log("Hello")
}
```

✅ **Key Points:**

- **Hoisted**: You can call it **before** it’s defined.
    
- Must have a **name** (not anonymous).
    
- Added to the **scope at compile time**

#### 🔹 Function Expression

```js
const greet = function(){
	console.log("Hello!")
}
```

✅ **Key Points:**

- **Not hoisted** the same way.
    
- Stored in a variable, so can be **anonymous** or **named**.
    
- Becomes available only **after execution reaches that line**.


#### 🔹 What is an Anonymous Function?

An **anonymous function** is a function **without a name**.  
It’s usually used where functions are passed as **values** (like callbacks, event handlers, IIFEs, etc.).

```js
const greet = function(){
	console.log("Hello");
}
greet();
```

Here, the function has no name → it’s stored in the variable `greet`.

#### 🔹 What is a Named Function Expression?

A **named function expression** is when you assign a function **with a name** to a variable.

```js
const greet = function sayHello(name) {
  console.log("Hello, " + name);
};

greet("Akshay"); // ✅ Hello, Akshay
sayHello("Vyshnavi"); // ❌ ReferenceError: sayHello is not defined
```

👉 Here:

- `sayHello` is the **function name**, but it’s **not available outside** the function itself.
    
- Only the variable `greet` can be used to call the function from outside.

#### 🔹 Parameters

- **Placeholders/variables** defined in the **function definition**.
    
- They **receive values** when the function is called.
    
- Think of them as _“inputs expected by the function”_.
    

### Example:

```js
function greet(name) {  // <-- "name" is a parameter 
  console.log("Hello, " + name); 
}
```

Here, `name` is the **parameter**.

#### 🔹 Arguments

- **Actual values** you pass to the function when calling it.
    
- They **get assigned** to the function’s parameters.
    

### Example:

```js
greet("Akshay");  // <-- "Akshay" is an argument
```

Here, `"Akshay"` is the **argument** that gets assigned to `name`.

#### 🔹 What are Arrow Functions?

Arrow functions were introduced in **ES6 (ECMAScript 2015)**.  
They provide a **shorter syntax** for writing functions and behave differently with `this`.

#### Regular Functions

```js
function greet(){
	console.log("Hello");
}
```

#### Arrow Functions

```js
const greet = () => console.log("Hello");
```
