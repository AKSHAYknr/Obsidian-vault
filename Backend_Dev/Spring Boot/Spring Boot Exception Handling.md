
---
Exception handling in Spring Boot allows developers to manage errors gracefully and send meaningful responses to clients (especially in REST APIs).  
It ensures:

- Consistent error responses
    
- Clear debugging messages
    
- Cleaner controller code

## ⚙️ 1. Default Exception Handling

By default, Spring Boot uses `@ResponseStatus` and internal exception resolvers (like `ResponseStatusExceptionResolver`) to handle common errors such as:

- `MethodArgumentNotValidException`
    
- `HttpRequestMethodNotSupportedException`
    
- `HttpMessageNotReadableException`

You can use `@ResponseStatus` on custom exceptions to control the HTTP status:

```java
@ResponseStatus(HttpStatus.NOT_FOUND)
public class ResourceNotFoundException extends RuntimeException {
    public ResourceNotFoundException(String message) {
        super(message);
    }
}
```

If this exception is thrown, the response will be:

```json
{
  "timestamp": "2025-10-18T12:00:00",
  "status": 404,
  "error": "Not Found",
  "message": "Resource not found",
  "path": "/api/resource/5"
}
```

### 🧩 2. Using `@ExceptionHandler` in Controller

You can handle exceptions within a specific controller using the `@ExceptionHandler` annotation.

```java
@RestController
@RequestMapping("/api/users")
public class UserController {

    @GetMapping("/{id}")
    public ResponseEntity<User> getUser(@PathVariable Long id) {
        if (id == 0) {
            throw new ResourceNotFoundException("User not found with id " + id);
        }
        return ResponseEntity.ok(new User(id, "Akshay"));
    }

    @ExceptionHandler(ResourceNotFoundException.class)
    public ResponseEntity<String> handleNotFound(ResourceNotFoundException ex) {
        return ResponseEntity.status(HttpStatus.NOT_FOUND).body(ex.getMessage());
    }
}
```

✅ **Good for:**  
Handling exceptions relevant only to this specific controller.

### 🌍 3. Global Exception Handling with `@ControllerAdvice`

To manage all exceptions centrally, create a **Global Exception Handler** using `@ControllerAdvice`.

```java
@ControllerAdvice
public class GlobalExceptionHandler {

    @ExceptionHandler(ResourceNotFoundException.class)
    public ResponseEntity<ErrorResponse> handleResourceNotFound(ResourceNotFoundException ex) {
        ErrorResponse error = new ErrorResponse(
                HttpStatus.NOT_FOUND.value(),
                ex.getMessage(),
                System.currentTimeMillis()
        );
        return new ResponseEntity<>(error, HttpStatus.NOT_FOUND);
    }

    @ExceptionHandler(Exception.class)
    public ResponseEntity<ErrorResponse> handleGenericException(Exception ex) {
        ErrorResponse error = new ErrorResponse(
                HttpStatus.INTERNAL_SERVER_ERROR.value(),
                "Something went wrong",
                System.currentTimeMillis()
        );
        return new ResponseEntity<>(error, HttpStatus.INTERNAL_SERVER_ERROR);
    }
}
```

🧱 ErrorResponse DTO

```java
public class ErrorResponse {
    private int status;
    private String message;
    private long timestamp;

    public ErrorResponse(int status, String message, long timestamp) {
        this.status = status;
        this.message = message;
        this.timestamp = timestamp;
    }

    // getters and setters
}
```

 ### 🧱 4. Customizing Error Response with`ResponseEntityExceptionHandler`

Extend Spring’s `ResponseEntityExceptionHandler` for advanced control.

```java
@ControllerAdvice
public class CustomGlobalExceptionHandler extends ResponseEntityExceptionHandler {

    @Override
    protected ResponseEntity<Object> handleMethodArgumentNotValid(
            MethodArgumentNotValidException ex,
            HttpHeaders headers,
            HttpStatusCode status,
            WebRequest request) {

        Map<String, String> errors = new HashMap<>();
        ex.getBindingResult().getFieldErrors().forEach(err ->
            errors.put(err.getField(), err.getDefaultMessage())
        );

        return new ResponseEntity<>(errors, HttpStatus.BAD_REQUEST);
    }
}
```

