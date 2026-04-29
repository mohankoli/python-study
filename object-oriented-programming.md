# Object-Oriented Programming (OOP) in Python

## Simple Definition (Interview-Friendly)

Object-Oriented Programming (OOPS) is a programming paradigm that uses objects to represent real-world entities. In Python, OOPS is implemented through classes and objects. Classes are blueprints for creating objects, and objects are instances of a class.

------------------------------------------------------------------------

## Core Concepts of OOP

### 1. Class (Blueprint)

A class is a template or blueprint for create objects.

``` python
class Car:
    def start(self):
        print("Car started")
```

------------------------------------------------------------------------

### 2. Object (Instance)

An object is an instance of a class.

``` python
c = Car()
c.start()
```

------------------------------------------------------------------------

### 3. Encapsulation (Data Hiding)

Wrapping data and methods together and restricting access.

``` python
class Bank:
    def __init__(self):
        self.__balance = 1000

    def get_balance(self):
        return self.__balance

b = Bank()
print(b.get_balance())
```

------------------------------------------------------------------------

### 4. Inheritance (Code Reuse)

Child class inherits properties of parent class.

``` python
class Animal:
    def speak(self):
        print("Animal speaks")

class Dog(Animal):
    pass

d = Dog()
d.speak()
```

------------------------------------------------------------------------

### 5. Polymorphism (Many Forms)

Same method behaves differently.

``` python
class Dog:
    def sound(self):
        print("Bark")

class Cat:
    def sound(self):
        print("Meow")

for obj in (Dog(), Cat()):
    obj.sound()
```

------------------------------------------------------------------------

### 6. Abstraction (Hide Complexity)

``` python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass
```

------------------------------------------------------------------------

# Method Overloading vs Method Overriding

## Method Overloading

Same method name with different parameters (simulated in Python).

``` python
class Math:
    def add(self, a, b, c=0):
        return a + b + c

m = Math()
print(m.add(2, 3))
print(m.add(2, 3, 4))
```

## Method Overriding

Child class redefines method of parent class.

``` python
class Animal:
    def sound(self):
        print("Animal sound")

class Dog(Animal):
    def sound(self):
        print("Bark")

d = Dog()
d.sound()
```

------------------------------------------------------------------------

## Key Differences

  ------------------------------------------------------------------------
  Feature            Overloading                 Overriding
  ------------------ --------------------------- -------------------------
  Definition         Same method, different      Same method in parent &
                     params                      child

  Support            Not direct in Python        Fully supported

  Inheritance        Not required                Required
  ------------------------------------------------------------------------

------------------------------------------------------------------------

## One-Line Summary

-   Overloading → Same method, different inputs\
-   Overriding → Same method, different behavior
