# Predicting house prices in Surrey British Columbia, Canada
### Overview:
- Scraped web data from zillow to acquire house prices and other information
- Constructed a linear regression model in order to predict house prices in Surrey, British Columbia based on variables
- Developed a simple Tkinter application from a linear regression model.

### Tools used:
- **Python**: 3.10.1
- **Packages**: pandas, numpy, tkinter, seaborn, matplotlib, pickle, statistics, os
- **Scraper**: https://chrome.google.com/webstore/detail/instant-data-scraper/ofaokhiedipichpaobibbnahnkdoiiah

###  Introduction: 
The lower mainland of British Columbia, Canada has one of the most expensive real estate prices in the country. In particular, the City of Surrey has been experiencing rapid population growth over the past decade. As someone who is born and raised here and a prospective real estate investor, I was curious of the trends in the Surrey real estate market. Therefore, I decided to investigate further by developing a calculator based on machine learning models. 

**Task**: The task for this project was to predict the price of a house given square footage, bed, and baths.


### Methods:

### Cleaning:
Data was scraped by using a Chrome webscraper found [here](https://chrome.google.com/webstore/detail/instant-data-scraper/ofaokhiedipichpaobibbnahnkdoiiah). I particularly was intereseted in how square footage, number of beds, and baths affect the price of a piece of real estate therefore, I scraped those particulars. Unfortunately, I had some troubles getting large amounts of data so my dataset was only constrained to about 114 entries. Upon scraping and saving it to an excel file, I loaded it into Jupyter. I had to format the strings of the `list-card-price` column to a format where it is convertible to an integer in order to build a machine learning model and made a new `price` column. Null values were dropped. The first 5 rows are shown here after.

![image](https://user-images.githubusercontent.com/72810148/146697633-d231cce6-ff32-4807-8d2a-0cfe99e5182e.png)

Upon cleaning and formatting the required values to an integer format, the finalized dataset is shown here
![image](https://user-images.githubusercontent.com/72810148/146697866-0044867a-ac11-4490-9977-d0e582e2f52e.png)

where `price` is the total price of the property, `sqft` is the number of square footage in that particular property, `bds` is the number of beds, and `ba` as the number of baths in the property. Further detail on the dataset cleaning process can be found under the `clean` branch.

### Exploratory Visualization

# Skills Acquired
- Cleaning Raw data from scraped website
- Formatting strings to numbers 
- Setting custom tick labels
