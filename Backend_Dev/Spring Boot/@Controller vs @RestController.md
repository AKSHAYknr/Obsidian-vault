
---
Both `@Controller` and `@RestController` are used to define **controller classes** in Spring MVC / Spring Boot.  
They handle **incoming web requests**, but differ in **how they return responses**.

🧱 1️⃣ `@Controller`

🔹 Purpose

Used to mark a **web controller** class that returns **views (HTML/JSP pages)** — typically in MVC web apps.

🔹 Behavior

- Returns **View (template)** name, not the data itself.
    
- You must explicitly add `@ResponseBody` to return JSON or text.

⚙️ 2️⃣ `@RestController`

🔹 Purpose

Used for **RESTful APIs** — directly returns **JSON or XML** response, not views.

🔹 Behavior

- Combines `@Controller` + `@ResponseBody`.
    
- All methods return data directly (serialized to JSON/XML).
    
- Commonly used for **backend APIs** or **microservices**.

🪄 Tip

✅ Use `@Controller` → For web apps using Thymeleaf, JSP, etc.  
✅ Use `@RestController` → For APIs and microservices that return JSON.