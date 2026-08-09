# Python `*args` and `**kwargs`

## 1. Function using `*args` and `**kwargs`

``` python
def calculate(*args, **kwargs):
    total = sum(args)
    op = kwargs.get("opration", "Add")

    if op == "Add":
        return total
    elif op == "multiply":
        result = 1
        for num in args:
            result *= num
        return result
    else:
        return "Invalid opration"


print(calculate(1, 2, 3, 4))
print(calculate(1, 2, 3, 4, opration="multiply"))
```

### Output

``` text
10
24
```

### Explanation

-   `*args` accepts multiple positional arguments and stores them as a
    **tuple**.
-   `**kwargs` accepts multiple keyword arguments and stores them as a
    **dictionary**.
-   `kwargs.get("opration", "Add")` gets the operation. If no operation
    is provided, `"Add"` is used by default.
-   For `"Add"`, `sum(args)` calculates the total.
-   For `"multiply"`, the function multiplies all numbers.

> Note: `opration` is a spelling mistake. A better name is `operation`.

### Improved version

``` python
def calculate(*args, **kwargs):
    operation = kwargs.get("operation", "Add")

    if operation == "Add":
        return sum(args)

    elif operation == "multiply":
        result = 1
        for num in args:
            result *= num
        return result

    else:
        return "Invalid operation"


print(calculate(1, 2, 3, 4))
print(calculate(1, 2, 3, 4, operation="multiply"))
```

------------------------------------------------------------------------

## 2. Understanding `*args` and `**kwargs`

``` python
def demo(*args, **kwargs):
    print("Args", args)
    print("kwargs", kwargs)


demo(10, 20, 30, name="Mohan", age=35)
```

### Output

``` text
Args (10, 20, 30)
kwargs {'name': 'Mohan', 'age': 35}
```

### Key Point

``` text
*args    → multiple positional arguments → tuple
**kwargs → multiple keyword arguments   → dictionary
```

For this call:

``` python
demo(10, 20, 30, name="Mohan", age=35)
```

Python separates the arguments like this:

``` python
args = (10, 20, 30)

kwargs = {
    "name": "Mohan",
    "age": 35
}
```

## Interview Answer

**What is the difference between `*args` and `**kwargs`?**

> `*args` allows a function to accept any number of positional
> arguments, and Python stores them as a tuple. `**kwargs` allows a
> function to accept any number of keyword arguments, and Python stores
> them as a dictionary.
