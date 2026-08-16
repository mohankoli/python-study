# SOLID Principles in Python — Interview Friendly

SOLID is a set of **5 object-oriented design principles** that help us write code that is easier to **maintain, test, extend, and reuse**.

## 1. S — Single Responsibility Principle (SRP)

> A class should have **one responsibility** and therefore one reason to change.

### ❌ Bad Example

```python
class Report:
    def generate(self):
        print("Generating report")

    def save_to_file(self):
        print("Saving report to file")

    def send_email(self):
        print("Sending report by email")
```

`Report` is doing three different jobs:
- Generate report
- Save report
- Send email

### ✅ Better Example

```python
class Report:
    def generate(self):
        print("Generating report")


class ReportSaver:
    def save(self, report):
        print("Saving report")


class EmailService:
    def send(self, report):
        print("Sending report by email")
```

**Interview line:** SRP means a class should focus on one responsibility.

---

## 2. O — Open/Closed Principle (OCP)

> Software entities should be **open for extension but closed for modification**.

We should be able to add new behavior without changing existing, tested code.

### ❌ Bad Example

```python
class Payment:
    def pay(self, method):
        if method == "card":
            print("Paying by card")
        elif method == "upi":
            print("Paying by UPI")
```

If we add PayPal, we need to modify the existing class.

### ✅ Better Example

```python
class Payment:
    def pay(self):
        pass


class CardPayment(Payment):
    def pay(self):
        print("Paying by card")


class UPIPayment(Payment):
    def pay(self):
        print("Paying by UPI")


class PayPalPayment(Payment):
    def pay(self):
        print("Paying by PayPal")
```

Now we can add a new payment type without changing existing classes.

**Interview line:** OCP means extend behavior without modifying existing code.

---

## 3. L — Liskov Substitution Principle (LSP)

> A child class should be usable wherever its parent class is expected **without breaking the program**.

### ❌ Bad Example

```python
class Bird:
    def fly(self):
        print("Flying")


class Penguin(Bird):
    def fly(self):
        raise Exception("Penguins cannot fly")
```

`Penguin` cannot properly behave like a `Bird` that supports `fly()`. This violates LSP.

### ✅ Better Example

```python
class Bird:
    pass


class FlyingBird(Bird):
    def fly(self):
        print("Flying")


class Sparrow(FlyingBird):
    pass


class Penguin(Bird):
    def swim(self):
        print("Swimming")
```

Now `Penguin` does not inherit behavior that it cannot support.

**Interview line:** LSP means subclasses should honor the behavior expected from their parent type.

---

## 4. I — Interface Segregation Principle (ISP)

> A class should not be forced to depend on methods it does not use.

Python does not have a `interface` keyword like Java, but we can use **abstract base classes** to design small interfaces.

### ❌ Bad Example

```python
class Worker:
    def work(self):
        pass

    def eat(self):
        pass


class Robot(Worker):
    def work(self):
        print("Robot working")

    def eat(self):
        raise NotImplementedError
```

A robot does not need `eat()`.

### ✅ Better Example

```python
from abc import ABC, abstractmethod


class Workable(ABC):
    @abstractmethod
    def work(self):
        pass


class Eatable(ABC):
    @abstractmethod
    def eat(self):
        pass


class Robot(Workable):
    def work(self):
        print("Robot working")


class Human(Workable, Eatable):
    def work(self):
        print("Human working")

    def eat(self):
        print("Human eating")
```

**Interview line:** ISP means prefer small, focused interfaces instead of one large interface.

---

## 5. D — Dependency Inversion Principle (DIP)

> High-level modules should not depend directly on low-level modules. Both should depend on an **abstraction**.

### ❌ Bad Example

```python
class EmailService:
    def send(self, message):
        print("Sending email:", message)


class Notification:
    def __init__(self):
        self.email = EmailService()

    def send(self, message):
        self.email.send(message)
```

`Notification` is tightly coupled to `EmailService`.

### ✅ Better Example

```python
class Notification:
    def __init__(self, service):
        self.service = service

    def send(self, message):
        self.service.send(message)


class EmailService:
    def send(self, message):
        print("Email:", message)


class SMSService:
    def send(self, message):
        print("SMS:", message)


notification = Notification(EmailService())
notification.send("Hello")

notification = Notification(SMSService())
notification.send("Hello")
```

`Notification` does not care whether the message is sent by email or SMS.

**Interview line:** DIP reduces tight coupling by depending on abstractions rather than concrete implementations.

---

# SOLID — Quick Interview Revision

| Principle | Meaning | Keyword |
|---|---|---|
| **S — Single Responsibility** | One class → one responsibility | Focus |
| **O — Open/Closed** | Extend without modifying existing code | Extension |
| **L — Liskov Substitution** | Child should safely replace parent | Substitution |
| **I — Interface Segregation** | Don't force unused methods | Small interfaces |
| **D — Dependency Inversion** | Depend on abstraction, not concrete class | Loose coupling |

## Easy Way to Remember

**S** → Single responsibility  
**O** → Open for extension, closed for modification  
**L** → Child can replace parent  
**I** → Small/focused interfaces  
**D** → Depend on abstractions

## Interview Answer

**Q: What are SOLID principles?**

**Answer:**

> SOLID is a set of five object-oriented design principles used to create maintainable, flexible, testable, and loosely coupled software. They are Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, and Dependency Inversion.
