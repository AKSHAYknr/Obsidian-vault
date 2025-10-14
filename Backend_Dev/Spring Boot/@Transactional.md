
---
`@Transactional` is used to **manage database transactions** in Spring.  
It ensures that a series of database operations **either all succeed or all fail**, maintaining **data consistency**.

#### ⚙️ How it works

When a method is annotated with `@Transactional`, Spring:

1. Starts a **transaction** before the method executes.
    
2. Commits the transaction if the method completes successfully.
    
3. Rolls back the transaction if a **runtime exception** (unchecked) occurs.

#### 🧩 Common Use Cases

- Wrapping multiple repository operations that must act as one unit.
    
- Ensuring rollback on failure during CRUD or business logic methods.
    
- Used in **service layer**, not in controllers or repositories directly.

**ACID** stands for the four key properties of a reliable transaction:

🧱 1. Atomicity

- All operations in a transaction are treated as one unit.
    
- If any operation fails → the whole transaction rolls back.  
    🟢 _All or nothing._


⚖️ 2. Consistency

- Transaction must take the database from one valid state to another.
    
- All rules, constraints, and relationships must remain valid.  
    🟢 _Data always stays correct._


🔒 3. Isolation

- Each transaction runs independently of others.
    
- Prevents dirty reads, non-repeatable reads, and phantom reads.  
    🟢 _No interference between transactions._


💽 4. Durability

- Once committed, the data change is permanent.
    
- Even system crashes won’t undo it.  
    🟢 _Committed = Saved forever._


---


⚙️ Transaction Manager — Spring Boot

A **Transaction Manager** in Spring controls how transactions start, commit, and roll back.  
It’s the core component behind the `@Transactional` annotation.

🧩 Role of Transaction Manager

- Begins a transaction before a method runs.
    
- Commits if the method completes successfully.
    
- Rolls back if an exception occurs.
    
- Works with the **database connection** to ensure ACID properties.

🏗️ Common Implementations

|Database Type|Transaction Manager|
|---|---|
|JDBC|`DataSourceTransactionManager`|
|JPA / Hibernate|`JpaTransactionManager`|
|JTA (Distributed)|`JtaTransactionManager`|

Spring automatically picks the right one based on dependencies.

 🧱 Example

```java
@Configuration 
@EnableTransactionManagement 
public class AppConfig {      
	@Bean     
	public PlatformTransactionManager transactionManager(EntityManagerFactory emf){         
		return new JpaTransactionManager(emf);     
	} 
}
```

Or simply use `@Transactional` — Spring Boot will auto-configure it for you.

💡 Key Points

- Only **one transaction manager** should manage a datasource.
    
- Can define multiple if using **multiple datasources**.
    
- Works at the **service layer** — not at controller or repository directly.


---


🧾 TransactionTemplate — Spring Boot

🧠 What it is

`TransactionTemplate` is a **programmatic way** to manage transactions in Spring.  
It’s an alternative to using the `@Transactional` annotation.

⚙️ When to Use

- When you need **fine-grained control** over transactions.
    
- When you want to **handle commit/rollback manually**.
    
- Useful in **non-Spring-managed classes** or **custom transaction logic**.

```java
@Service
public class PaymentService {

    @Autowired
    private TransactionTemplate transactionTemplate;

    @Autowired
    private PaymentRepository paymentRepo;

    public void processPayment(Payment payment) {
        transactionTemplate.execute(status -> {
            try {
                paymentRepo.save(payment);
                // custom logic
            } catch (Exception e) {
                status.setRollbackOnly(); // rollback manually
            }
            return null;
        });
    }
}
```

```java
@Bean
public TransactionTemplate transactionTemplate(PlatformTransactionManager manager) {
    return new TransactionTemplate(manager);
}
```

💡 Key Points

- Gives **manual control** of commit/rollback.
    
- Works internally with **TransactionManager**.
    
- Ideal for **custom or nested transaction scenarios**.
    
- `@Transactional` → declarative  
    `TransactionTemplate` → programmatic


---

🔒 Isolation Levels in Transaction

🧠 What it is

**Isolation level** defines how much one transaction is **isolated from others** —  
i.e., how visible its changes are before it’s committed.

It helps prevent problems like **dirty reads**, **non-repeatable reads**, and **phantom reads**.

⚙️ Common Isolation Levels

|Level|Description|Prevents|
|---|---|---|
|**READ_UNCOMMITTED**|Transactions can read uncommitted data from others.|❌ None (least safe)|
|**READ_COMMITTED**|Can only read committed data.|✅ Dirty reads|
|**REPEATABLE_READ**|Ensures data read once won’t change during the transaction.|✅ Dirty + Non-repeatable reads|
|**SERIALIZABLE**|Highest isolation; transactions execute one by one logically.|✅ Dirty + Non-repeatable + Phantom reads|