
---
## 🔹 What is `CompletableFuture` in Java?

`CompletableFuture` (introduced in **Java 8**) is part of the `java.util.concurrent` package.  
It represents a **Future** that can be **explicitly completed** and **chained with multiple asynchronous operations**.

It helps you write **non-blocking, asynchronous, and concurrent** code easily.

---

## 🔹 Why do we need `CompletableFuture`?

Before `CompletableFuture`, we used:

- `Future` and `Callable`
    
- Problem:
    
    - We **cannot chain** tasks easily
        
    - We **cannot combine** multiple futures
        
    - We **have to block** using `get()` to get results
        

`CompletableFuture` fixes all that:  
✅ It supports **callbacks** when a task is done  
✅ It allows **chaining** and **combining** tasks  
✅ It supports **asynchronous execution** with `ForkJoinPool`

## 🔹 Key Static Methods

| Method                     | Description                                   |
| -------------------------- | --------------------------------------------- |
| `runAsync(Runnable)`       | Run a task asynchronously with no result      |
| `supplyAsync(Supplier<T>)` | Run a task asynchronously and return a result |
| `completedFuture(T value)` | Create a pre-completed future                 |
| `allOf(...)`               | Wait for all futures to complete              |
| `anyOf(...)`               | Wait for any one future to complete           |

## 🔹 Summary Table

| Method            | Purpose                         |
| ----------------- | ------------------------------- |
| `thenApply()`     | Transform the result            |
| `thenAccept()`    | Consume the result (no return)  |
| `thenRun()`       | Run a Runnable after completion |
| `thenCombine()`   | Combine two futures             |
| `thenCompose()`   | Chain dependent futures         |
| `exceptionally()` | Handle exceptions               |
| `handle()`        | Handle result or exception both |
