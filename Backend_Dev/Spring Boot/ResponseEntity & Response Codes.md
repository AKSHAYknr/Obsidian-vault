
---

`ResponseEntity` represents the **whole HTTP response** —  
✅ **Status Code**  
✅ **Headers**  
✅ **Body**

It gives you **full control** over what your API returns.

```java
@PostMapping("/users")
public ResponseEntity<User> createUser(@RequestBody User user) {
    User savedUser = userService.save(user);
    return ResponseEntity
            .status(HttpStatus.CREATED)
            .header("Location", "/users/" + savedUser.getId())
            .body(savedUser);
}
```

## 🌐 **Common HTTP Response Codes**

|Code|Name|Meaning|Typical Use|
|---|---|---|---|
|**200**|OK|Request succeeded|GET, PUT, POST (with response)|
|**201**|Created|Resource created|POST|
|**204**|No Content|Success but no body|DELETE, PUT|
|**400**|Bad Request|Invalid input|Validation errors|
|**401**|Unauthorized|Missing/invalid auth|JWT, OAuth|
|**403**|Forbidden|Access denied|Authenticated but not allowed|
|**404**|Not Found|Resource doesn’t exist|Wrong ID or URL|
|**409**|Conflict|Resource already exists|Duplicate entries|
|**500**|Internal Server Error|Server crash/unexpected error|Exceptions|
