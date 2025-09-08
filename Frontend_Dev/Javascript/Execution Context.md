
---

Execution context :

In JavaScript, an execution context is an abstract concept representing the environment in which JavaScript code is evaluated and executed. It defines the current scope, variables, functions, and the value of the `this` keyword available to the running code.

Each execution context has two main components: 

- **Memory Component (Variable Environment):**
    
    - This component stores variables and functions as key-value pairs.
    
    - During the creation phase of an execution context, memory is allocated for variables and functions. Variables are initially assigned `undefined` (a process known as hoisting), while functions are stored in their entirety.
    

- **Code Component (Thread of Execution):**
    
    - This component is responsible for executing the JavaScript code line by line within that specific context.
    
    - It performs the actual operations and assigns values to variables during the execution phase.


| Memory(Variable environment)               | Code(Thread of execution) |
| ------------------------------------------ | ------------------------- |
| key : value<br>a : 10<br>function : {....} |                           |

## 🟢 What is the Call Stack?

- The **Call Stack** is a data structure that the JavaScript engine uses to **keep track of function execution**.
    
- It works on the principle of **LIFO (Last In, First Out)** → the last function added is the first one to be removed.

## 🟢 How It Works

1. When a function is **called**, a new **Execution Context** is created and pushed onto the Call Stack.
    
2. When the function **finishes**, its Execution Context is popped off.
    
3. The engine always runs the function that’s **on top of the stack**.

