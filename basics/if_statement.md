# Python Control Statements - `if` Statement

## 📚 Basics of `if` Statement

In Python, the `if` statement allows you to execute code only when a specific condition is met.  
It is an essential syntax that enables your program to behave differently depending on the situation.

---

## 📚 Basic Structure of an `if` Statement

```python
if condition:
    statement_1
    statement_2
else:
    statement_A
    statement_B
```

- After `if`, write a condition followed by a colon `:`.
- Indentation (tab or 4 spaces) is required.
- The `else` block runs when the condition is `False`.

**Example:**

```python
age = 18

if age >= 18:
    print("You are an adult.")
else:
    print("You are a minor.")
```

Since `age >= 18` is `True`, it prints:  
`You are an adult.`

---

## 📚 `if`-`elif`-`else` Structure

When there are multiple conditions, use `elif` (else if):

```python
if condition_1:
    statement_1
elif condition_2:
    statement_A
else:
    statement_B
```

- `elif` runs if the previous conditions were `False`.
- `else` runs if all conditions are `False`.

**Example:**

```python
score = 85

if score >= 90:
    print("Grade A")
elif score >= 80:
    print("Grade B")
else:
    print("Grade C")
```

Since `score = 85`, it prints:  
`Grade B`

---

## 📚 Comparison Operators

Common comparison operators used in `if` statements:

- `x < y` → `x` is less than `y`
- `x > y` → `x` is greater than `y`
- `x == y` → `x` is equal to `y`
- `x != y` → `x` is not equal to `y`
- `x >= y` → `x` is greater than or equal to `y`
- `x <= y` → `x` is less than or equal to `y`

**Example:**

```python
x = 1
y = 2

print(x < y)    # True
print(x == y)   # False
print(x >= y)   # False
print(x != y)   # True
```

Comparison operations always return `True` or `False`.

---

## 📚 Logical Operators (`and`, `or`, `not`)

Use logical operators to combine multiple conditions:

- `x and y` → `True` only if both `x` and `y` are `True`
- `x or y` → `True` if either `x` or `y` is `True`
- `not x` → reverses the truth value of `x`

**Example:**

```python
x = 10
y = 20

print(x > 5 and y > 15)   # True
print(x > 5 or y < 15)    # True
print(not (x > 5))        # False
```

---

## 📚 `in`, `not in` Operators

Used to check membership in lists, tuples, or strings:

- `x in collection` → `True` if `x` exists in the collection
- `x not in collection` → `True` if `x` does not exist in the collection

**Example:**

```python
fruits = ["apple", "banana", "cherry"]

print("banana" in fruits)     # True
print("grape" not in fruits)  # True
```

---

## 📚 `pass` Statement

Use `pass` when you want a placeholder that does nothing:

```python
if True:
    pass  # Do nothing
else:
    print("This won't run.")
```

The `pass` statement is used to avoid syntax errors in empty blocks.
