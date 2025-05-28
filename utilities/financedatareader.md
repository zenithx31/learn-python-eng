# How to Fetch Financial Data Using the FinanceDataReader Library

---

## 📚 What is FinanceDataReader?

FinanceDataReader is a Python library designed to help you easily collect and analyze financial data.  
It provides access to a wide variety of data including Korean stock prices, US stock prices, cryptocurrency prices, commodity futures prices, various indices, exchange rates, and stock listings.

> **Note:** This library primarily focuses on Korean financial data but also supports major global markets including the US and other international exchanges.

---

## 📚 Installation

Before installing FinanceDataReader, make sure you have Python and pip installed on your system.  
Then, run the following command to install the library:

~~~bash
$ pip install -U finance-datareader
~~~

---

## 📚 How to Retrieve Stock Listings

### 1. Retrieve all stocks listed on the Korea Exchange (KRX)

~~~python
import FinanceDataReader as fdr

df_sample = fdr.StockListing('KRX')
print(df_sample)
~~~

~~~
       Code        ISU_CD      Name  ...           Marcap      Stocks MarketId
0     005930  KR7005930003      Samsung Electronics  ...  417884778500000  5969782550      STK
1     373220  KR7373220003  LG Energy Solution  ...  100503000000000   234000000      STK
2     000660  KR7000660001    SK Hynix  ...   92747501301000   728002365      STK
3     207940  KR7207940008  Samsung Biologics  ...   51957020000000    71174000      STK
4     005935  KR7005931001     Samsung Electronics Preferred  ...   46575387220000   822886700      STK
...      ...           ...       ...  ...              ...         ...      ...
2764  245450  KR7245450002    CNS Link  ...       2678032200     1579960      KNX
2765  308700  KR7308700004       TechEn  ...       2560000000     4000000      KNX
2766  288490  KR7288490006     NaraSoft  ...       2466219285    43267005      KNX
2767  217320  KR7217320001       SunTech  ...       2420250000     1050000      KNX
2768  322190  KR7322190000        Bern  ...       1017472458     8925197      KNX

[2769 rows x 17 columns]
~~~

---

### 2. Retrieve data for a specific stock (e.g., Samsung Electronics)

~~~python
import FinanceDataReader as fdr

# Samsung Electronics, from 2023 to present
df_sample1 = fdr.DataReader(symbol='005930', start='2023')

# Samsung Electronics, from January 1, 2023 to October 31, 2023
df_sample2 = fdr.DataReader(symbol='005930', start='20230101', end='20231031')

# Samsung Electronics, from IPO date to present
df_sample3 = fdr.DataReader(symbol='005930')

print(df_sample1.head())
print(df_sample2.head())
print(df_sample3.head())
~~~

~~~
           Open   High    Low  Close    Volume    Change
Date                                                      
2023-01-02  55500  56100  55200  55500  10031448  0.003617
2023-01-03  55400  56000  54500  55400  13547030 -0.001802
2023-01-04  55700  58000  55600  57800  20188071  0.043321
2023-01-05  58200  58800  57600  58200  15682826  0.006920
2023-01-06  58300  59400  57900  59000  17334989  0.013746

           Open   High    Low  Close    Volume    Change
Date                                                      
2023-01-02  55500  56100  55200  55500  10031448  0.003617
2023-01-03  55400  56000  54500  55400  13547030 -0.001802
2023-01-04  55700  58000  55600  57800  20188071  0.043321
2023-01-05  58200  58800  57600  58200  15682826  0.006920
2023-01-06  58300  59400  57900  59000  17334989  0.013746

       Open  High   Low  Close   Volume    Change
Date                                                  
1999-07-23  3400  3400  3000   3120  1180685       NaN
1999-07-26  3120  3260  3060   3170  1212761  0.016026
1999-07-27  3229  3399  3200   3370   910512  0.063091
1999-07-28  3409  3750  3390   3560  1952152  0.056380
1999-07-29  3699  3960  3570   3940  1661889  0.106742
~~~

---

### 3. Retrieve the list of stocks in the US S&P 500 index

~~~python
import FinanceDataReader as fdr

df_sp500 = fdr.StockListing('S&P500')
print(df_sp500)
~~~

~~~
     Code         ISU_CD              Name             ...        Marcap          Stocks  MarketId
0    0001Z     US0378331005      Apple Inc.       ...   2535210000000   16500000000   NYSE
1    0002Y     US5949181045      Microsoft Corp.  ...   2171400000000   7460000000    NASDAQ
2    0003X     US0231351067      Amazon.com Inc.   ...   1576450000000   5120000000    NASDAQ
3    0004W     US0378331005      Tesla, Inc.       ...   1162100000000   1540000000    NASDAQ
4    0005V     US68389X1054      Meta Platforms    ...    920000000000   2435000000    NASDAQ
...   ...           ...                   ...    ...         ...              ...   ...

[500 rows x 17 columns]
~~~

---

### 4. Visualize stock price data with a graph (e.g., Samsung Electronics)

~~~python
import FinanceDataReader as fdr
import matplotlib.pyplot as plt

df_sample = fdr.DataReader(symbol='005930')  # Samsung Electronics

df_sample['Close'].plot()
plt.show()
~~~

---

## 📚 Overview of Functions

- **StockListing()**: Returns the list of stocks for specified exchanges  
  - Korea Exchange: 'KRX', 'KOSPI', 'KOSDAQ', 'KONEX', 'KRX-DELISTING', 'KRX-ADMINSTRATIVE'  
  - US Exchanges: 'NASDAQ', 'NYSE', 'AMEX', 'S&P500'  
  - Global Exchanges: 'SSE', 'SZSE', 'HKEX', 'TSE', 'HOSE', etc.

- **DataReader()**: Returns price data for specified symbols  
  - Domestic stocks: e.g., '005930', '000660', '068270'  
  - Foreign stocks: e.g., 'AAPL', 'AMZN', 'GOOG'  
  - Domestic indices: 'KS11', 'KQ11', 'KS200'  
  - US indices: 'DJI', 'IXIC', 'US500', 'RUT', 'VIX'  
  - Exchange rates (supports 'KRW', 'EUR', 'CNY', 'JPY', 'CHF'): e.g., 'USD/KRW', 'USD/EUR', 'CNY/KRW', 'EUR/CNY'  
  - Cryptocurrencies (supports 'BTC', 'ETH', 'USDT', 'BNB', 'USDC', 'XRP', 'BUSD', 'ADA', 'SOL', 'DOGE'): e.g., 'BTC/USD', 'BTC/KRW', 'ETH/USD', 'ETH/KRW'  
  - Commodity futures: 'CL=F', 'BZ=F', 'NG=F', 'GC=F', 'SI=F', 'HG=F'  
  - Others: 'ETF/KR', 'US5YT', etc.

---

## 📚 More Information

For more detailed information about the FinanceDataReader library, please visit the following links:

- [FinanceDataReader User Guide](https://financedata.github.io/posts/finance-data-reader-users-guide.html)  
- [FinanceDataReader API Documentation](https://github.com/FinanceData/FinanceDataReader/wiki/)
