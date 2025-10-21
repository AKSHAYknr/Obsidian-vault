
---
Spring Data JPA can **generate queries automatically** from method names — no need to write JPQL or SQL manually.  
The framework parses the method name and builds the query based on the entity and its fields.

### ✅ **Example**

Suppose you have an entity:

```java
@Entity public class Employee {     
	@Id     
	@GeneratedValue(strategy = GenerationType.IDENTITY)     
	private Long id;      
	private String name;     
	private String department;     
	private Double salary; 
}
```

and a repository:

```java
public interface EmployeeRepository extends JpaRepository<Employee, Long> {          // Derived queries     
	List<Employee> findByDepartment(String department);      
	List<Employee> findBySalaryGreaterThan(Double salary);      
	Optional<Employee> findByName(String name);      
	boolean existsByName(String name);      
	long countByDepartment(String department); 
}
```

### ⚙️ **How It Works**

|Method Name|Derived Query|
|---|---|
|`findByDepartment("HR")`|`SELECT * FROM employee WHERE department = 'HR'`|
|`findBySalaryGreaterThan(50000)`|`SELECT * FROM employee WHERE salary > 50000`|
|`existsByName("John")`|`SELECT CASE WHEN COUNT(*) > 0 THEN TRUE ELSE FALSE END FROM employee WHERE name = 'John'`|
|`countByDepartment("IT")`|`SELECT COUNT(*) FROM employee WHERE department = 'IT'`|

### 🧠 **Advantages**

- No JPQL or SQL needed.
    
- Very readable and concise.
    
- Automatically mapped to entity fields.
    

### ⚠️ **Limitations**

- Complex queries (joins, subqueries, custom conditions) aren’t always expressible.
    
- Method names can become **very long** and hard to maintain for complex filters.


JPQL is **object-oriented SQL** — you write queries **based on entity names and fields**, not table or column names.  
You can write JPQL queries using the `@Query` annotation in your repository.

### ✅ **Example**

```java
public interface EmployeeRepository extends JpaRepository<Employee, Long> {  

	@Query("SELECT e FROM Employee e WHERE e.department = :department")     List<Employee> getEmployeesByDepartment(@Param("department") String department);      
	@Query("SELECT e FROM Employee e WHERE e.salary > :salary")     
	List<Employee> getEmployeesWithSalaryGreaterThan(@Param("salary") Double salary);      
}
```

### 🧠 **JPQL vs SQL**

|Feature|JPQL|SQL|
|---|---|---|
|Operates on|Entities|Tables|
|Fields|Entity properties|Table columns|
|Return type|Entity objects|Rows/columns|
|Example|`SELECT e FROM Employee e WHERE e.department = 'HR'`|`SELECT * FROM employee WHERE department = 'HR'`|

---

### 🧩 **Advantages**

- More **flexible** than derived queries.
    
- Allows joins, group by, aggregate functions, etc.
    
- Still portable (works with all JPA providers).


### 🧱 **Native SQL Queries**

If you really need to use **raw SQL**, you can do this too:

```java
@Query(value = "SELECT * FROM employee WHERE department = :department", nativeQuery = true) List<Employee> findEmployeesByDepartmentNative(@Param("department") String department);
```

