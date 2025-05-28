# Python List Types

## 📚 What is a List?

A **List** in Python is a data type used to store multiple values together in a single variable.  
With lists, you can store numbers, strings, or even other lists.

```python
# List creation examples
a = []  # Empty list
b = [1, 2, 3]  # List of numbers
c = ['Life', 'is', 'too', 'short']  # List of strings
d = [1, 2, 'Life', 'is']  # Mixed list of numbers and strings
e = [1, 2, ['Life', 'is']]  # Nested list
```

---

## 📚 List Indexing

Indexing is how you access individual elements in a list using their position.

```python
a = [1, 2, 3]

print(a[0])  # 1 (first element)
print(a[1])  # 2
print(a[-1]) # 3 (last element)
```

You can also access elements within nested lists:

```python
a = [1, 2, 3, ['a', 'b', 'c']]

print(a[3])    # ['a', 'b', 'c']
print(a[3][0]) # 'a'
```

---

## 📚 List Slicing

Slicing lets you extract a range of elements from a list.

```python
a = [1, 2, 3, 4, 5]

print(a[0:2])  # [1, 2]
print(a[:2])   # [1, 2]
print(a[2:])   # [3, 4, 5]
```

You can also slice within nested lists:

```python
a = [1, 2, 3, ['a', 'b', 'c'], 4, 5]

print(a[3][:2])  # ['a', 'b']
```

---

## 📚 List Operations

Lists support operations like addition and multiplication.

```python
a = [1, 2, 3]
b = [4, 5, 6]

print(a + b)  # [1, 2, 3, 4, 5, 6]
print(a * 2)  # [1, 2, 3, 1, 2, 3]
print(len(a)) # 3
```

---

## 📚 Modifying Lists

You can change list elements by using their index.

```python
a = [1, 2, 3]
a[2] = 4

print(a)  # [1, 2, 4]
```

---

## 📚 Deleting List Elements

Use the `del` keyword to remove elements from a list.

```python
a = [1, 2, 3]
del a[1]

print(a)  # [1, 3]
```

You can delete multiple elements at once:

```python
a = [1, 2, 3, 4, 5]
del a[2:]

print(a)  # [1, 2]
```

---

## 📚 Built-in List Methods

### 1) Add Element (`append`)

```python
a = [1, 2, 3]
a.append(4)

print(a)  # [1, 2, 3, 4]

a.append([5, 6])
print(a)  # [1, 2, 3, 4, [5, 6]]
```

---

### 2) Sort List (`sort`)

```python
a = [3, 1, 4, 2]
a.sort()

print(a)  # [1, 2, 3, 4]

b = ['c', 'a', 'b']
b.sort()

print(b)  # ['a', 'b', 'c']
```

---

### 3) Reverse List (`reverse`)

```python
a = [1, 3, 2]
a.reverse()

print(a)  # [2, 3, 1]
```

---

### 4) Find Index of Value (`index`)

```python
a = [1, 2, 3]

print(a.index(3))  # 2
print(a.index(1))  # 0

# Searching for a non-existent value raises an error
# print(a.index(0))  # ValueError
```

---

### 5) Insert Element (`insert`)

```python
a = [1, 2, 3]
a.insert(0, 4)

print(a)  # [4, 1, 2, 3]
```

---

### 6) Remove Element (`remove`)

```python
a = [1, 2, 3, 3, 4, 5]
a.remove(3)  # Removes the first occurrence of 3

print(a)  # [1, 2, 3, 4, 5]
```

---

### 7) Pop Element (`pop`)

```python
a = [1, 2, 3]
print(a.pop())  # 3

print(a)  # [1, 2]

a = [1, 2, 3]
print(a.pop(1))  # 2

print(a)  # [1, 3]
```

---

### 8) Count Occurrences (`count`)

```python
a = [1, 2, 3, 1, 2, 3]

print(a.count(2))  # 2
```

---

### 9) Extend List (`extend`)

```python
a = [1, 2, 3]
a.extend([4, 5])

print(a)  # [1, 2, 3, 4, 5]

b = [6, 7]
a.extend(b)

print(a)  # [1, 2, 3, 4, 5, 6, 7]
```
