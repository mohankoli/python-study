# Abstraction in Python

**Abstraction** means **hiding the internal implementation details and exposing only the essential functionality to the user.**

## Example

```python
from abc import ABC, abstractmethod


class Vehicle(ABC):

    @abstractmethod
    def start(self):
        pass


class Car(Vehicle):

    def start(self):
        print("Car starts with a key")


class Bike(Vehicle):

    def start(self):
        print("Bike starts with a self button")


car = Car()
bike = Bike()

car.start()
bike.start()
