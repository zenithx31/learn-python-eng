# Python Control Statements – `for` Loop

## 📚 Basic Structure of a `for` Loop

The `for` loop is used to iterate over a sequence such as a list, tuple, or string.

```python
for variable in iterable:
    code_to_execute
```

- It takes each element from the iterable and assigns it to the variable, then executes the code block repeatedly.

### Example 1: Iterating over a list

```python
a = [1, 2, 3]

for i in a:
    print(i)
```

**Output**

```
1  
2  
3
```

---

### Example 2: Using a tuple

```python
a = [(1, 2), (3, 4), (5, 6)]

for (first, last) in a:
    print(first + last)
```

**Output**

```
3  
7  
11
```

- Each tuple in the list is unpacked into two variables and used in the loop.

---

## 📚 `continue` (Skip Current Iteration)

The `continue` statement skips the current iteration and proceeds to the next one.

```python
a = [1, 2, 3, 4, 5]

for i in a:
    if i % 2 == 0:  # Skip even numbers
        continue
    print(i)
```

**Output**

```
1  
3  
5
```

- Even numbers 2 and 4 are skipped due to `continue`.

---

## 📚 `range()` Function (Generating Number Sequences)

The `range()` function generates a sequence of numbers.

### Example 1: Sum from 1 to 10

```python
num = 0

for i in range(1, 11):  # 1 to 10 (11 is not included)
    num += i

print(num)
```

**Output**

```
55
```

- `range(start, end+1)` is used. The `end` value is exclusive.

---

### Example 2: Loop from 0 to 4

```python
for i in range(5):  # Defaults to starting at 0
    print(i)
```

**Output**

```
0  
1  
2  
3  
4
```

---

### Example 3: Print even numbers using `range()`

```python
for i in range(2, 11, 2):  # Start at 2, end before 11, step by 2
    print(i)
```

**Output**

```
2  
4  
6  
8  
10
```

---

## 📚 List Comprehension (Create Simple Lists)

List comprehension is a concise way to create new lists using a `for` loop in a single line.

### Example 1: Create a list by multiplying each element by 3

```python
a = [1, 2, 3]

result = [num * 3 for num in a]

print(result)
```

**Output**

```
[3, 6, 9]
```

- Useful for transforming or generating new lists.

---

### Example 2: Create a list of even numbers only

```python
numbers = [1, 2, 3, 4, 5, 6]
even_numbers = [num for num in numbers if num % 2 == 0]

print(even_numbers)
```

**Output**

```
[2, 4, 6]
```

- `if` can be added to include elements that meet a condition.
