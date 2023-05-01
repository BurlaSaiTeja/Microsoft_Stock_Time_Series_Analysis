# Microsoft_Stock_Time_Series_Analysis

### Information:
----------------

INFO-I 535 - Management, Access, and Use Of Big and Complex Data<br>
Course Project: Big Data Concepts<br>
Name: Sai Teja Burla

### Problem Statement:
----------------------

This project is made to perform basic Time Series Analysis on Microsoft Stock Dataset to predict stock prices for future based on the historical stock price values. Implementation of the entire pipeline was done on Jetstream2 VM. MongoDB was installed to ingest and store the dataset which I took from kaggle. Jupyter Notebook was installed to implement the main model pipeline. I had implemented two different pipelines one that made use of Pandas and Statsmodels libraries and th eother that made use of PySpark and Prophet libraries.

### Dataset:
------------

The Microsoft stock dataset is structures as follows:
- Date - The corresponding date of a certain stock price in the format ‘mm/dd/yyyy 16:00:00’
- Open - Opening price of the stock in decimals
- Close - Closing price of the stock in decimals
- High - Highest price of the stock in the day in decimals
- Low - Lowest price of the stock in the day in decimals
- Volume - Number of shares traded in the day in numbers

### Requirements:
-----------------

To run this project we need to have the following libraries:
- Python 3.x - Used as the base language to implement the project
- Pandas and Numpy - For preprocessing and analysis
- Pymongo - To import data from MongoDB
- Matplotlib, Plotly, Seaborn - Data visualization purpose
- Statsmodels, Prophet - For implementing the main model
- PySpark - For implementing a model using distributed computing

### Implementation Steps:
-------------------------

- Imported all the required libraries
- Connected to MongoDB using the pymongo library and get the data and store it in a dataframe
- Preprocessed the ‘Date’ column from object to datetime datatype with the format ‘YYYY-MM-DD’ for further use
- Checked if there were any missing values in the dataset which there weren't any in this case
- Checked for any outliers in the data using a boxplot 
- Plotted a few visualizations to gain insights into the data this includes a correlation heatmap as well
- Preparing the data for time series analysis by only keeping ‘Date’ and ‘Close’ columns and making the ‘Date’ column as the index
- Performed Augmented Dickey Fuller test 
- Plotted the Decomposition plots to check if the data had any trend and seasonality in it
- Plotted ACF and PACF plots for finding the hyperparameter values for our time series models
- Split the data into train and test and plotted this in the same graph
- Implemented ARIMA, SARIMAX, Prophet models for predicting Close price values on the test data
- Plotted graphs and calculated MSE value for checking weather the predicted values are accurate or not and to what rate are they accurate

### Results:
------------

Based on the prediction graphs and MSE values I concluded that ARIMA model performs the best with an MSE value of 19.68 as compared to the other two models that I had implemented.


