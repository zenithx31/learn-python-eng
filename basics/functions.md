# Python Input and Output - Functions

## 📚 Why Use Functions?

- To group repetitive code into a single block for efficient reuse  
- To make the program flow clearer and easier to understand

---

## 📚 Basic Structure of a Function

```python
def function_name(parameters):
    statement 1
    statement 2
    ...
```

- Use the `def` keyword to define a function.  
- Parameters are the values passed into the function when it runs.  
- Use `return` to return a value from the function.

### Example: Function that adds two numbers

```python
def add(a, b):
    return a + b
```

---

## 📚 Parameters and Arguments

- Parameter: The variable that receives input inside the function  
- Argument: The actual value passed to the function when calling it

### Example

```python
def add(a, b):  # a and b are parameters
    return a + b

print(add(3, 4))  # 3 and 4 are arguments
```

**Output**

```
7
```

---

## 📚 Functions with Input Values (Typical Functions)

When you pass arguments to a function, it calculates and returns a result.

```python
def add(a, b):
    result = a + b
    return result

a = add(3, 4)
print(a)
```

**Output**

```
7
```

---

## 📚 Functions without Input Values

If no input is given, the function may either perform no operation or return `None`.

```python
def say_hello():
    print("Hello!")

say_hello()
```

**Output**

```
Hello!
```

---

## 📚 Unknown Number of Inputs (*args)

Using `*` before a parameter collects multiple arguments into a tuple.

```python
def add(*args):
    result = 0
    for i in args:
        result += i
    return result

print(add(1, 2, 3))         # 6
print(add(1, 2, 3, 4, 5))   # 15
```

---

## 📚 Keyword Arguments (**kwargs)

Using `**` before a parameter collects keyword arguments into a dictionary.

```python
def print_kwargs(**kwargs):
    print(kwargs)

print_kwargs(a=1)  
# {'a': 1}

print_kwargs(name="Alice", age=25)  
# {'name': 'Alice', 'age': 25}
```

---

## 📚 Calling Functions with Named Parameters

You can specify parameters by name when calling a function, ignoring their order.

```python
def add(a, b):
    return a + b

result = add(b=2, a=1)
print(result)  # 3
```

---

## 📚 The `global` Keyword (Using Global Variables)

To modify a variable outside the function inside the function, use the `global` keyword.

```python
a = 1

def test():
    global a  # Use the global variable a
    a += 1

test()
print(a)  # 2
```

- Using `global` is generally discouraged; it’s better to use return values.

---

## 📚 Lambda (Creating Simple Functions)

`lambda` is used to create one-line anonymous functions.

```python
add = lambda a, b: a + b

print(add(3, 4))  # 7
```

Equivalent normal function:

```python
def add(a, b):
    return a + b
```

- `lambda` is useful for simple, short operations.
