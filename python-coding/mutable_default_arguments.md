# Mutable Default Arguments — Problem and Solution

## Problem

Identify the issue in this code:

```python
def add_item(item, items=[]):
    items.append(item)
    return items


print(add_item("A"))
print(add_item("B"))
print(add_item("C"))
```

### Actual Output

```text
['A']
['A', 'B']
['A', 'B', 'C']
```

### Expected Output

```text
['A']
['B']
['C']
```

### Why?

The default list `items=[]` is created only once, when the function is defined. All calls share the same list.

## Solution

Use `None` as the default value and create a new list inside the function.

```python
def add_item(item, items=None):
    if items is None:
        items = []

    items.append(item)
    return items


print(add_item("A"))
print(add_item("B"))
print(add_item("C"))
```

### Output

```text
['A']
['B']
['C']
```

## Dictionary Example

### Wrong

```python
def add_user(name, users={}):
    users[name] = "active"
    return users
```

### Correct

```python
def add_user(name, users=None):
    if users is None:
        users = {}

    users[name] = "active"
    return users
```

## Key Point

```text
Mutable default: [] or {}

Use: None → create a new list/dict inside the function
```

## Interview Answer

> A mutable default argument such as a list or dictionary is created only once when the function is defined. Therefore, changes can persist across multiple function calls. We avoid this by using `None` as the default and creating a new mutable object inside the function.
