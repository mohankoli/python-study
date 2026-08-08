# Custom Iterator in Python

A custom iterator uses `__iter__()` and `__next__()` to control how values are generated.

```python
class Counter:
    def __init__(self, max):
        self.current = 1
        self.max = max

    def __iter__(self):
        return self

    def __next__(self):
        if self.current <= self.max:
            value = self.current
            self.current += 1
            return value

        raise StopIteration


count = Counter(10)

for num in count:
    print(num)
```

## Output

```text
1
2
3
4
5
6
7
8
9
10
```

## Key Points

### `__iter__()`

```python
def __iter__(self):
    return self
```

Returns the iterator object.

### `__next__()`

```python
def __next__(self):
```

Returns the next value.

### `StopIteration`

```python
raise StopIteration
```

Tells Python that there are no more values.

## Interview Memory Trick

```text
__iter__() → Give me the iterator
__next__() → Give me the next value
StopIteration → Iteration is finished
```
