# BTC Twitter Sentiment and Price Movement
by Colton Manning

In this project, I attempt to predict the next-day price movement of bitcoin.  I walk through my entire process from cleaning the data to building a logistic regression classifier.  I did most of the data cleaning in python and a little in sqlite.  I used R for all of the model building.

My motivation for doing this project was out of a general interest for cryptocurrencies and to serve as a learning experience.  Cryptocurrencies are extremely volatile.  This is what makes people love crypto as well as what terrifies people about crypto.  The huge volatility in the markets sets up a high-risk high-reward setting.  If someone were able to predict the markets, thereby mitigating this high-risk, the payoff could be immense.  

While working on this project, I was not expecting to build a model that would be useful.  There are entire corporations that dedicate a vast amount of resources for predicting the markets.  Even with all those resources, it is still quite difficult to make sense of bitcoin's volatility.  There was no way I could compete, but nonetheless, I really enjoyed the overall learning process.  

I decided to focus on bitcoin twitter sentiment for price prediction after seeing firsthand just how impactful market sentiment can be...especially in the crypto world.  Back in May of 2021, a single tweet from Elon Musk sent the entire crypto market in a downward spiral.  This event, and the negative sentiment that followed, inspired me to work on this project.  There are **many** other factors, than sentiment alone, that affect bitcoin pricing.  Therefore, the best case is that my model could explain only a fraction of bitcoin's variance.  However, I hope to improve my model in the future by adding more data/predictors.        

## Data

For this project I used two datasets.   One dataset consists of several bitcoin-related tweets, and another contains BTC pricing historical data.

**Bitcoin Historical Data:**

This dataset consists of the minute-by-minute pricing info for bitcoin from select exchanges.  The data spans from January 2012 to March 2021.  There are a little less than 5 million rows in this dataset.

* Columns:
  * `Timestamp` - This column gives the timestamp in unix time 
  * `Open` - The opening price for the one-minute interval
  * `High` - The maximum price during the one-minute interval
  * `Low` - The minimum price during the one-minute interval
  * `Close` - The closing price for the one-minute interval
  * `Volume_(BTC)` - The trading volume in bitcoin
  * `Volume_(Currency)` - The trading volume in USD
  * `Weighted_Price` - The volume-weighted price of bitcoin

**Bitcoin Tweets:**

This dataset consists of 16 million tweets containing 'Bitcoin' or 'BTC' that were scrapped from the web.

* Columns:
  * `id` - the tweet's id number
  * `user` - the user's twitter handle
  * `fullname` the name of the user
  * `url` - the tweet's url
  * `timestamp` - the time the tweet was created
  * `replies` - the number of replies
  * `likes` - the number of likes
  * `retweets` - the number of retweets
  * `text` - the text content of the tweet

The columns that we are primarily interested in are the `timestamp` and `text` columns

## Packages Used

Python:

* **pandas** - for loading our data into a dataframe for manipulation
* **numpy** - for applying mathematical functions to our dataframes
* **datetime** - for extracting dates from timestamps
* **re** - for regex
* **textblob** - for text sentiment
* **sklearn** - for scaling functions

## Sources:

* **Data**
  * [Bitcoin Historical Data](https://www.kaggle.com/mczielinski/bitcoin-historical-data)
  * [Bitcoin Tweets](https://www.kaggle.com/alaix14/bitcoin-tweets-20160101-to-20190329)

* **Code**
  * [Twitter Sentiment Analysis using Python](https://www.geeksforgeeks.org/twitter-sentiment-analysis-using-python/)
  * [Step by Step: Twitter Sentiment Analysis](https://towardsdatascience.com/step-by-step-twitter-sentiment-analysis-in-python-d6f650ade58d)

