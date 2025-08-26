
---

OOP is a programming paradigm based on the concept of of "objects", which contains data (fields) and behavior (methods).

*Class : A blueprint to create objects consist of fields and methods.*
*Object : Implementation of a class. These are the real entities.*

There are four main pillars of oop.

1. Encapsulation.
2. Abstraction.
3. Polymorphism.
4. Inheritance.

#### **1.Encapsulation**

Wrapping up data and and methods into a single unit and controlling the access to them.
This protects data from direct access.

```java
class BankAccount {
	private double balance; // private -> cant be accessed from outside
	
	// Getter
	public double getBalance(){
		return balance;
	}
	
	// Setter
	public void deposit(double amount) {
		if(amount > 0){
			balance += amount;
		}
	}
}
```

***Balance is hidden from outside (private).***

***Access is given only via getter/setter methods.***

---
#### **2.Abstraction**

Hiding all the implementation details and showing only essential features.
This is achieved by using **abstract classes and interfaces**.

```java
abstract class Vehicle {
	abstract void start(); //abstract method
}

class Car extends Vehicle {

	// implementation of abstract method
	void start(){
		System.out.println("Car start with a key");
	}
}

class Bike extends Vehicle {

	void start(){
		System.out.println("Bike starts with button");
	}
}
```

*This helps in hiding the business logic, we just call the method and it will take care of the implementation.*

---

#### 3. **Inheritance**

When one class (child) acquires properties and behavior of another class (parent) we call it inheritance.

*This helps is reusability of the code.*

```java

class Animal {
	void sound(){
		System.out.println("Animal makes sound");
	}
}

class Dog extends Animal {

	void sound(){
		System.out.println("Dog barks");
	}
}
```

*Dog inherits behavior from animal.*

*We can override the sound to fit into dogs behavior.*


---

#### **4.Polymorphism**

One action, many forms

Two types
	
	Compile-time polymorphism/Method overloading.
	
	Runtime polymorphism/Method overriding.

```java
class Addition {
	
	//Method overloading - same method with different parameters
	public int add(int a, int b){
		return a + b;
	}
	
	public double add(double a, double b){
		return a + b;
	}
}
```

```java
class Animal {
	void sound(){
		System.out.println("Animal makes sound");
	}
}

class Dog extends Animal {
	//Child overrides the parent method, at runtime jvm decides which one to run.
	void sound(){
		System.out.println("Dog barks");
	}
}
```

