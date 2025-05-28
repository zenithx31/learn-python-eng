# Basic Numpy Syntax and Examples

📚 What is Numpy?

Numpy stands for "Numeric Python".  
It is a powerful Python library used for numerical computing.  
Compared to plain Python, Numpy provides a much faster way to process large-scale numerical data.

Numpy enables efficient manipulation of vectors and matrices through its core data structure, `ndarray`.

It is widely used in linear algebra, scientific computations, and data analysis.

---

📚 np.array()

`np.array()` is used to create an `ndarray`, which is the core data structure of Numpy.

### 1) 1D Array
~~~python
import numpy as np
vec = np.array([1, 2, 3, 4, 5])
print(vec)
# Output:
# [1 2 3 4 5]
~~~

### 2) 2D Array
~~~python
import numpy as np
mat = np.array([[10, 20, 30], [40, 50, 60]])
print(mat)
# Output:
# [[10 20 30]
#  [40 50 60]]
~~~

### 3) Type Check
~~~python
print(type(vec))
print(type(mat))
# Output:
# <class 'numpy.ndarray'>
# <class 'numpy.ndarray'>
~~~

### 4) Dimension Check
~~~python
print(vec.ndim)  # 1D
print(mat.ndim)  # 2D
# Output:
# 1
# 2
~~~

### 5) Shape Check
~~~python
print(vec.shape)  # (5,)
print(mat.shape)  # (2, 3)
# Output:
# (5,)
# (2, 3)
~~~

---

📚 Initializing Arrays

Numpy provides various methods for easy array initialization.

### 1) Array filled with zeros
~~~python
import numpy as np
zero = np.zeros((2, 3))
print(zero)
# Output:
# [[0. 0. 0.]
#  [0. 0. 0.]]
~~~

### 2) Array filled with ones
~~~python
import numpy as np
one = np.ones((2, 3))
print(one)
# Output:
# [[1. 1. 1.]
#  [1. 1. 1.]]
~~~

### 3) Array filled with a specific value
~~~python
import numpy as np
same_value = np.full((2, 3), 5)
print(same_value)
# Output:
# [[5 5 5]
#  [5 5 5]]
~~~

### 4) Identity matrix
~~~python
import numpy as np
eye = np.eye(5)
print(eye)
# Output:
# [[1. 0. 0. 0. 0.]
#  [0. 1. 0. 0. 0.]
#  [0. 0. 1. 0. 0.]
#  [0. 0. 0. 1. 0.]
#  [0. 0. 0. 0. 1.]]
~~~

### 5) Random values
~~~python
import numpy as np
random = np.random.random((2, 3))
print(random)
# Output (example):
# [[0.55580566 0.58351512 0.6544916 ]
#  [0.09908401 0.25436744 0.44398083]]
~~~

---

📚 np.arange()

`np.arange()` creates an array with evenly spaced values in a given range.

### 1) Create array from 0 to n-1
~~~python
import numpy as np
range_vec = np.arange(10)
print(range_vec)
# Output:
# [0 1 2 3 4 5 6 7 8 9]
~~~

### 2) Create array with step n
~~~python
import numpy as np
n = 2
range_step_vec = np.arange(1, 10, n)
print(range_step_vec)
# Output:
# [1 3 5 7 9]
~~~

---

📚 np.reshape()

`np.reshape()` changes the shape of an array without altering its data.

~~~python
import numpy as np
reshape = np.array(np.arange(30))
reshape = reshape.reshape((5, 6))
print(reshape)
~~~

---

📚 Numpy Slicing

You can extract parts of an array using slicing.

### 1) Get the first row
~~~python
import numpy as np
mat = np.array([[1, 2, 3], [4, 5, 6]])
slice_mat1 = mat[0, :]
print(slice_mat1)
# Output:
# [1 2 3]
~~~

### 2) Get the first column
~~~python
slice_mat2 = mat[:, 0]
print(slice_mat2)
# Output:
# [1 4]
~~~

---

📚 Integer Indexing

Access or extract values from specific positions using integer indexing.

### 1) Access a specific element
~~~python
import numpy as np
mat = np.array([[1, 2], [3, 4], [5, 6]])
print(mat[1, 0])  # 3
# Output:
# 3
~~~

### 2) Create new array using indexing
~~~python
index_mat = mat[[2, 1], [0, 1]]
print(index_mat)
# Output:
# [5 4]
~~~

---

📚 Numpy Operations

Numpy allows simple and efficient element-wise operations on arrays.

### 1) Addition
~~~python
import numpy as np
x = np.array([1, 2, 3])
y = np.array([4, 5, 6])
result1 = x + y
result2 = np.add(x, y)
print(result1)
print(result2)
# Output:
# [5 7 9]
# [5 7 9]
~~~

### 2) Subtraction
~~~python
result1 = x - y
result2 = np.subtract(x, y)
print(result1)
print(result2)
# Output:
# [-3 -3 -3]
# [-3 -3 -3]
~~~

### 3) Division
~~~python
result1 = x / y
result2 = np.divide(x, y)
print(result1)
print(result2)
# Output:
# [0.25 0.4  0.5 ]
# [0.25 0.4  0.5 ]
~~~

### 4) Multiplication (element-wise)
~~~python
result1 = x * y
print(result1)
# Output:
# [ 4 10 18]
~~~

### 5) Dot Product
~~~python
result2 = np.dot(x, y)
print(result2)
# Output:
# 32
~~~
