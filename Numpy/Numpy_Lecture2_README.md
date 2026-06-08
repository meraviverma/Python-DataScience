# ➕ Adding a New Axis in NumPy

NumPy lets you increase the dimensions of an array using **`np.newaxis`** or **`np.expand_dims`**.

---

## 🎯 Starting Point: 1D Array
```python
import numpy as np

a = np.array([1, 2, 3, 4, 5, 6])
print(a.shape)   # (6,)

---

## 🟦 Using `np.newaxis`

- **Row vector** (axis at position 0):
```python
row_vector = a[np.newaxis, :]
print(row_vector.shape)   # (1, 6)
```

- **Column vector** (axis at position 1):
```python
col_vector = a[:, np.newaxis]
print(col_vector.shape)   # (6, 1)
```

---

## 🟩 Using `np.expand_dims`

- Add axis at position 1:
```python
b = np.expand_dims(a, axis=1)
print(b.shape)   # (6, 1)
```

- Add axis at position 0:
```python
c = np.expand_dims(a, axis=0)
print(c.shape)   # (1, 6)
```

---

# ✂️ Indexing and Slicing

NumPy arrays behave like Python lists for slicing:

```python
data = np.array([1, 2, 3])

print(data[1])     # 2
print(data[0:2])   # [1 2]
print(data[1:])    # [2 3]
print(data[-2:])   # [2 3]
```

---

# 🔍 Conditional Selection

Filter arrays with conditions:

```python
a = np.array([[1, 2, 3, 4],
              [5, 6, 7, 8],
              [9, 10, 11, 12]])

print(a[a < 5])          # [1 2 3 4]
print(a[a >= 5])         # [ 5  6  7  8  9 10 11 12]
print(a[a % 2 == 0])     # [ 2  4  6  8 10 12]

c = a[(a > 2) & (a < 11)]
print(c)                 # [3 4 5 6 7 8 9 10]
```

---

# 📍 Finding Indices with `np.nonzero()`

```python
b = np.nonzero(a < 5)
print(b)   # (array([0,0,0,0]), array([0,1,2,3]))

# Coordinates of elements < 5
coords = list(zip(b[0], b[1]))
print(coords)   # [(0,0), (0,1), (0,2), (0,3)]

# Elements < 5
print(a[b])     # [1 2 3 4]
```

---

# 📝 Summary
- **`np.newaxis`** → quick way to add a new dimension  
- **`np.expand_dims`** → more explicit, lets you choose axis position  
- **Indexing/Slicing** → same as Python lists  
- **Conditional Selection** → filter arrays with logical operators  
- **`np.nonzero()`** → find indices of elements matching conditions
```