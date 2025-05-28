# Operations Between Pandas Objects

## 📚 Operations Between Objects

In pandas, you can easily perform various operations between objects like DataFrames or Series.

---

### Creating a Sample DataFrame

Let's create a simple DataFrame first.

~~~python
import pandas as pd

# Define data
data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']

# Create DataFrame
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
~~~

Output:

~~~
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
~~~

---

## 📚 Addition (add, radd)

### 1. Adding a Number

Adding a number to a DataFrame adds that number to every element.

~~~python
result1 = df_example.add(1)
print(result1)
~~~

Output:

~~~
      col1  col2  col3
row1     2     3     4
row2     5     6     7
row3     8     9    10
~~~

The `add()` method and the `+` operator produce the same result.

~~~python
result2 = df_example + 1
print(result2)
~~~

Output:

~~~
      col1  col2  col3
row1     2     3     4
row2     5     6     7
row3     8     9    10
~~~

---

### 2. Adding Another DataFrame

Here’s an example of adding two DataFrame objects.

NaN values are ignored by default in the operation.

~~~python
data_add = [[3], [4], [5]]
df_add = pd.DataFrame(data=data_add, index=['row1', 'row2', 'row3'], columns=['col1'])

result3 = df_example.add(df_add)
print(result3)
~~~

Output:

~~~
      col1  col2  col3
row1     4   NaN   NaN
row2     8   NaN   NaN
row3    12   NaN   NaN
~~~

---

### 3. Handling NaN Values

You can use the `fill_value` option to fill NaN with another value.

~~~python
result4 = df_example.add(df_add, fill_value=1)  # Fill NaN with 1
print(result4)
~~~

Output:

~~~
      col1  col2  col3
row1     4   3.0   4.0
row2     8   6.0   7.0
row3    12   9.0  10.0
~~~

---

## 📚 Subtraction (sub, rsub)

### 1. Subtracting a Number

~~~python
result1 = df_example.sub(1)
print(result1)
~~~

Output:

~~~
      col1  col2  col3
row1     0     1     2
row2     3     4     5
row3     6     7     8
~~~

`sub()` and the `-` operator behave the same.

~~~python
result2 = df_example - 1
print(result2)
~~~

Output:

~~~
      col1  col2  col3
row1     0     1     2
row2     3     4     5
row3     6     7     8
~~~

---

### 2. Subtracting Another DataFrame

~~~python
result3 = df_example.sub(df_add)
print(result3)
~~~

Output:

~~~
      col1  col2  col3
row1    -2   NaN   NaN
row2     0   NaN   NaN
row3     2   NaN   NaN
~~~

---

### 3. Handling NaN Values

~~~python
result4 = df_example.sub(df_add, fill_value=1)
print(result4)
~~~

Output:

~~~
      col1  col2  col3
row1    -2   1.0   2.0
row2     0   4.0   5.0
row3     2   7.0   8.0
~~~

---

## 📚 Multiplication (mul, rmul)

### 1. Multiplying by a Number

~~~python
result1 = df_example.mul(2)
print(result1)
~~~

Output:

~~~
      col1  col2  col3
row1     2     4     6
row2     8    10    12
row3    14    16    18
~~~

---

### 2. Multiplying by Another DataFrame

~~~python
result3 = df_example.mul(df_add)
print(result3)
~~~

Output:

~~~
      col1  col2  col3
row1     3   NaN   NaN
row2    16   NaN   NaN
row3    35   NaN   NaN
~~~

---

### 3. Handling NaN Values

~~~python
result4 = df_example.mul(df_add, fill_value=1)
print(result4)
~~~

Output:

~~~
      col1  col2  col3
row1     3   2.0   3.0
row2    16   5.0   6.0
row3    35   8.0   9.0
~~~

---

## 📚 Division (div, rdiv)

### 1. Dividing by a Number

~~~python
result1 = df_example.div(2)
print(result1)
~~~

Output:

~~~
      col1  col2  col3
row1   0.5   1.0   1.5
row2   2.0   2.5   3.0
row3   3.5   4.0   4.5
~~~

---

### 2. Dividing by Another DataFrame

~~~python
result3 = df_example.div(df_add)
print(result3)
~~~

Output:

~~~
      col1  col2  col3
row1  0.333333   NaN   NaN
row2  1.000000   NaN   NaN
row3  1.400000   NaN   NaN
~~~

---

### 3. Handling NaN Values

~~~python
result4 = df_example.div(df_add, fill_value=1)
print(result4)
~~~

Output:

~~~
      col1  col2  col3
row1  0.333333   2.0   3.0
row2  1.000000   5.0   6.0
row3  1.400000   8.0   9.0
~~~

---

## 📚 Modulo (mod, rmod)

### 1. Modulo with a Number

~~~python
result1 = df_example.mod(2)
print(result1)
~~~

Output:

~~~
      col1  col2  col3
row1     1     0     1
row2     0     1     0
row3     1     0     1
~~~

---

## 📚 Power (pow, rpow)

### 1. Power with a Number

~~~python
result1 = df_example.pow(2)
print(result1)
~~~

Output:

~~~
      col1  col2  col3
row1     1     4     9
row2    16    25    36
row3    49    64    81
~~~

---

### 2. Power with Another DataFrame

~~~python
result3 = df_example.pow(df_add)
print(result3)
~~~

Output:

~~~
      col1  col2  col3
row1      1   NaN   NaN
row2    256   NaN   NaN
row3  16807   NaN   NaN
~~~

---

## 📚 Matrix Multiplication (dot)

Matrix multiplication can be performed between two DataFrames using the `dot()` method.

~~~python
# Create sample DataFrames
data1 = [[1, 2], [3, 4]]
data2 = [[5, 6], [7, 8]]
df1 = pd.DataFrame(data=data1)
df2 = pd.DataFrame(data=data2)

result = df1.dot(df2)
print(result)
~~~

Output:

~~~
    0   1
0  19  22
1  43  50
~~~
