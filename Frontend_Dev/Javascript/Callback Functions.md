
---
## 🔹 What is a Callback Function?

A **callback function** is a function that is **passed as an argument** to another function and is **executed later** after some operation is completed.

👉 In simple words:  
You "call back" a function once another function is done with its task.

## 🔹 Example 1: Simple Callback

```js
function greet(name, callback) {    
	console.log("Hello, " + name);     
	callback(); 
}  
function sayGoodbye() {     
	console.log("Goodbye!"); 
}  
// Passing sayGoodbye as a callback 
greet("Akshay", sayGoodbye);
```

**Output:**

```
Hello, Akshay
Goodbye!
```

Here:

- `sayGoodbye` is passed into `greet` as a callback.
    
- After printing `Hello, Akshay`, it "calls back" `sayGoodbye`.

```js
function fetchData(callback) {
    console.log("Fetching data...");
    setTimeout(() => {
        const data = { id: 1, name: "JavaScript" };
        callback(data); // callback is executed after data is "fetched"
    }, 2000);
}

fetchData(function(result) {
    console.log("Data received:", result);
});
```

## 🔹 Why Use Callbacks?

- To **control the order of execution** in async operations.
    
- To **avoid blocking** code while waiting for results (like fetching data).
    
- Foundation of async patterns like **Promises** and **async/await**.
    

---

⚡ But:  
Too many nested callbacks lead to **"Callback Hell"**, which is why **Promises** and **async/await** were introduced.

## 🔹 What is an Event Listener?

An **event listener** is a function that **waits (listens) for an event** to happen on an element (like a button click, key press, mouse hover, etc.), and then **executes a callback function** when the event occurs.

👉 In short:

- Event = Something happens (click, hover, keydown, etc.)
    
- Listener = Waits for the event
    
- Callback = Function that runs when the event happens
    

---

## 🔹 Syntax

```js
element.addEventListener(event, callback);
```

- `element` → The DOM element you want to listen on.
    
- `event` → The event type (`"click"`, `"mouseover"`, `"keydown"`, etc.).
    
- `callback` → Function to run when the event occurs.

✅ In summary:

- `addEventListener` lets you attach multiple callbacks to the same event.
    
- It’s **preferred** over inline `onclick="..."` because it’s cleaner and supports multiple listeners.