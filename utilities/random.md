# How to Generate Random Numbers Using the `random` Module

## 📚 What is a Random Number?

A random number is a value that cannot be predicted in advance. It’s widely used in games, simulations, cryptography, and more.  
In Python, you can generate random numbers using the `random` module.

---

## 1. How to Generate a Float Between 0 and 1

The function `random.random()` returns a random floating-point number between 0 and 1.

~~~
import random

print(random.random())
# Example output
# > 0.5744194603677023
~~~

This value changes every time you run the code, so you get a different number on each execution.

---

## 2. How to Generate a Random Integer Within a Range

The function `random.randint(a, b)` returns a random integer between `a` and `b` (both inclusive).  
That means the generated number can be equal to either `a` or `b`.

~~~
import random

# Generate a random integer between 1 and 100
print(random.randint(1, 100))

# Example output
# > 51
~~~

Calling `random.randint(1, 100)` will generate an integer somewhere between 1 and 100, including both endpoints.

---

## 📚 How to Use Handy Random Functions

Besides basic random number generation, Python’s `random` module offers convenient functions for selecting or shuffling items in a list, sampling, and more.

---

### How to Select a Random Item

The function `random.choice()` picks one random element from a given list or tuple.

~~~
import random

# List of items to choose from
chars = ['a', 'b', 'c']

# Select a random element from the list
print(random.choice(chars))
# Example output
# > c
~~~

Here, `random.choice(chars)` selects one random element from the `chars` list.  
The output can vary each time you run it.

---

### How to Shuffle a List with `random.shuffle()`

The function `random.shuffle()` randomly rearranges the elements of a list.

~~~
import random

# List to shuffle
chars = ['a', 'b', 'c']

# Shuffle the list
random.shuffle(chars)

# Print the shuffled list
print(chars)
# Example output
# > ['b', 'a', 'c']
~~~

In this example, `random.shuffle(chars)` randomly rearranges the items in the list.  
The result will likely be different every time you run it.

---

### How to Select a Random Item Again with `random.choice()`

`random.choice()` picks one random element from a list or tuple.

~~~
import random

chars = ['a', 'b', 'c']

print(random.choice(chars))
# Example output
# > c
~~~

The selected item will vary each time the code runs.

---

### How to Sample Without Replacement Using `random.sample()`

The function `random.sample()` selects a specified number of unique items from a list without duplicates.

~~~
import random

# List to sample from
chars = ['a', 'b', 'c']

# Select 2 random samples
print(random.sample(chars, 2))
# Example output
# > ['c', 'b']
~~~

Here, `random.sample(chars, 2)` returns a new list containing 2 unique elements randomly chosen from `chars`.  
No duplicates will appear in the sampled list.
