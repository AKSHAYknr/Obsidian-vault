
---
Mapping a **DTO (Data Transfer Object)** to a **database entity/table** in **Spring Boot** is a common practice when you want to separate API request/response models from your persistence models (JPA entities).

## 🧩 Step 1: Define Your Entity (Database Table)

This represents your **table** in the database.


```java
@Entity 
@Table(name = "users") 
public class User {     
	@Id     
	@GeneratedValue(strategy = GenerationType.IDENTITY)     
	private Long id;      
	private String name;     
	private String email;     
	private int age;      
	// Getters and Setters 
}
```

## 📦 Step 2: Define Your DTO (Data Transfer Object)

This is what you’ll use to send/receive data in your API — it’s **not** tied to your database schema.

```java
public class UserDTO {     
	private String name;     
	private String email;     
	private int age;      
	// Getters and Setters 
}
```

## 🔁 Step 3: Map DTO ↔ Entity

There are **three common approaches**:

### ✅ Option 1: Manual Mapping (Simple and clear)

Best for small projects.

```java
public class UserMapper {     
	public static User toEntity(UserDTO dto) {         
		User user = new User();         
		user.setName(dto.getName());         
		user.setEmail(dto.getEmail());         
		user.setAge(dto.getAge());         
		return user;     
	}      
	public static UserDTO toDTO(User user) {         
		UserDTO dto = new UserDTO();         
		dto.setName(user.getName());         
		dto.setEmail(user.getEmail());         
		dto.setAge(user.getAge());         
		return dto;     
	} 
}
```

Usage in Service:

```java
@Service public class UserService {     
@Autowired     
private UserRepository userRepository;      
	public UserDTO createUser(UserDTO userDTO) {         
		User user = UserMapper.toEntity(userDTO);         
		User savedUser = userRepository.save(user);         
		return UserMapper.toDTO(savedUser);     
	} 
}
```

### ⚙️ Option 2: Using **ModelMapper** Library

Add dependency:

```xml
<dependency>     
	<groupId>org.modelmapper</groupId>     
	<artifactId>modelmapper</artifactId>     
	<version>3.2.0</version> 
</dependency>
```

Create a configuration bean:

```java
@Configuration public class ModelMapperConfig {     
	@Bean     
	public ModelMapper modelMapper() {         
		return new ModelMapper();     
	} 
}
```

Use it in your service:

```java
@Service public class UserService {     
	@Autowired     
	private UserRepository userRepository;      
	
	@Autowired     
	private ModelMapper modelMapper;      
	
	public UserDTO createUser(UserDTO userDTO) {         
		User user = modelMapper.map(userDTO, User.class);         
		User savedUser = userRepository.save(user);         
		return modelMapper.map(savedUser, UserDTO.class);     
	} 
}
```

### ⚡ Option 3: Using **MapStruct** (Best for large projects — compile-time mapping)

Add dependency:

```xml
<dependency>     
	<groupId>org.mapstruct</groupId>     
	<artifactId>mapstruct</artifactId>     
	<version>1.5.5.Final</version> 
</dependency>  

<dependency>     
	<groupId>org.mapstruct</groupId>     
	<artifactId>mapstruct-processor</artifactId>     <version>1.5.5.Final</version>     
	<scope>provided</scope> 
</dependency>
```

Define mapper interface:

```java
@Mapper(componentModel = "spring") 
public interface UserMapper {     
	User toEntity(UserDTO dto);     
	UserDTO toDTO(User entity); 
}
```

Use it in your service:

```java
@Service public class UserService {     
	@Autowired     
	private UserRepository userRepository;      
	
	@Autowired     
	private UserMapper userMapper;    
	  
	public UserDTO createUser(UserDTO userDTO) {         
		User user = userMapper.toEntity(userDTO);         
		User savedUser = userRepository.save(user);         
		return userMapper.toDTO(savedUser);     
	} 
}
```

## 🧠 Summary

|Approach|Library|Pros|Cons|
|---|---|---|---|
|Manual|None|Simple, clear|Tedious for large apps|
|ModelMapper|Runtime-based|Quick to set up|Slower (reflection)|
|MapStruct|Compile-time|Fast, type-safe|Slight setup overhead|