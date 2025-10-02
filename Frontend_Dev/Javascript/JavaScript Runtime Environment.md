
---
## 🔹 Components of JavaScript Runtime Environment

1. **JavaScript Engine**
    
    - Executes the JavaScript code.
        
    - Examples:
        
        - V8 (Chrome, Node.js)
            
        - SpiderMonkey (Firefox)
            
        - JavaScriptCore (Safari)
            
    - Converts JS into machine code so the computer can understand it.
        
2. **Call Stack**
    
    - A stack data structure that keeps track of function calls.
        
    - Executes functions in a **Last In, First Out (LIFO)** order.
        
3. **Heap**
    
    - Memory allocation space for objects and variables.
        
4. **Web APIs (in Browser runtime only)**
    
    - Provided by the browser, not part of JS itself.
        
    - Examples: `setTimeout`, `DOM API`, `fetch`, `console`.
        
5. **Event Loop**
    
    - Continuously checks the **Call Stack** and **Callback Queue (Task Queue / Microtask Queue)**.
        
    - If the call stack is empty, it pushes queued tasks into it for execution.
        
6. **Callback Queue / Task Queue**
    
    - Stores asynchronous tasks like `setTimeout` or event handlers until they are ready to be executed.
        
7. **Microtask Queue**
    
    - Stores promises (`.then`, `catch`, `finally`) and executes them before the callback queue.
        

---

## 🔹 JavaScript Runtime Environments

1. **Browser Runtime Environment**
    
    - Runs JavaScript in browsers (Chrome, Firefox, Safari, etc.).
        
    - Has access to **Web APIs** like DOM, fetch, localStorage, setTimeout, etc.
        
2. **Node.js Runtime Environment**
    
    - Runs JavaScript outside the browser (on servers, command-line tools).
        
    - Uses **V8 engine** but instead of Web APIs, it provides Node APIs like `fs`, `http`, `events`.