# Shallow Copy / Deep Copy Program

```python
import copy

original = [[1, 2], [3, 4]]

# shallow = copy.copy(original)
shallow = copy.deepcopy(original)

print(original)
print(shallow)

shallow[0][0] = 100

print(original)
print(shallow)
```

## Output

```text
[[1, 2], [3, 4]]
[[1, 2], [3, 4]]
[[1, 2], [3, 4]]
[[100, 2], [3, 4]]
```

## Explanation

Here:

```python
shallow = copy.deepcopy(original)
```

The variable is named `shallow`, but `copy.deepcopy()` creates a **deep copy**.

So `original` and `shallow` have separate nested lists.

When we change:

```python
shallow[0][0] = 100
```

only `shallow` changes.

### If you use shallow copy

Change:

```python
shallow = copy.deepcopy(original)
```

to:

```python
shallow = copy.copy(original)
```

Then the output will be:

```text
[[100, 2], [3, 4]]
[[100, 2], [3, 4]]
```

The nested list is shared because `copy.copy()` creates a shallow copy.

## Key Point

```text
copy.copy()      → Shallow Copy → nested objects are shared
copy.deepcopy()  → Deep Copy    → nested objects are independent
```
