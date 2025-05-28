# Python Control Flow - while Statement

## 📚 Basics of while Loop

Loops are used to execute the same block of code repeatedly.  
Among them, the `while` loop continues as long as a given condition is `True`.

---

## 📚 Basic Structure of while Loop

```python
while condition:
    statement 1
    statement 2
    statement 3
    ...
```

- The code block inside the `while` loop runs repeatedly as long as the condition is `True`.
- The loop stops when the condition becomes `False`.

**Example**

```python
count = 0  # initialize variable

while count < 5:  # execute while count is less than 5
    print("Looping:", count)
    count += 1  # increment count
```

**Output**

```
Looping: 0  
Looping: 1  
Looping: 2  
Looping: 3  
Looping: 4  
```

After the 5th iteration, `count` becomes 5, the condition becomes `False`, and the loop ends.

---

## 📚 Force Stop with break Statement

The `break` statement is used to forcibly exit a `while` loop.

**Example**

```python
num = 1

while num <= 10:
    print(num)
    
    if num == 5:  # exit loop when num is 5
        break
    
    num += 1
```

**Output**

```
1  
2  
3  
4  
5
```

The loop terminates when `num` becomes 5 and `break` is executed.

---

## 📚 Skip Current Iteration with continue Statement

The `continue` statement skips the current iteration and proceeds to the next one.

**Example**

```python
num = 0

while num < 5:
    num += 1
    
    if num == 3:  # skip printing when num is 3
        continue

    print(num)
```

**Output**

```
1  
2  
4  
5
```

The value 3 is skipped due to the `continue` statement.

---

## 📚 Prevent Infinite Loops

When using `while` loops, always ensure that an end condition will eventually be met.  
If the condition remains `True` forever, an infinite loop will occur.

**Incorrect Example (Infinite Loop)**

```python
num = 0

while num < 5:
    print("Infinite loop!")
```

- Since `num` never changes, the loop runs endlessly.

**Correct Example**

```python
num = 0

while num < 5:
    print("Looping:", num)
    num += 1  # update to eventually end the loop
```
