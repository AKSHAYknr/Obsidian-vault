
---

- `@ConditionalOnProperty` is a **Spring Boot annotation** used to **conditionally create a bean or enable configuration** based on the presence and value of a **property** in `application.properties` or `application.yml`.
    
- Useful for **feature toggles** or **optional beans**.

🧱 Example 1: Enable Bean Based on Property

**application.properties**

```
feature.payment.enabled=true
```

**PaymentService Bean**

```java
@Service 
@ConditionalOnProperty(     
	name = "feature.payment.enabled",     
	havingValue = "true" 
) 
public class PaymentService {     
	public void pay() {         
		System.out.println("Payment processed!");     
	} 
}
```

✅ Behavior:

- `PaymentService` bean is **created only if** `feature.payment.enabled=true`.
    
- If property is `false` or missing → bean is **not created**.

