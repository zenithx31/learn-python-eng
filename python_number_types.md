# [ Python ] Summary of Python's Number Data Types

## 📚 Number Data Types

---

### 1. Integer

Integers are whole numbers including positive numbers, negative numbers, and zero.

```python
a = 123   # positive integer  
b = -123  # negative integer  
c = 0     # zero
```

---

### 2. Floating-point

Floating-point numbers are used to represent numbers with decimal points.

```python
a = 123.45   # positive float  
b = -123.45  # negative float
```

---

### 3. Octal

Octal numbers start with `0o` (or `0O`).

Octal uses digits from 0 to 7 and is often used in computing for memory addresses or bit-level operations.

```python
a = 0o123  # octal for 83
```

---

### 4. Hexadecimal

Hexadecimal numbers start with `0x` (or `0X`) and use digits and letters from A to F to represent 16 values.

Hexadecimal is mainly used in computer systems for memory addresses or color codes.

```python
a = 0xABC  # hexadecimal for 2748
```

---

### 5. Mathematical Operations

Basic arithmetic operations use `+`, `-`, `*`, and `/`.

```python
a = 1  
b = 2

# Addition
print(a + b)  # 3

# Subtraction
print(a - b)  # -1

# Multiplication
print(a * b)  # 2

# Division
print(a / b)  # 0.5
```

---

### 6. Exponentiation

The `**` operator is used for exponentiation.

```python
a = 2  
b = 4  
print(a ** b)  # 16
```

---

### 7. Modulo and Floor Division

**Modulo `%`**  
Returns the remainder of a division.

```python
# Remainder of 7 divided by 3
print(7 % 3)  # 1
```

**Floor Division `//`**  
Returns the integer part of the division, discarding the decimal part.

```python
# Quotient of 7 divided by 3
print(7 // 3)  # 2
```
