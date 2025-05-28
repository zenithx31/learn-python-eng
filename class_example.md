# How to Write and Use Classes in Python

📚 Basic Structure of a Class

A class is defined using the `class` keyword. Inside a class, you can define attributes (data) and methods (functions).

Example:

~~~python
class ClassName:
    # Constructor definition
    def __init__(self, param1, param2):
        self.attribute1 = param1
        self.attribute2 = param2

    # Method implementation
    def method1(self):
        # Implementation code
        pass

    def method2(self):
        # Implementation code
        pass

# Main code area
# Creating instances
c1 = ClassName(value1_for_c1, value2_for_c1)
c2 = ClassName(value1_for_c2, value2_for_c2)

# Using methods on instances
c1.method1()
c2.method1()

c1.method2()
c2.method2()
~~~

**Explanation**

- `class ClassName`  
  Used to define a class.

- `__init__(self, param1, param2)`  
  Constructor of the class. Automatically called when an object is created. It usually sets the initial state of the object.

- `self.attribute = value`  
  Assigns values to the object’s attributes. `self` refers to the instance of the class.

- Method definition  
  Functions inside a class that define behaviors the object can perform.

- Creating an instance  
  Use `ClassName(param1, param2)` to create an instance of the class.

- Calling a method  
  Use `instance.method()` format to call a method on an object.

---

📚 Practical Example: Children's Height

Example:

~~~python
class Child:
    def __init__(self, name, height):
        self.name = name
        self.height = height

    def getName(self):
        return self.name

    def getHeight(self):
        return self.height

    def growHeight(self, increase):
        before = self.height
        self.height += increase
        print("Height increased from {} to {}".format(before, self.height))

# Creating instances
c1 = Child('Tom', 150)
c2 = Child('Jerry', 100)

# Display current height
print("Current height of {} is {} cm.".format(c1.getName(), c1.getHeight()))
print("Current height of {} is {} cm.".format(c2.getName(), c2.getHeight()))

# Grow taller
c1.growHeight(10)
c2.growHeight(30)

# Display updated height
print("Current height of {} is {} cm.".format(c1.getName(), c1.getHeight()))
print("Current height of {} is {} cm.".format(c2.getName(), c2.getHeight()))
~~~

**Explanation**

- `Child` class  
  A class representing children, with name and height as attributes.

- `__init__` constructor  
  Initializes the child's name and height.

- `getName` method  
  Returns the child’s name.

- `getHeight` method  
  Returns the child’s height.

- `growHeight` method  
  Increases the child’s height by the specified amount and prints the before-and-after heights.

**Output**

```
Current height of Tom is 150 cm.
Current height of Jerry is 100 cm.
Height increased from 150 to 160
Height increased from 100 to 130
Current height of Tom is 160 cm.
Current height of Jerry is 130 cm.
```

The objects `c1` and `c2` are instances of the `Child` class, representing Tom and Jerry. Their heights are printed before and after using the `growHeight()` method.
