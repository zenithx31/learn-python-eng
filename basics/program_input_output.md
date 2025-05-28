# Python Input and Output - Program Input and Output

## 📚 Handling Command Line Arguments with sys.argv

`sys.argv` is a way in Python to receive arguments from the command line when running a program.  
It is mainly used when running scripts so users can pass values to the program, which the program then processes.

---

## 📚 Example

```python
# example.py
import sys

args = sys.argv[1:]  # Slice from [1:] to skip the script name and get only the arguments
for i in args:
    print(i.upper(), end=' ')
```

---

## 📚 Explanation

1) `import sys`  
   Imports the sys module.  
   `sys.argv` allows the program to access arguments passed when the program is run.

2) `args = sys.argv[1:]`  
   `sys.argv` stores all command-line inputs as a list.  
   Since `sys.argv[0]` is always the script name, we slice with `[1:]` to get only the actual arguments.

3) `for i in args:`  
   Loops through each value stored in the `args` list.

4) `print(i.upper(), end=' ')`  
   Converts each argument to uppercase using the `upper()` method, and prints it with a space after instead of a newline.  
   By default, `print()` ends with a newline, but `end=' '` allows multiple values to print on the same line separated by spaces.

---

## 📚 How to Run

Save this code as `example.py` and run it in the command line (terminal or command prompt):

```
C:\user> python example.py hello world
```

**Output**

```
HELLO WORLD
```

Here, `hello` and `world` are the arguments input after the command, and the program receives these arguments, converts them to uppercase, and prints them.
