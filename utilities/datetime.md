# How to Work with Dates and Times Using the datetime Library in Python

## 📚 What is datetime?

The datetime module is a standard Python library that provides various functions to handle dates and times.  
It is especially useful for processing time series data or performing time-related calculations.

- **time**: A class for handling time  
  Represents a specific time of day including hours, minutes, seconds, and microseconds.

- **date**: A class for handling dates  
  Represents year, month, and day, and is used for operations or comparisons involving specific dates.

- **datetime**: A class that includes both date and time  
  Contains year, month, day, as well as hour, minute, second, and microsecond, useful when dealing with both date and time simultaneously.

---

## 📚 Data Type Conversion (string ↔ datetime)

1. **Converting a string to datetime**

~~~python
import datetime

datetime_str = '2023-11-08 16:00:00'
format = '%Y-%m-%d %H:%M:%S'
datetime_dt = datetime.datetime.strptime(datetime_str, format)
print(datetime_dt)
print(type(datetime_dt))
# Output:
# 2023-11-08 16:00:00
# <class 'datetime.datetime'>
~~~

2. **Converting datetime to string**

~~~python
import datetime

datetime_str = '2023-11-08 16:00:00'
format = '%Y-%m-%d %H:%M:%S'
datetime_dt = datetime.datetime.strptime(datetime_str, format)

datetime_str = datetime_dt.strftime('%Y-%m-%d %H:%M:%S')
print(datetime_str)
print(type(datetime_str))
# Output:
# 2023-11-08 16:00:00
# <class 'str'>
~~~
