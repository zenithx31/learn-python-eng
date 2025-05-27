# Python Boolean Types

## 📚 Basics of Boolean Data Type

In Python, the Boolean data type represents truth values: True and False.  
It is mainly used to determine truthiness in conditional statements.

---

## 📚 Boolean Values

There are two Boolean values:

```python
print(True)   # True
print(False)  # False
```

True and False must be capitalized.
Using lowercase true or false will cause an error.

---

## 📚 Boolean Comparison Operations

Boolean values often result from comparison operations.

```python
print(3 > 1)   # True
print(3 < 1)   # False
print(3 == 3)  # True
print(3 != 3)  # False
print(5 >= 3)  # True
print(2 <= 1)  # False
```

Comparison operations always return either True or False.

---

## 📚 Boolean Logical Operations

Boolean values are frequently used with logical operators like and, or, and not.

```python
print(True and False)  # False
print(True or False)   # True
print(not True)        # False
```

- The and operator returns True only if all conditions are True.
- The or operator returns True if at least one condition is True.

---

## 📚 Boolean in Conditional Statements

Boolean values play a key role in conditional statements.

```python
age = 18

if age >= 18:
    print("You are an adult.")  # Output: You are an adult.
else:
    print("You are a minor.")
```

In the above code, since age >= 18 evaluates to True, "You are an adult." is printed.

---

## 📚 Boolean Evaluation of Other Data Types

In Python, various data types like numbers, strings, and lists can also be evaluated as True or False.

- Values considered False:

  - 0 (integer zero, float zero)  
  - "" (empty string)
  - [] (empty list)
  - {} (empty dictionary) 
  - set() (empty set)  
  - None (no value) 

```python
print(bool(0))      # False
print(bool(""))     # False
print(bool([]))     # False
print(bool(None))   # False
```

All other values are evaluated as True.

```python
print(bool(1))          # True
print(bool("hello"))    # True
print(bool([1, 2, 3]))  # True
```
