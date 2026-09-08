# Exp 7 CRUD Operations on Products Collection using MongoDB

**Date:**

## AIM:

To implement **CRUD (Create, Read, Update, and Delete) Operations using MongoDB** on a Products collection to store, retrieve, modify, and delete product information.

## DESIGN STEPS:

### Step 1:

Fork the given repository and clone the forked repository from GitHub.

### Step 2:

Open **MongoDB Shell (mongosh)** or MongoDB Compass and create a database for storing product information.

### Step 3:

Create a collection named **Products** with the fields **id, name, brand, price, category, stock,** and **tags**.

### Step 4:

Insert the following product records into the Products collection.

| id | name       | brand    | price | category    | stock | tags                       |
| -- | ---------- | -------- | ----: | ----------- | ----: | -------------------------- |
| 1  | Laptop     | Dell     | 55000 | Electronics |    30 | ["computer", "technology"] |
| 2  | Smartphone | Samsung  | 30000 | Electronics |    50 | ["mobile", "android"]      |
| 3  | Headphones | Sony     |  2500 | Accessories |   100 | ["audio", "music"]         |
| 4  | Smartwatch | Apple    | 45000 | Electronics |    20 | ["wearable", "ios"]        |
| 5  | Keyboard   | Logitech |  1200 | Accessories |    80 | ["computer", "typing"]     |

### Step 5:

Perform the **Create operation** by inserting all the given product documents into the Products collection.

### Step 6:

Perform the **Read operation** to display all the documents available in the Products collection.

### Step 7:

Retrieve products based on conditions such as **product ID, category, price, brand, stock,** and **tags**.

### Step 8:

Perform the **Update operation** to modify selected product information such as **price, stock,** or **tags**.

### Step 9:

Perform an update operation on multiple documents belonging to a particular product category.

### Step 10:

Perform the **Delete operation** to remove a selected product document from the Products collection.

### Step 11:

Display the final Products collection and verify the changes made through the CRUD operations.

### Step 12:

Execute all the MongoDB commands, capture the required outputs, commit the completed experiment, and push the changes to the forked GitHub repository.

## PROGRAM:
a) Stock Market Prediction using Linear Regression : To predict future stock prices using machine learning regression techniques.
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score

data = pd.read_csv("stock_data_big.csv")

print(data.head())

X = data[["Open", "High", "Low", "Volume"]]
y = data["Close"]

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

model = LinearRegression()
model.fit(X_train, y_train)

predictions = model.predict(X_test)

print("\nMean Squared Error:", mean_squared_error(y_test, predictions))
print("R2 Score:", r2_score(y_test, predictions))

plt.figure(figsize=(8,5))
plt.plot(y_test.values[:50], label='Actual Prices', color='blue')
plt.plot(predictions[:50], label='Predicted Prices', color='red')
plt.title("Stock Price Prediction (Actual vs Predicted)")
plt.xlabel("Time")
plt.ylabel("Stock Close Price")
plt.legend()
plt.show()
```
b) Real-Time Sentiment Analysis of Tweets: Perform real-time sentiment analysis on user-provided text data (tweets or reviews).
```

import pandas as pd
from textblob import TextBlob
import matplotlib.pyplot as plt

data = pd.read_csv("tweets_big.csv")

def get_sentiment(text):
    analysis = TextBlob(str(text))
    if analysis.sentiment.polarity > 0:
        return "Positive"
    elif analysis.sentiment.polarity < 0:
        return "Negative"
    else:
        return "Neutral"


data["Sentiment"] = data["text"].apply(get_sentiment)

sentiment_counts = data["Sentiment"].value_counts()
print(sentiment_counts)

plt.figure(figsize=(6,4))
sentiment_counts.plot(kind='bar', color=['green','red','gray'])
plt.title("Sentiment Analysis Results")
plt.xlabel("Sentiment Type")
plt.ylabel("Number of Tweets/Reviews")
plt.show()

print("\nSample Results:")
print(data[["text", "Sentiment"]].head())
```
##output:
```
```
a) Stock Market Prediction using Linear Regression : To predict future stock prices using machine learning regression techniques.
```
```
<img width="878" height="657" alt="645886570-af295af6-4d49-4943-85d8-6cbbb96acf15" src="https://github.com/user-attachments/assets/f55f4cd7-f93c-4cda-9f30-7a32ae292751" />
```
```
b) Real-Time Sentiment Analysis of Tweets: Perform real-time sentiment analysis on user-provided text data (tweets or reviews).
```
```
<img width="737" height="652" alt="645886417-e3f524ba-4914-44f4-8515-7de366410c79" src="https://github.com/user-attachments/assets/d9e5c604-3b2b-48a8-8ed9-39b50881e89f" />
```
```
##RESULT:
The Stock Market Prediction using Linear Regression and Real-Time Sentiment Analysis of Tweets were implemented successfully. The Linear Regression model was used to predict stock prices using historical stock market data, while the sentiment analysis system successfully analyzed user-provided tweets or reviews and classified them as Positive, Negative, or Neutral.

