# Python Dictionary Types

## 📚 What is a Dictionary?

A dictionary is a data type that stores data as key-value pairs.  
Unlike lists or tuples, which use an index to access data, dictionaries use keys to store and retrieve values.

```python
# Examples of dictionary creation
a = {'name': 'Alice', 'age': 25, 'city': 'Seoul'}
b = {1: 'one', 2: 'two', 3: 'three'}
c = {'fruits': ['apple', 'banana', 'cherry']}  # Values can be lists
```

---

## 📚 Adding Items to a Dictionary

To add a new key-value pair, use the syntax: dictionary[new_key] = value.

```python
a = {1: 'a'}
a[2] = 'b'  # Add a new item

print(a)  # {1: 'a', 2: 'b'}
```

---

## 📚 Deleting Items from a Dictionary

Use `del` to remove a key-value pair by key.

```python
a = {1: 'a', 2: 'b'}
del a[1]  # Delete key 1

print(a)  # {2: 'b'}
```

---

## 📚 Accessing Values Using Keys

You can get values by their keys.

1) Using the key directly

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a['a'])  # 1
print(a['c'])  # 3
```

Note: Accessing a non-existent key this way will cause an error.

2) Using the `get()` method

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.get('a'))  # 1
print(a.get('c'))  # 3
print(a.get('d'))  # None (returns None instead of error)
```

`get()` is safer since it doesn't raise an error if the key is missing.

---

## 📚 Getting a List of Keys

Use `keys()` to get all keys in a dictionary.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.keys())  # dict_keys(['a', 'b', 'c'])
```

To convert to a list, use `list(a.keys())`.

---

## 📚 Checking if a Key Exists

Use the `in` operator to check if a key exists in a dictionary.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print('b' in a)  # True
print('d' in a)  # False
```

---

## 📚 Getting a List of Values

Use `values()` to get all values in a dictionary.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.values())  # dict_values([1, 2, 3])
```

To convert to a list, use `list(a.values())`.

---

## 📚 Getting Key-Value Pairs

Use `items()` to get key-value pairs as tuples.

```python
a = {'a': 1, 'b': 2, 'c': 3}

print(a.items())  # dict_items([('a', 1), ('b', 2), ('c', 3)])
```

You can iterate through keys and values easily with a `for` loop.

```python
for key, value in a.items():
    print(f'Key: {key}, Value: {value}')
```

# Output

```
Key: a, Value: 1
Key: b, Value: 2
Key: c, Value: 3
```

---

## 📚 Clearing a Dictionary

To remove all items from a dictionary, use `clear()`.

```python
a = {'a': 1, 'b': 2, 'c': 3}

a.clear()
print(a)  # {}
```
