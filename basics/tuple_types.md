# Python Tuple Types

## 📚 What is a Tuple?

A **tuple** is a data type in Python that allows you to store multiple values together.  
It is similar to a list, but unlike lists, **tuples are immutable**, meaning once created, their values cannot be changed.

Tuples are created using parentheses `()` and **cannot be modified (no adding or removing elements)** after creation.

```python
# Examples of creating tuples
a = (1, 2, 3)  # Tuple of integers
b = ('a', 'b', 'c')  # Tuple of strings
c = (1, 2, 'a', 'b')  # Mixed types
d = (1, 2, (3, 4))  # Nested tuple
```

---

## 📚 Tuple Indexing

You can access specific elements of a tuple using indexing.

```python
a = (1, 2, 'a', 'b')

print(a[0])  # 1 (first element)
print(a[2])  # 'a' (third element)
```

You can also access elements inside a nested tuple.

```python
a = (1, 2, (3, 4))

print(a[2])    # (3, 4)
print(a[2][0]) # 3
```

---

## 📚 Tuple Slicing

You can use slicing to retrieve a range of elements from a tuple.

```python
a = (1, 2, 'a', 'b')

print(a[1:])  # (2, 'a', 'b')
```

---

## 📚 Tuple Operations

Just like lists, tuples support **addition (`+`) and multiplication (`*`)** operations.

### 1) Tuple Addition (`+`)

You can concatenate two tuples.

```python
a = (1, 2, 'a', 'b')
b = (3, 4)

c = a + b
print(c)  # (1, 2, 'a', 'b', 3, 4)
```

### 2) Tuple Multiplication (`*`)

You can repeat a tuple multiple times.

```python
a = (1, 2)

b = a * 3
print(b)  # (1, 2, 1, 2, 1, 2)
```

### 3) Tuple Length (`len()`)

You can find out how many items are in a tuple using `len()`.

```python
a = (1, 2, 'a', 'b')

print(len(a))  # 4
```
