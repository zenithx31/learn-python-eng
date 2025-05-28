# Python Variables

## 📚 Introduction to Variables

In Python, a variable is a storage location for data.  
Variables are used to store values so they can be reused later in the program.

---

## 📚 What is a Variable?

A variable is a name that refers to a memory address where a value is stored.

```python
a = [1, 2, 3]  
print(id(a))  # Example: 12345678 (will vary at runtime)
```

The variable `a` refers to the memory location that stores the list `[1, 2, 3]`.  
The `id()` function returns the memory address of the object the variable refers to.

---

## 📚 Variable References

What happens when you assign variable `a` to another variable `b`?

```python
a = [1, 2, 3]
b = a  # b also refers to the same memory address as a

print(id(a))  # 12345678
print(id(b))  # 12345678 (same address)
```

When you write `b = a`, both variables refer to the same object in memory.  
Therefore, changing the value of `a` also affects `b`.

```python
a[1] = 4
print(a)  # [1, 4, 3]
print(b)  # [1, 4, 3]
```

This means both `a` and `b` are pointing to the same object.

---

## 📚 Copying a Variable as a New Object

If you want `b` to be a completely independent copy of `a`, use one of the following methods:

### · Copy Using Slicing

```python
a = [1, 2, 3]
b = a[:]  # Creates a copy using slicing

print(b is a)  # False (different object)
```

`a[:]` creates a shallow copy of all elements into a new list.

### · Copy Using the `copy` Module

```python
from copy import copy

a = [1, 2, 3]
b = copy(a)  # Copy using copy() function

print(b is a)  # False (different object)
```

The `copy()` function creates a new object with the same contents.

### · Copy Using List’s `copy()` Method

```python
a = [1, 2, 3]
b = a.copy()  # Copy using list's copy() method

print(b is a)  # False (different object)
```

This method is equivalent to using `copy.copy()`.

---

## 📚 Multiple Variable Assignment

Python allows you to assign values to multiple variables at once.

```python
# Using a tuple
a, b = ("Hello", "World")  
print(a)  # Hello
print(b)  # World

# Without parentheses (implicitly a tuple)
a, b = "Hello", "World"

# Using a list
[a, b] = ["Hello", "World"]

# Assigning the same value to multiple variables
a = b = "Hello"
print(a, b)  # Hello Hello
```

When assigning without parentheses like `a, b = ...`, Python automatically treats it as a tuple.  
With `a = b = "Hello"`, both variables are assigned the same value simultaneously.

---

## 📚 Swapping Variable Values

Swapping values in Python is simple and doesn't require a temporary variable.

```python
a = 1
b = 2

# Swap the values
a, b = b, a

print(a)  # 2
print(b)  # 1
```

Using `a, b = b, a` allows you to swap values directly in one line.
