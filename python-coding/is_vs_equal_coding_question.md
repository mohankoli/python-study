# `is` vs `==` — Coding Question

## Question

What is the difference between `is` and `==` in Python?

Predict the output:

```python
a = [1, 2, 3]
b = [1, 2, 3]
c = a

print(a == b)
print(a is b)

print(a == c)
print(a is c)
```

## Answer

```text
True
False
True
True
```

## Explanation

### `==` — Compares Values

```python
a == b
```

Both contain:

```text
[1, 2, 3]
```

So:

```text
True
```

`==` checks whether the **values/content are equal**.

### `is` — Compares Object Identity

```python
a is b
```

Although `a` and `b` contain the same values, they are **different list objects**.

So:

```text
False
```

### Why is `a is c` True?

```python
c = a
```

Now both variables point to the same object:

```text
a ──┐
    ├──→ [1, 2, 3]
c ──┘
```

Therefore:

```python
a == c   # True
a is c   # True
```

## Easy Rule

```text
==  → Same VALUE?
is  → Same OBJECT?
```

## Common Interview Example

Use `is` for identity checks such as `None`:

```python
x = None

if x is None:
    print("No value")
```

## Coding Practice Question

What will be the output?

```python
x = [10, 20]
y = x
z = [10, 20]

print(x == y)
print(x is y)

print(x == z)
print(x is z)
```

### Answer

```text
True
True
True
False
```

## Interview Answer

> `==` compares the values of two objects, while `is` checks whether two variables refer to the same object in memory. `is` is commonly used for identity checks such as `x is None`.
