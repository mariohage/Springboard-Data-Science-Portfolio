
# Is there any correlation between Stock Prices and their mentions/sentiment on Reddit.com/r/wallstreetbets?

Quick answer: No, however after having completed this project, there is a correlation between volume of trading and comment counts on reddits (verifying the obvious.)

## Data

Reddit comments data was sourced from reddit.com/r/wallstreetbets using a custom built web scraper built on the reddit PRAW crawler: https://praw.readthedocs.io/en/latest/index.html

Stock Price data was sourced using the yfinance API: https://algotrading101.com/learn/yahoo-finance-api-guide/

## Method

The scraper was ran on an Amazon EC2 server 24/7, and the script would store scraped comment data into an AWS Relational Database. I did this so to safeguard the data that was collected, and to be able to connect to the DB from any machine.

## Cleaning

Fitlering of comments with a length of > 150 characters
Groupbys/Merging of data between Stock Prices dataset and Reddit Comments Data

## Model

I used the ProsusAI/finbert model from the HuggingFace Transformers library: https://huggingface.co/ProsusAI/finbert

## Model Results

Ultimately there was no correlation between Stock Prices and Comment Sentiment/count/volume:

![alt text](https://imgur.com/a/Ce7llvi)
