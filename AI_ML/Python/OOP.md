
---

OOP (Object-Oriented Programming) is a way of structuring code around **objects** (data) and **classes** (blueprints for objects).

## 🔹 1. Class and Object

A **class** is a blueprint, and an **object** is an instance of that class.

```python
class Person:
    def __init__(self, name, age):   # constructor
        self.name = name
        self.age = age

    def greet(self):                 # method
        return f"Hello, my name is {self.name}"

# object creation
p1 = Person("Akshay", 25)
print(p1.greet())  # Hello, my name is Akshay
```

## 🔹 2. Four Pillars of OOP in Python

### (a) **Encapsulation**

- Wrapping variables and methods inside a class.
    
- Using **access modifiers**:
    
    - Public (`self.name`)
        
    - Protected (`self._name`) → convention only
        
    - Private (`self.__name`) → name mangling

```python
class BankAccount:
    def __init__(self, balance):
        self.__balance = balance   # private variable

    def deposit(self, amount):
        self.__balance += amount

    def get_balance(self):
        return self.__balance

acc = BankAccount(1000)
acc.deposit(500)
print(acc.get_balance())  # 1500
```

### (b) **Inheritance**

- One class inherits properties and methods from another.

```python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):  # Dog inherits from Animal
    def speak(self):
        print("Bark!")

d = Dog()
d.speak()   # Bark!
```

✔️ Supports:

- **Single Inheritance**
    
- **Multiple Inheritance**
    
- **Multilevel Inheritance**
    
- **Hierarchical Inheritance**

### (c) **Polymorphism**

- Same function/method behaves differently depending on the object.

```python
class Cat:
    def sound(self):
        return "Meow"

class Dog:
    def sound(self):
        return "Bark"

# polymorphism
for animal in (Cat(), Dog()):
    print(animal.sound())
# Meow
# Bark
```

- Method Overriding → Child class redefines parent method
    
- Operator Overloading → Redefining how operators work

```python
class Number:
    def __init__(self, value):
        self.value = value

    def __add__(self, other):   # operator overloading
        return self.value + other.value

n1 = Number(5)
n2 = Number(10)
print(n1 + n2)  # 15
```

