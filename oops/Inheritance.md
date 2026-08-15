# Inheritance in Python

## Definition

**Inheritance** allows a child class to reuse the properties and methods of a parent class.

It allows **code reuse** and represents an **"is-a" relationship**.

## Example

```python
class Vehicle:
    def start(self):
        print("vehicle is started")


class Car(Vehicle):
    def driving(self):
        print("Car is driving")


myCar = Car()

myCar.start()
myCar.driving()
```

## Output

```text
vehicle is started
Car is driving
```

## Key Points

- `Vehicle` → **Parent class**
- `Car` → **Child class**
- `Car(Vehicle)` → `Car` inherits from `Vehicle`
- `start()` → **Inherited method**
- `driving()` → **Child class method**
- `myCar` → **Object of `Car`**
