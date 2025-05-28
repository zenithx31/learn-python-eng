# How to Scrape Telegram Chatrooms Using the Telethon Library

## 📚 What is Telethon?

Telethon is a Telegram API client library written in Python.  
It allows direct communication with Telegram servers to automate various tasks such as sending and receiving messages, managing chatrooms, and more.  
It supports asynchronous (async) operations, making it efficient for handling large volumes of data.

---

## 📚 Obtaining Telegram API ID and Hash

To get a Telegram API ID and Hash, you must have a Telegram account. If you do, you can obtain them from the link below:

https://my.telegram.org/auth?to=apps

---

## 📚 Example: Scraping Telegram Chatrooms

To use Telethon, you need to have Python and pip installed first.

Then install the required libraries with the following commands:

~~~bash
pip install pandas
pip install telethon
~~~

~~~python
import pandas as pd
from telethon import TelegramClient

# Enter your issued API ID, hash, and the chat link you want to scrape.
name = 'test'
api_id = '<api_id>'
api_hash = '<api_hash>'
chat = '<chat_link>'

data = []

# Connect to the Telegram server
async def some_function():
    async with TelegramClient(name, api_id, api_hash) as client:
        async for message in client.iter_messages(chat):
            data.append([message.sender_id, message.text])

df = pd.DataFrame(data, columns=['SENDER', 'MESSAGE'])
df.to_csv('test.csv', encoding='utf-8')
~~~

Using the example code above, you can asynchronously fetch messages one by one from the specified Telegram chatroom.

The fetched messages are saved as a DataFrame and exported to a CSV file using the `to_csv()` function.
