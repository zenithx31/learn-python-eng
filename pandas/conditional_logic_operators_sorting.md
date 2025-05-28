# Conditional Logic, Operators, and Sorting in Pandas

---

## 📚 Conditional Logic in DataFrames

Pandas allows filtering rows based on specific conditions.

---

### 1. Selecting Rows that Meet a Condition

```python
df['column_name'] == 'condition'
```

**Example:**

```python
import pandas as pd  

data = {'number': [100, 50, 200, 100, 300],  
        'value': [10, 20, 30, 40, 50]}  
df_sample = pd.DataFrame(data)  

filtered_df = df_sample[df_sample['number'] == 100]
print(filtered_df)
```

**Output:**

```
   number  value  
0    100     10  
3    100     40  
```

---

### 2. Selecting the First N Rows that Meet a Condition

```python
df[df['column_name'] == 'condition'].head(N)
```

**Example:**

```python
print(df_sample[df_sample['number'] == 100].head(1))
```

**Output:**

```
   number  value  
0    100     10  
```

---

### 3. Checking and Filtering Null Values

#### 1) Check for Nulls

```python
df['column_name'].isnull()
```

**Example:**

```python
df_sample['number'].isnull()
```

**Output:**

```
0    False  
1    False  
2    False  
3    False  
4    False  
Name: number, dtype: bool  
```

#### 2) Filter Rows with Null Values

```python
df[df['column_name'].isnull()]
```

---

## 📚 Operators in Pandas (AND, OR, NOT)

You can combine multiple conditions to filter data.

---

### 1. NOT (~): Exclude a Condition

```python
df[~(condition)]
```

**Example:**

```python
print(df_sample[~(df_sample['number'] == 100)])
```

**Output:**

```
   number  value  
1     50     20  
2    200     30  
4    300     50  
```

---

### 2. AND (&): Rows that Satisfy All Conditions

```python
df[(condition1) & (condition2)]
```

**Example:**

```python
print(df_sample[(df_sample['number'] == 100) & (df_sample['value'] == 10)])
```

**Output:**

```
   number  value  
0    100     10  
```

---

### 3. OR (|): Rows that Satisfy At Least One Condition

```python
df[(condition1) | (condition2)]
```

**Example:**

```python
print(df_sample[(df_sample['number'] == 100) | (df_sample['value'] == 50)])
```

**Output:**

```
   number  value  
0    100     10  
3    100     40  
4    300     50  
```

---

## 📚 Sorting DataFrames

You can sort data using one or more columns.

---

### 1. Sort by a Single Column

```python
df.sort_values('column_name')  # Ascending  
df.sort_values('column_name', ascending=False)  # Descending  
```

**Example:**

```python
print(df_sample.sort_values('number'))
```

**Output:**

```
   number  value  
1     50     20  
0    100     10  
3    100     40  
2    200     30  
4    300     50  
```

**Descending:**

```python
print(df_sample.sort_values('number', ascending=False))
```

**Output:**

```
   number  value  
4    300     50  
2    200     30  
0    100     10  
3    100     40  
1     50     20  
```

---

### 2. Sort by Multiple Columns

```python
df.sort_values(['column1', 'column2'])
```

**Example:**

```python
print(df_sample.sort_values(['number', 'value']))
```

**Output:**

```
   number  value  
1     50     20  
0    100     10  
3    100     40  
2    200     30  
4    300     50  
```
