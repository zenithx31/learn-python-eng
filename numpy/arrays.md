# 1D and 2D Arrays in Numpy

## 📚 1D Arrays

Using Numpy, you can easily convert Python lists into arrays and perform fast operations on them. Numpy arrays are optimized for efficient computation, enabling very fast mathematical calculations.

---

Example 1: Creating a 1D array

~~~python
import numpy as np

data = [1, 2, 3]
arr = np.array(data)
print(arr)
print(type(arr))

# Output
# [1 2 3]
# <class 'numpy.ndarray'>
~~~

This code converts the list `data` into a Numpy array, prints the array, and checks its data type.  
Numpy arrays have the type `numpy.ndarray`.

---

Example 2: Applying an operation to all elements of the array

Numpy allows applying the same operation to all elements of an array without using loops.

~~~python
import numpy as np

data = [1, 2, 3]
arr = np.array(data)
result = arr * 10
print(result)

# Output
# [10 20 30]
~~~

This code multiplies each element in the array by 10 and prints the result.  
Numpy performs such operations quickly and efficiently through vectorization.

---

## 📚 2D Arrays

Numpy lets you create 2D arrays and easily select specific elements. Numpy arrays are also very useful for matrix operations.

---

Example 1: Creating a 2D array

~~~python
import numpy as np

data = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

arr = np.array(data)
print(arr)

# Output
# [[1 2 3]
#  [4 5 6]
#  [7 8 9]]
~~~

---

Example 2: Selecting specific elements from the array

To access a specific element in the array, use the format `arr[row, column]`.

~~~python
print(arr[:, 0])

# Output
# [1 4 7]
~~~

In this code, `:` means all rows, and `0` means the first column.  
As a result, the values in the first column of the array are printed.
