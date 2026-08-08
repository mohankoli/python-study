# Memoization Decorator in Python

Memoization means **caching the result of a function** so that if the same input comes again, Python can return the cached result instead of calculating it again.

```python
def memoize(func):
    cache = {}

    def wrapper(n):
        if n in cache:
            print("Returning from cache")
            return cache[n]

        print("Calculating...")
        result = func(n)
        cache[n] = result

        return result

    return wrapper


@memoize
def square(n):
    return n * n


print(square(5))
print(square(5))
print(square(10))
print(square(10))
```

## Output

```text
Calculating...
25

Returning from cache
25

Calculating...
100

Returning from cache
100
```

## How it works

First call:

```python
square(5)
```

There is no `5` in the cache:

```text
cache = {}
     ↓
calculate 5 × 5
     ↓
cache = {5: 25}
```

Second call:

```python
square(5)
```

`5` is already in the cache:

```text
cache = {5: 25}
     ↓
return 25
```

### Key idea

```python
if n in cache:
    return cache[n]
```

**Memoization = Calculate once → Store result → Reuse result**
