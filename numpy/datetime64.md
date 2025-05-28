# Working with datetime64 Date and Time Functions

## 📚 What is datetime64?

`datetime64` is a data type in Numpy designed for high-resolution handling of dates and times.  
It allows us to represent and calculate dates and times in various units (e.g., year, month, day, second, millisecond, etc.).

By default, `datetime64` can represent time down to the attosecond (10^-18 seconds), whereas Python's standard `datetime` module only supports up to microseconds (10^-6 seconds). This makes Numpy’s `datetime64` capable of much more precise time handling.

---

## 📚 Creating Dates Using Numpy Objects

You can create dates or times using Numpy’s `datetime64` objects.  
Dates and times can be specified with different units.

~~~
import numpy as np

example1 = np.datetime64('2023-11-08')  # Create date '2023-11-08'
example2 = np.datetime64(100000, 'ns')  # 100,000 nanoseconds
example3 = np.datetime64(100000, 's')   # 100,000 seconds
example4 = np.datetime64(100000, 'D')   # 100,000 days

print(example1)  # Output: 2023-11-08
print(example2)  # Output: 1970-01-01T00:00:00.000100000 (Epoch reference: 1970-01-01)
print(example3)  # Output: 1970-01-02T03:46:40
print(example4)  # Output: 2243-10-17
~~~

- `example1`: Creates the date 2023-11-08.  
- `example2`: Creates a timestamp 100,000 nanoseconds after the epoch (1970-01-01 00:00:00).  
- `example3`: Represents 100,000 seconds after the epoch, which is 1970-01-02 03:46:40.  
- `example4`: Represents 100,000 days after the epoch, which corresponds to October 17, 2243.  

---

## 📚 Creating Dates Using Numpy’s array() Function

You can create arrays with `datetime64` data type in Numpy.  
When creating dates as arrays, you can specify the unit such as year, month, or day.

~~~
import numpy as np

example1 = np.array('2023-11-08', dtype='datetime64')     # Default date
example2 = np.array('2023-11-08', dtype='datetime64[D]')  # Day unit
example3 = np.array('2023-11-08', dtype='datetime64[M]')  # Month unit
example4 = np.array('2023-11-08', dtype='datetime64[Y]')  # Year unit

print(example1)  # Output: 2023-11-08
print(example2)  # Output: 2023-11-08
print(example3)  # Output: 2023-11
print(example4)  # Output: 2023
~~~

- `example1`: Basic date format.  
- `example2`: Specified with 'D' (day) unit; date is unchanged.  
- `example3`: Specified with 'M' (month) unit; shows only year and month.  
- `example4`: Specified with 'Y' (year) unit; shows only the year.  

---

## 📚 Creating Date Ranges with arange()

You can use `np.arange()` to create date ranges with specific intervals.  
You can also specify the date unit.

~~~
import numpy as np

example1 = np.arange('2023-10', '2023-11', dtype='datetime64[D]')  # Day unit
example2 = np.arange('2023-10', '2023-11', dtype='datetime64[W]')  # Week unit
example3 = np.arange('2023-10', '2023-11', dtype='datetime64[M]')  # Month unit
example4 = np.arange('2022-10', '2023-11', dtype='datetime64[Y]')  # Year unit
example5 = np.arange('2023-11-07', '2023-11-08', dtype='datetime64[h]')  # Hour unit
example6 = np.arange('2023-11-07', '2023-11-08', dtype='datetime64[m]')  # Minute unit
example7 = np.arange('2023-11-07', '2023-11-08', dtype='datetime64[s]')  # Second unit

print(example1)
print(example2)
print(example3)
print(example4)
print(example5)
print(example6)
print(example7)
~~~

- `example1`: Generates daily dates from October 1 to October 31, 2023.  
- `example2`: Generates weekly dates from September 28 to October 19, 2023.  
- `example3`: Generates monthly dates for October 2023.  
- `example4`: Generates yearly dates from October 2022 to November 2023.  
- `example5`: Generates hourly times from November 7 to November 8, 2023.  
- `example6`: Generates minute-level times from November 7 to November 8, 2023.  
- `example7`: Generates second-level times from November 7 to November 8, 2023.  

---

## 📚 Calculating Differences Between Dates

You can subtract one `datetime64` object from another to calculate the difference between two dates.  
The result is returned as a timedelta-like object.

~~~
import numpy as np

example = np.datetime64('2023-11') - np.datetime64('2023-01')
print(example)  # Output: 10 months
~~~

The difference between the two dates is shown as `10 months`.  
`datetime64` supports calculating differences in units like years, months, and days.
