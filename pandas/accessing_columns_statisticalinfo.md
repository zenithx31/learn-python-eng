# Accessing DataFrame Columns & Statistical Info in Pandas

---

📚 **Accessing DataFrame Columns**

There are several ways to access columns in a Pandas DataFrame.

### 1. Accessing a Single Column

```python
df.column_name      # Access using dot notation
df['column_name']   # Access using bracket notation
```

Example:

```python
import pandas as pd  

# Create sample data  
data = {'number1': [10, 20, 30, 40, 50],  
        'number2': [5, 15, 25, 35, 45]}  
df_sample = pd.DataFrame(data)  

# Print a single column
print(df_sample.number1)  
print(df_sample['number1'])  
```

Output:

```
0    10  
1    20  
2    30  
3    40  
4    50  
Name: number1, dtype: int64  
```

---

### 2. Accessing Multiple Columns

```python
df[['column1', 'column2']]
```

Example:

```python
print(df_sample[['number1', 'number2']])
```

Output:

```
   number1  number2  
0       10        5  
1       20       15  
2       30       25  
3       40       35  
4       50       45  
```

> ✅ Dot notation only works for single columns  
> ✅ Use double brackets `[[]]` to select multiple columns

---

📚 **Statistical Information of a DataFrame**

Pandas makes it easy to get statistical summaries of data.

---

### 1. Summary Statistics of All Columns (`describe()`)

```python
df.describe()
```

Example:

```python
print(df_sample.describe())
```

Output:

```
        number1  number2  
count       5.0       5.0  
mean       30.0      25.0  
std        15.8      15.8  
min        10.0       5.0  
25%        20.0      15.0  
50%        30.0      25.0  
75%        40.0      35.0  
max        50.0      45.0  
```

Explanation:

- `count`: Number of entries  
- `mean`: Average value  
- `std`: Standard deviation  
- `min`: Minimum value  
- `25%, 50%, 75%`: Quartiles (median included)  
- `max`: Maximum value

---

### 2. Summary Statistics of a Specific Column

```python
df['column_name'].describe()
```

Example:

```python
print(df_sample['number1'].describe())
```

Output:

```
count     5.0  
mean     30.0  
std      15.8  
min      10.0  
25%      20.0  
50%      30.0  
75%      40.0  
max      50.0  
```

---

### 3. Individual Statistical Metrics

```python
df['column_name'].mean()    # Mean  
df['column_name'].max()     # Max  
df['column_name'].min()     # Min  
df['column_name'].sum()     # Sum  
df['column_name'].count()   # Count  
```

Example:

```python
print("Mean:", df_sample['number1'].mean())  
print("Max:", df_sample['number1'].max())  
print("Min:", df_sample['number1'].min())  
print("Sum:", df_sample['number1'].sum())  
print("Count:", df_sample['number1'].count())  
```

Output:

```
Mean: 30.0  
Max: 50  
Min: 10  
Sum: 150  
Count: 5  
```

---
