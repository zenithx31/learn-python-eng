# Python File Input and Output - Reading and Writing Files

## 📚 Creating a File

First, let’s learn how to create a new file in Python.

### 1) Creating a New File

~~~python
# Create a new file named new.txt
f = open("new.txt", 'w')  # 'w' mode opens the file for writing and creates the file if it doesn't exist.
f.close()
~~~

The above code opens a file named `new.txt` in write mode. If the file doesn’t exist, it will be created automatically.  
After finishing the operation, you should close the file with `close()`.

### 2) Creating a File in a Specific Directory

~~~python
f = open("C:/user/new.txt", 'w')
f.close()
~~~

This code creates a file named `new.txt` inside the `C:/user/` directory.

---

## 📚 File Opening Modes

There are several modes for opening files, depending on how you want to handle the file.

- `'r'` : Read mode (raises an error if the file does not exist)  
- `'w'` : Write mode (creates a new file if it doesn’t exist, or overwrites if it does)  
- `'a'` : Append mode (creates a new file if it doesn’t exist, or appends to the end if it does)  
- `'b'` : Binary mode (used for reading/writing binary files)  

---

## 📚 Writing to a File

Use write mode (`'w'`) when you want to write data to a file.

~~~python
f = open("C:/user/new.txt", 'w')
for i in range(0, 5):
    data = "%dth line.\n" % i
    f.write(data)
f.close()
~~~

This writes 5 lines to `new.txt`. The `write()` function records the string to the file.

---

## 📚 Reading from a File

There are multiple ways to read data from a file using Python.  
You can use `read()`, `readline()`, and `readlines()` functions.

### 1) Using `read()` Function

Reads the entire content of the file.

~~~python
f = open("C:/user/new.txt", 'r')
data = f.read()
print(data)
f.close()
~~~

### 2) Using `readline()` Function

Reads one line at a time. Each call reads the next line in the file.

~~~python
f = open("C:/user/new.txt", 'r')
line = f.readline()  # Reads only the first line
print(line)
f.close()
~~~

### 3) Reading All Lines Using `readline()` with a Loop

Use a `while` loop to read all lines one by one.

~~~python
f = open("C:/user/new.txt", 'r')
while True:
    line = f.readline()
    if not line:
        break
    print(line)
f.close()
~~~

### 4) Using `readlines()` Function

Reads all lines and returns them as a list.

~~~python
f = open("C:/user/new.txt", 'r')
lines = f.readlines()
for line in lines:
    print(line)
f.close()
~~~

### 5) Using a `for` Loop to Read a File

You can iterate directly over the file object, which is simpler and similar to `readlines()`.

~~~python
f = open("C:/user/new.txt", 'r')
for line in f:
    print(line)
f.close()
~~~

---

## 📚 Appending Content to a File

If you use write mode (`'w'`), the existing content will be overwritten.  
To add content without deleting existing data, use append mode (`'a'`).

~~~python
f = open("C:/user/new.txt", 'a')
for i in range(11, 15):
    data = "%dth line.\n" % i
    f.write(data)
f.close()
~~~

This adds new lines to the existing `new.txt` file.

---

## 📚 Using `with` Statement for File Handling

You must close files after finishing operations, but the `with` statement automatically closes the file for you, making your code safer and cleaner.

~~~python
with open("new.txt", 'w') as f:
    f.write("Hello World")
~~~

Using `with` ensures the file is closed automatically when the block is exited, so no need to call `close()` manually.
