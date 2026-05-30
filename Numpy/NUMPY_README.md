# 🔢 NumPy: Numerical Python

NumPy (**Numerical Python**) is an open-source Python library widely used in **science** and **engineering**.  
It provides powerful **multidimensional array data structures** (`ndarray`) and a rich set of functions for efficient computation.

---

## 📦 Key Characteristics of NumPy Arrays
- **Homogeneous**: All elements must be of the same data type.
- **Fixed size**: Once created, the total size cannot change.
- **Rectangular shape**: Each row in a 2D array must have the same number of columns.
- **Mutable**: Arrays can be modified after creation.

---

## 🔍 Copies vs Views

### 👁️ View
- A **view** changes only metadata (like stride or dtype).  
- The underlying data buffer remains the same.  
- ✅ Efficient, but changes in the view **reflect in the original array**.

### 📑 Copy
- A **copy** duplicates both the data buffer and metadata.  
- Changes in the copy **do not affect** the original array.  
- ❌ Slower and memory-consuming, but sometimes necessary.  
- Use `ndarray.copy()` to force a copy.

---

## 📐 Array Attributes
- **`ndim`** → Number of dimensions  
- **`shape`** → Tuple specifying elements along each dimension  
- **`dtype`** → Data type of elements  

---

## ✅ Example

```python
import numpy as np

# Create an array
arr = np.array([[1, 2, 3], [4, 5, 6]])

print("Array:\n", arr)
print("Dimensions:", arr.ndim)   # 2
print("Shape:", arr.shape)       # (2, 3)
print("Data type:", arr.dtype)   # int64 (platform-dependent)

# View vs Copy
view_arr = arr.view()
copy_arr = arr.copy()

view_arr[0,0] = 99
print("Original after view change:\n", arr)  # Reflects change

copy_arr[0,0] = 77
print("Original after copy change:\n", arr)  # No change

```

# 🔢 Creating Arrays in NumPy

Besides creating arrays from sequences, NumPy provides convenient functions to generate arrays quickly.

---

## 🟦 Arrays Filled with Constants
```python
import numpy as np

np.zeros(2)   # Array of zeros
# Output: array([0., 0.])

np.ones(2)    # Array of ones
# Output: array([1., 1.])
```

---

## ⚡ Empty Arrays
`np.empty()` creates an array without initializing values.  
⚠️ Contents are random (depend on memory state). Use when speed matters, but **always overwrite values**.

```python
np.empty(2)
# Output: array([3.14, 42. ])  # may vary
```

---

## 📈 Arrays with Ranges
```python
np.arange(4)          # Range of elements
# Output: array([0, 1, 2, 3])

np.arange(2, 9, 2)    # Start, stop, step
# Output: array([2, 4, 6, 8])
```

---

## 📏 Linearly Spaced Arrays
```python
np.linspace(0, 10, num=5)
# Output: array([0., 2.5, 5., 7.5, 10.])
```

---

## 🧩 Specifying Data Types
By default, arrays use `float64`. You can explicitly set `dtype`.

```python
x = np.ones(2, dtype=np.int64)
# Output: array([1, 1])
```

---

# 🔄 Adding, Removing, and Sorting Elements

## 📊 Sorting
```python
arr = np.array([2, 1, 5, 3, 7, 4, 6, 8])
np.sort(arr)
# Output: array([1, 2, 3, 4, 5, 6, 7, 8])
```

### Other Sorting Functions
- **`argsort`** → Indirect sort, returns indices  
- **`lexsort`** → Stable sort on multiple keys  
- **`searchsorted`** → Finds insertion points in sorted arrays  
- **`partition`** → Partial sort (fast for selection problems)

---

## ➕ Concatenation
```python
a = np.array([1, 2, 3, 4])
b = np.array([5, 6, 7, 8])

np.concatenate((a, b))
# Output: array([1, 2, 3, 4, 5, 6, 7, 8])
```

---

# 🎯 Summary
- **Array creation**: `zeros`, `ones`, `empty`, `arange`, `linspace`  
- **Data types**: Default `float64`, customizable with `dtype`  
- **Sorting**: `sort`, `argsort`, `lexsort`, `searchsorted`, `partition`  
- **Concatenation**: Combine arrays seamlessly  

NumPy makes array creation and manipulation **fast, flexible, and efficient** — essential for data science and machine learning workflows.
```


