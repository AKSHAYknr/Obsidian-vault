
---

### **What is a Closure?**

A **closure** is a combination of a **function** and the **lexical environment** within which that function was declared. In simpler terms:

> A closure gives a function **access to variables from an outer scope** even after that outer function has finished executing.

### **Key Points**

1. **Lexical scope matters**: Functions in JS remember the scope in which they were created.
    
2. **Closures allow data privacy**: Variables in the outer function can’t be accessed directly from outside, but can be accessed via inner functions.
    
3. **Closures are everywhere in JS**: Callbacks, event listeners, setTimeout, and even modules use closures.

### **Example 1: Basic Closure**

```js
function outer() {     
let count = 0; // variable in outer scope     
	function inner() {         
		count++;         
		console.log(count);     
	}     
	return inner; // returning inner function 
}  
const counter = outer(); // outer() executes, returns inner() 
counter(); // 1 
counter(); // 2 
counter(); // 3
```

**Explanation:**

- `outer()` returns `inner`.
    
- `inner` remembers the `count` variable from `outer()`’s scope, even though `outer()` has already finished executing.
    
- That memory of `count` is the **closure**.

### **Why Use Closures?**

1. **Encapsulation / data hiding**  
    Protects variables from being modified directly.
    
2. **Function factories**  
    Can generate functions dynamically with specific behavior.
    
3. **Maintaining state**  
    Useful in callbacks, timers, and event handlers to remember information.
    

💡 **Summary:**  
A **closure** is created whenever a function accesses a variable outside its immediate scope.  
It allows **persistent memory**, **data privacy**, and **dynamic behavior** in JavaScript.