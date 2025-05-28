# Python Set Types

## 📚 What is a Set?

A set is an unordered collection of unique elements.  
This means that even if there are duplicate values, they are automatically removed, and you cannot access elements by index like in lists or tuples.

- Characteristics of sets:  
1) No order (unordered)  
2) No duplicates allowed  
3) No indexing access  
4) Easy to perform operations like intersection, union, and difference

---

## 📚 Creating a Set

You can create a set using the `set()` function.

```python
# Creating a set from a list
a = set([1, 2, 3])
print(a)  # {1, 2, 3}

# Creating a set from a string
b = set("Hello")
print(b)  # {'H', 'e', 'l', 'o'}

# Creating an empty set (Note: {} creates an empty dictionary, not a set)
c = set()
print(c)  # set()
```

---

## 📚 Set Indexing

Sets do not support indexing because they are unordered.  
However, you can convert a set to a list or tuple to use indexing.

```python
# Convert to list and then index
a = set([1, 2, 3])
list_a = list(a)
print(list_a)    # e.g. [1, 2, 3] (order may vary)
print(list_a[1])  # 2 (output can vary each run)

# Convert to tuple and then index
tuple_a = tuple(a)
print(tuple_a)    # e.g. (1, 2, 3)
print(tuple_a[1])  # 2
```

---

## 📚 Set Operations

Sets allow easy calculation of intersection, union, and difference.

- Intersection  
Returns elements common to both sets.

```python
a = set([1, 2, 3, 4])
b = set([3, 4, 5, 6])

# Method 1: Using & operator
print(a & b)  # {3, 4}

# Method 2: Using intersection() method
print(a.intersection(b))  # {3, 4}
```

- Union  
Returns all elements from both sets, excluding duplicates.

```python
# Method 1: Using | operator
print(a | b)  # {1, 2, 3, 4, 5, 6}

# Method 2: Using union() method
print(a.union(b))  # {1, 2, 3, 4, 5, 6}
```

- Difference  
Returns elements in the first set that are not in the second set.

```python
# Method 1: Using - operator
print(a - b)  # {1, 2}

# Method 2: Using difference() method
print(a.difference(b))  # {1, 2}
```

---

## 📚 Adding and Removing Elements in a Set

- Add a single element (add)  
Use `add()` to add one element to a set.

```python
a = set([1, 2, 3])
a.add(4)
print(a)  # {1, 2, 3, 4}
```

- Add multiple elements at once (update)  
Use `update()` to add multiple elements to a set.

```python
a.update([4, 5])
print(a)  # {1, 2, 3, 4, 5}
```

- Remove an element (remove)  
Use `remove()` to delete a specific element.

```python
a.remove(2)
print(a)  # {1, 3}
```
