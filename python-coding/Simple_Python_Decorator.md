# Simple Python Decorator

A **decorator** is used to add extra behavior to an existing function without changing the function itself.

```python
def my_decorator(func):
    def wrapper():
        print("Before execution")
        func()
        print("After execution")

    return wrapper


@my_decorator
def greet():
    print("Hello Mohan")


greet()
```

## Output

```text
Before execution
Hello Mohan
After execution
```

## Simple Explanation

```python
@my_decorator
def greet():
```

is the same as:

```python
greet = my_decorator(greet)
```

So the flow is:

```text
greet()
   ↓
wrapper()
   ↓
Before execution
   ↓
greet()
   ↓
Hello Mohan
   ↓
After execution
```
