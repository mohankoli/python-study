# decorator with arguments Python

```python
def log_call(func):
    def wrapper(*args, **kwargs):
        print(f"Function name: {func.__name__}")

        result = func(*args, **kwargs)

        print(f"Result: {result}")
        return result

    return wrapper


@log_call
def add(a, b):
    return a + b


print(add(10, 20))
```

## Output

```text
Function name: add
Result: 30
30
```

## How it works

This:

```python
@log_call
def add(a, b):
    return a + b
```

is equivalent to:

```python
def add(a, b):
    return a + b

add = log_call(add)
```

The decorator wraps the original `add()` function and adds extra behavior before and after the function call.
