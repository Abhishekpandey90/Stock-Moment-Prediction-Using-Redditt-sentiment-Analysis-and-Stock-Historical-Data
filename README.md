
# Stock Movement Prediction using Reddit Sentiment & Historic Data Analysis

This project aims to predict stock price movements by analyzing sentiment from Reddit discussions. The workflow involves scraping data from specific subreddits related to stock market discussions, processing and feature extraction, and then applying machine learning models to predict stock trends.

## Table of Contents
1. [Introduction](#introduction)
2. [Data Collection](#data-collection)
3. [Data Preprocessing](#data-preprocessing)
4. [Feature Extraction](#feature-extraction)
5. [Model Training and Evaluation](#model-training-and-evaluation)
6. [Performance Comparison](#performance-comparison)
7. [Installation](#installation)
8. [Usage](#usage)
9. [Results](#results)


## Introduction
This project utilizes sentiment analysis from user-generated content on Reddit to predict stock movements. By combining natural language processing (NLP) with machine learning techniques, it aims to forecast stock price trends based on social sentiment.

## Data Collection
Data is scraped from Reddit using the `asyncpraw` library:
- Subreddits focused on stock discussions are targeted.
- Both post titles and comments are collected.
- Relevant features such as post score, number of comments, and upvote ratio are extracted.
- Timestamps are converted to a readable format for time-series analysis.

## Data Preprocessing
The scraped data undergoes preprocessing:
- Text cleaning is performed to remove noise.
- Sentiment analysis using the VADER sentiment analyzer assigns a sentiment score to each post.
- Posts are categorized as positive, negative, or neutral based on their sentiment scores.

## Feature Extraction
Daily aggregation of features is performed to create a time-series dataset:
- Features such as average sentiment score, sum of scores, and daily post count are computed.
- Data is aligned with stock price data to prepare for modeling.

## Model Training and Evaluation
Three models are used for predicting stock movements:
1. **Random Forest**: A tree-based ensemble method that uses aggregated features.
2. **XGBoost**: Another tree-based model that utilizes gradient boosting techniques.
3. **LSTM**: A deep learning model that captures sequential dependencies in the time-series data.

The LSTM model is trained over 20 epochs, with accuracy and loss recorded at each epoch.

## Performance Comparison
Plots are generated to compare the models:
- Line plots for accuracy of Random Forest, XGBoost, and LSTM.
- Loss curve for the LSTM model over training epochs.

## Installation
To run the project, you'll need Python 3.x and the following packages:
- `asyncpraw`
- `pandas`
- `numpy`
- `matplotlib`
- `scikit-learn`
- `xgboost`
- `tensorflow`
- `vaderSentiment`

Install the packages using:
```bash
pip install asyncpraw pandas numpy matplotlib scikit-learn xgboost tensorflow vaderSentiment
```

## Usage
1. Clone the repository:
    ```bash
    git clone https://github.com/Abhishekpandey/stock-prediction-reddit.git
    ```


## Results
The project compares the predictive capabilities of Random Forest, XGBoost, and LSTM:
- Accuracy and loss metrics for each model are visualized.
- LSTM showed gradual improvement in loss, indicating effective training.
