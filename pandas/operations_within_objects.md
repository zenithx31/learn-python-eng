# Operations Within Pandas Objects

## 📚 Operations Within Objects

In Pandas, you can easily perform various operations on DataFrame objects.

---

### Creating an Example DataFrame

```python
import pandas as pd

data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
```

Output:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

---

## 📚 Rounding (round)

The `round()` method lets you round numbers.

- decimals=0 (default): rounds to the nearest integer

```python
print(df_example.round(0))
```

Output:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

- decimals>0 (positive): rounds to n decimal places

```python
print(df_example.round(1))
```

Output:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

- decimals<0 (negative): rounds to the nearest 10^n place

```python
print(df_example.round(-1))
```

Output:

```
      col1  col2  col3
row1     0     0     0
row2     0     0    10
row3    10    10    10
```

---

## 📚 Sum (sum)

You can use `sum()` to calculate the sum of columns or rows.

- Sum by columns (axis=0)

```python
print(df_example.sum(axis=0))
```

Output:

```
col1    12
col2    15
col3    18
```

- Sum by rows (axis=1)

```python
print(df_example.sum(axis=1))
```

Output:

```
row1     6
row2    15
row3    24
```

---

## 📚 Product (prod)

`prod()` calculates the product of columns or rows.

- Product by columns (axis=0)

```python
print(df_example.prod(axis=0))
```

Output:

```
col1     28
col2     80
col3    162
```

- Product by rows (axis=1)

```python
print(df_example.prod(axis=1))
```

Output:

```
row1      6
row2    120
row3    504
```

---

## 📚 Absolute Value (abs)

`abs()` converts negative numbers to positive.

```python
import pandas as pd

data = [[1, -2, 3], [-4, 5, -6], [7, -8, 9]]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
```

Output:

```
      col1  col2  col3
row1     1    -2     3
row2    -4     5    -6
row3     7    -8     9
```

Calculate absolute values:

```python
print(df_example.abs())
```

Output:

```
      col1  col2  col3
row1     1     2     3
row2     4     5     6
row3     7     8     9
```

---

## 📚 Transpose (transpose)

`transpose()` flips rows and columns.

Shortcut: use `.T`

```python
import pandas as pd

data = [[1, 2, 'A'], [4, 5, 'B'], [7, 8, 'C']]
col = ['col1', 'col2', 'col3']
row = ['row1', 'row2', 'row3']
df_example = pd.DataFrame(data=data, index=row, columns=col)
print(df_example)
```

Output:

```
      col1  col2 col3
row1     1     2    A
row2     4     5    B
row3     7     8    C
```

Transpose:

```python
print(df_example.transpose())
```

Output:

```
      row1  row2  row3
col1     1     4     7
col2     2     5     8
col3     A     B     C
```

---

## 📚 Ranking (rank)

`rank()` calculates the rank of data.

There are various ranking methods.

```python
import pandas as pd

data = [[5], [1], [3], [5], [0.1], [30]]
row = ['A', 'B', 'C', 'D', 'E', 'F']
df_example = pd.DataFrame(data=data, index=row, columns=['Value'])
print(df_example)
```

Output:

```
   Value
A    5.0
B    1.0
C    3.0
D    5.0
E    0.1
F   30.0
```

Calculate ranks (various methods):

```python
df_example['average'] = df_example['Value'].rank(method='average')
df_example['min'] = df_example['Value'].rank(method='min')
df_example['max'] = df_example['Value'].rank(method='max')
df_example['first'] = df_example['Value'].rank(method='first')
df_example['dense'] = df_example['Value'].rank(method='dense')

print(df_example)
```

Output:

```
   Value  average  min  max  first  dense
A    5.0      4.5  4.0  5.0    4.0    4.0
B    1.0      2.0  2.0  2.0    2.0    2.0
C    3.0      3.0  3.0  3.0    3.0    3.0
D    5.0      4.5  4.0  5.0    5.0    4.0
E    0.1      1.0  1.0  1.0    1.0    1.0
F   30.0      6.0  6.0  6.0    6.0    5.0
```

