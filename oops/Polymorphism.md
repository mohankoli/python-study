# Polymorphism (Many Forms)

## Definition

**Polymorphism** means **one method or interface can have different behaviors depending on the object**.

In this example, both `Car` and `Bike` have the same `start()` method, but each class provides its own behavior.

## Example

```python
class Vehicle:
    def start(self):
        print("vehicle is started")


class Car(Vehicle):
    def start(self):
        print("car is started by key")


class Bike(Vehicle):
    def start(self):
        print("bike is started by self button")


myCar = Car()
myBike = Bike()

myCar.start()
myBike.start()
```

## Output

```text
car is started by key
bike is started by self button
```

## Key Point

The method name is the same:

```python
start()
```

But the behavior is different:

```text
Car  → start() → car is started by key
Bike → start() → bike is started by self button
```

This is **Polymorphism through Method Overriding**.
