# Pandas - DataFrame

📚 **What is Pandas?**

Pandas is a Python library for data analysis and manipulation.  
It provides a powerful data structure called the **DataFrame**, similar to Excel tables, making data handling easier and more efficient.

---

📚 **Creating a DataFrame**

Let's create a simple DataFrame.

~~~python
import pandas as pd  

# Sample data  
data = [[1, 2], [3, 4], [5, 6], [7, 8], [9, 10], 
        [11, 12], [13, 14], [15, 16], [17, 18], [19, 20]]  

col = ['col1', 'col2']  # Column names  
row = ['row1', 'row2', 'row3', 'row4', 'row5', 
       'row6', 'row7', 'row8', 'row9', 'row10']  # Row names  

df = pd.DataFrame(data=data, index=row, columns=col)  
print(df)
~~~

Output:

```
       col1  col2  
row1      1     2  
row2      3     4  
row3      5     6  
row4      7     8  
row5      9    10  
row6     11    12  
row7     13    14  
row8     15    16  
row9     17    18  
row10    19    20  
```

---

📚 **Displaying a DataFrame**

### 1. Display top rows (`head()`)

~~~python
print(df.head())      # Default: first 5 rows
print(df.head(8))     # Display first 8 rows
~~~

### 2. Display bottom rows (`tail()`)

~~~python
print(df.tail())      # Default: last 5 rows
print(df.tail(8))     # Display last 8 rows
~~~

### 3. Display random rows (`sample()`)

~~~python
print(df.sample())      # One random row
print(df.sample(5))     # Five random rows
~~~

---

📚 **Basic DataFrame Information**

### 1. Index (`index`)

~~~python
print(df.index)
~~~

Output:

```
Index(['row1', 'row2', 'row3', 'row4', 'row5', 
       'row6', 'row7', 'row8', 'row9', 'row10'], 
      dtype='object')
```

### 2. Data types (`dtypes`)

~~~python
print(df.dtypes)
~~~

Output:

```
col1    int64  
col2    int64  
dtype: object
```

### 3. Shape (`shape`)

~~~python
print(df.shape)
~~~

Output:

```
(10, 2)  # 10 rows, 2 columns
```

### 4. Values (`values`)

~~~python
print(df.values)
~~~

Output:

```
[[ 1  2]  
 [ 3  4]  
 [ 5  6]  
 [ 7  8]  
 [ 9 10]  
 [11 12]  
 [13 14]  
 [15 16]  
 [17 18]  
 [19 20]]
```

### 5. Info (`info()`)

~~~python
print(df.info())
~~~

Output:

```
<class 'pandas.core.frame.DataFrame'>  
Index: 10 entries, row1 to row10  
Data columns (total 2 columns):  
 #   Column  Non-Null Count  Dtype  
---  ------  --------------  -----  
 0   col1    10 non-null     int64  
 1   col2    10 non-null     int64  
dtypes: int64(2)  
memory usage: 240.0+ bytes  
```

---

📚 **Checking for Missing Values (Null)**

Missing values refer to data that is absent or not recorded.  
You can check for them using `isnull()`.

### 1. Check for null values (`isnull()`)

~~~python
print(df.isnull())
~~~

Output:

```
       col1   col2  
row1  False  False  
row2  False  False  
row3  False  False  
row4  False  False  
row5  False  False  
row6  False  False  
row7  False  False  
row8  False  False  
row9  False  False  
row10 False  False
```

→ All values are `False`, so no missing data.

### 2. Count missing values (`isnull().sum()`)

~~~python
print(df.isnull().sum())
~~~

Output:

```
col1    0  
col2    0  
dtype: int64
```

→ All values exist (no nulls).

---
