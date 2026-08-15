# OOP in Python — Class and Objects

## Problem

Create a `Car` class with:

- `brand` and `color` attributes
- `start()` method
- `stop()` method
- Create two car objects and call their methods

## Solution

```python
class Car:
    def __init__(self, brand, color):
        self.brand = brand
        self.color = color

    def start(self):
        print(f"{self.brand} is started")

    def stop(self):
        print(f"{self.brand} is stopped")


car1 = Car("Tata", "Red")
car2 = Car("Mahindra", "Black")

car1.start()
car2.stop()
```

## Output

```text
Tata is started
Mahindra is stopped
```

## Key Concepts

- **Class:** `Car` is the class.
- **Object:** `car1` and `car2` are objects of the `Car` class.
- **Constructor:** `__init__()` initializes `brand` and `color`.
- **`self`:** Refers to the current object.
- **Instance attributes:** `self.brand` and `self.color`.
- **Methods:** `start()` and `stop()` define the behavior of a car.
