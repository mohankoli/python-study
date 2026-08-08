# Generator using `yield` — Python

### Question

**Implement a generator that returns numbers from 1 to 5.**

```python
def numbers():
    for i in range(1, 6):
        yield i


for num in numbers():
    print(num)
```

### Output

```text
1
2
3
4
5
```

### How `yield` works

Unlike `return`, `yield` **pauses the function** and remembers its current state.

```text
numbers()
   ↓
yield 1 → pause
   ↓
yield 2 → pause
   ↓
yield 3 → pause
   ↓
yield 4 → pause
   ↓
yield 5 → pause
```

### `return` vs `yield`

```python
# return
def get_numbers():
    return [1, 2, 3, 4, 5]
```

Creates the complete list in memory.

```python
# yield
def get_numbers():
    for i in range(1, 6):
        yield i
```

Produces **one value at a time**.

### Interview Explanation

> "`yield` turns a Python function into a generator. It produces values lazily, one at a time, and preserves the function's state between calls."

### Why use generators?

* Memory efficient
* Lazy evaluation
* Useful for large files
* Useful for streams/data pipelines
* Avoids creating the entire collection in memory

**Memory trick:**

> `return` → give result and finish
> `yield` → give value and pause
