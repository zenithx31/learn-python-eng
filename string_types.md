# Python String Types

## 📚 String Types

---

### 1. Defining Strings

Strings in Python are enclosed in either single quotes `'` or double quotes `"`.  
You can define multi-line strings using triple quotes (`'''` or `"""`).

```python
# String with double quotes
a = "Hello World!"

# String with single quotes
b = 'Hello World!'

# Multi-line string (with triple double quotes)
c = """Hello
World!"""

# Multi-line string (with triple single quotes)
d = '''Hello
World!'''
```

---

### 2. Using Backslashes (`\`) in Strings

To include quotes within a string, use a backslash (`\`) to escape special characters.

```python
# Double quotes inside single quotes
a = "Life is too short. You need 'Python'."

# Single quotes inside double quotes
b = 'Life is too short. You need "Python".'

# Escaping single quotes
c = 'Life is too short. You need \'Python\'.'
```

---

### 3. Escape Codes

Escape codes allow special behavior within strings.

- `\n`: New line  
- `\t`: Tab space  
- `\\`: Literal backslash `\`  
- `\'`: Literal single quote  
- `\"`: Literal double quote  

```python
# New line
a = "Life is too short.\nYou need Python."
print(a)

# Tab space
b = "Life is too short.\tYou need Python."
print(b)

# Backslash
c = "This is a backslash: \\"
print(c)

# Quotes
d = "He said, \"Python is great!\""
print(d)
```

---

### 4. String Operations

Strings can be combined or repeated using various operations.

#### 1) String Addition (`+`)

```python
a = "Life is"
b = " too short."
print(a + b)  # "Life is too short."
```

#### 2) String Multiplication (`*`)

```python
a = "Life"
print(a * 2)  # "LifeLife"
```

#### 3) Getting String Length (`len()`)

```python
a = "Life is too short."
print(len(a))  # 17
```

---

### 5. String Indexing and Slicing

#### 1) String Indexing

You can retrieve specific characters in a string using indexing.  
Index starts at 0, and negative indexes read from the end.

```python
a = "Life is too short"
print(a[3])   # 'e'
print(a[-1])  # 't'
```

#### 2) String Slicing

You can extract parts of a string using slicing.

```python
a = "Life is too short"
print(a[0:4])  # "Life"
```

---

### 6. String Formatting

You can insert variables into strings using formatting.

#### 1) `%` Formatting

```python
a = 5
b = "five"
print("I eat %d apples." % a)
print("I eat %s apples." % b)
```

#### 2) `.format()` Method

```python
a = 5
b = "five"
print("I ate {0} apples for {1} days.".format(a, b))
```

#### 3) f-Strings (Python 3.6+)

```python
a = 'John'
b = 20
print(f"My name is {a}. I am {b} years old.")
```

---

### 7. String Built-in Functions

#### 1) Counting Characters (`count`)

```python
a = "Happy"
print(a.count("p"))  # 2
```

#### 2) Finding Character Position (`find`, `index`)

```python
a = "Life is too short"
print(a.find('e'))  # 3
```

#### 3) Replacing Strings (`replace`)

```python
a = "Life is too short"
print(a.replace("short", "long"))  # Life is too long
```

#### 4) Splitting Strings (`split`)

```python
a = "Life is too short"
print(a.split())  # ['Life', 'is', 'too', 'short']

b = "a/b/c/d"
print(b.split('/'))  # ['a', 'b', 'c', 'd']
```
