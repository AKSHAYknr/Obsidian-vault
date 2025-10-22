
---
Spring Security is built around the idea of **filter-based request interception**. Every HTTP request goes through a **filter chain** that handles authentication, authorization, and security-related concerns.

The main layers:

1. **Client** – sends requests (browser, mobile app, API client).
    
2. **Filter Chain** – a chain of security filters intercepting requests.
    
3. **Authentication Manager** – validates user credentials.
    
4. **UserDetailsService** – fetches user information (username, password, roles).
    
5. **SecurityContextHolder** – holds authentication info for the current session/request.
    
6. **Authorization Layer** – checks roles/permissions.
    
7. **Application Layer** – controllers, services, repositories.

| Component                                   | Role                                                                                                                                               |
| ------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Security Filter Chain**                   | Intercepts every request. Contains filters like `UsernamePasswordAuthenticationFilter`, `BasicAuthenticationFilter`, `ExceptionTranslationFilter`. |
| **AuthenticationManager**                   | Core component that delegates authentication to one or more `AuthenticationProvider`s.                                                             |
| **AuthenticationProvider**                  | Performs actual verification (e.g., checks username/password against DB).                                                                          |
| **UserDetailsService**                      | Loads user-specific data (`UserDetails`) such as username, password, and roles.                                                                    |
| **UserDetails**                             | Encapsulates user info for authentication and authorization.                                                                                       |
| **SecurityContext & SecurityContextHolder** | Stores authentication info for the current session or request. Accessible anywhere in code.                                                        |
| **AccessDecisionManager**                   | Decides whether an authenticated user can access a resource based on roles/permissions.                                                            |
| **PasswordEncoder**                         | Encodes passwords securely (e.g., BCrypt).                                                                                                         |
| **Exception Handling**                      | Handles authentication/authorization failures gracefully.                                                                                          |

```mermaid
flowchart TD
    A[Client] --> B[HTTP Request]
    B --> C[Filter Chain]
    
    C --> D[Security Filters]
    D --> D1[Authentication Filter]
    D --> D2[Authorization Filter]
    D --> D3[Other Filters (CSRF, CORS, etc.)]
    
    D1 --> E[AuthenticationManager]
    E --> F[UserDetailsService]
    F --> G[UserDetails (Load user from DB)]
    G --> H[PasswordEncoder & AuthenticationProvider]
    H --> I{Authenticated?}
    I -- Yes --> J[SecurityContextHolder Stores Authentication]
    I -- No --> K[Authentication Failure -> Return 401]
    
    D2 --> L{Access Allowed?}
    L -- Yes --> M[Proceed to Controller / Resource]
    L -- No --> N[Access Denied -> Return 403]
    
    M --> O[Controller / Service Layer]
    O --> P[Response Sent Back to Client]
```
