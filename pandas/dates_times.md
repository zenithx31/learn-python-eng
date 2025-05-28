# Working with Dates and Times in Pandas

📚 Handling Dates and Times in Pandas: Timestamp, DatetimeIndex, Period

Pandas offers various functions to work with date and time data.  
Objects like Timestamp, DatetimeIndex, and Period are very useful for processing and analyzing date and time information.
---

📚 Timestamp

A Timestamp represents a single date and time in Pandas.  
It is similar to numpy’s datetime64 but offers more convenient features.
<br>Timestamps can be created with various units and support nanosecond (ns) precision by default.

```python
import pandas as pd

example1 = pd.Timestamp(1234.5678)       # nanoseconds (default)
example2 = pd.Timestamp(1234.5678, unit='D')  # days

print(example1)
print(example2)
# Output
# 1970-01-01 00:00:00.000001234
# 1973-05-19 13:37:37.920000
```

- example1 interprets 1234.5678 as nanoseconds since 1970-01-01.  
- example2 interprets 1234.5678 as days since 1970-01-01.

---

📚 DatetimeIndex

DatetimeIndex is useful when handling multiple dates, allowing you to manage many dates as a single index.

Example 2: Convert single and multiple dates to DatetimeIndex

```python
import pandas as pd

example1 = pd.to_datetime('2023-11-1 12')          # single date
example2 = pd.to_datetime(['2023-1-1', '2023-10-31'])  # multiple dates

print(example1)
print(example2)
# Output
# 2023-11-01 12:00:00
# DatetimeIndex(['2023-01-01', '2023-10-31'], dtype='datetime64[ns]', freq=None)
```

- example1 converts a single date.  
- example2 converts multiple dates into a DatetimeIndex object.

---

Example 3: Automatically generate dates for a specific period

You can create a range of dates between two dates using `pd.date_range()`.

```python
import pandas as pd

example = pd.date_range('2023-1-1', '2023-10-31')
print(example)
# Output (truncated)
# DatetimeIndex(['2023-01-01', '2023-01-02', ..., '2023-10-31'], dtype='datetime64[ns]', length=304, freq='D')
```

- `pd.date_range()` generates all dates between the start and end dates.  
- Here, dates are output with daily frequency (D).

---

📚 Period and PeriodIndex

A Period represents a span of time rather than a specific moment.  
For example, it can represent a month or a year, unlike Timestamp which represents a single point in time.

Example 4: Creating Periods

```python
import pandas as pd

example1 = pd.Period('2023-11-1')           # default daily frequency
example2 = pd.Period('2023-11-1', freq='M')  # monthly frequency
example3 = pd.Period('2023-11-1', freq='Y')  # yearly frequency

print(example1)
print(example2)
print(example3)
print(type(example1))
# Output
# 2023-11-01
# 2023-11
# 2023
# <class 'pandas._libs.tslibs.period.Period'>
```

- example1 treats 2023-11-1 as a daily period.  
- example2 treats it as a monthly period (November 2023).  
- example3 treats it as a yearly period (2023).

---

Example 5: Creating PeriodRanges

You can generate multiple periods using `pd.period_range()`.  
It’s useful for creating a series of Period objects within a specified range or frequency.

```python
import pandas as pd

example1 = pd.period_range('2023-1', '2023-11')             # monthly by default
example2 = pd.period_range('2023-1', '2023-11', freq='M')   # monthly
example3 = pd.period_range('2022-1', '2023-11', freq='Y')   # yearly

print(example1)
print(example2)
print(example3)
print(type(example1))
# Output
# PeriodIndex(['2023-01', '2023-02', ..., '2023-11'], dtype='period[M]', freq='M')
# PeriodIndex(['2023-01', '2023-02', ..., '2023-11'], dtype='period[M]', freq='M')
# PeriodIndex(['2022', '2023'], dtype='period[Y]', freq='Y')
# <class 'pandas._libs.tslibs.period.Period'>
```

- example1 creates monthly periods from January to November 2023.  
- example2 does the same explicitly with freq='M'.  
- example3 creates yearly periods for 2022 and 2023.
