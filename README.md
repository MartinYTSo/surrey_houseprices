# Predicting house prices in Surrey British Columbia, Canada
### Overview:
- Scraped web data from zillow to acquire house prices and other information
- Constructed a linear regression model in order to predict house prices in Surrey, British Columbia based on variables
- Developed a simple Tkinter application from a linear regression model.
### Final Product: 
![image](https://user-images.githubusercontent.com/72810148/146699212-ab73556d-a11f-46b0-8d99-5cfdc34d6d94.png)

### How to Run:
Clone this repository and run all cells in the `main.ipynb` file under the `main` branch.

### Tools used:
- **Python**: 3.10.1
- **Packages**: pandas, numpy, tkinter, seaborn, matplotlib, pickle, statistics, os
- **Scraper**: https://chrome.google.com/webstore/detail/instant-data-scraper/ofaokhiedipichpaobibbnahnkdoiiah

###  Introduction: 
The lower mainland of British Columbia, Canada has one of the most expensive real estate prices in the country. In particular, the City of Surrey has been experiencing rapid population growth over the past decade. As someone who is born and raised here and a prospective real estate investor, I was curious of the trends in the Surrey real estate market. Therefore, I decided to investigate further by developing a calculator based on machine learning models. 

**Task**: The task for this project was to predict the price of a house given square footage, bed, and baths.

### Cleaning:
Data was scraped by using a Chrome webscraper found [here](https://chrome.google.com/webstore/detail/instant-data-scraper/ofaokhiedipichpaobibbnahnkdoiiah). I particularly was intereseted in how square footage, number of beds, and baths affect the price of a piece of real estate therefore, I scraped those particulars. Unfortunately, I had some troubles getting large amounts of data so my dataset was only constrained to about 114 entries. Upon scraping and saving it to an excel file, I loaded it into Jupyter. I had to format the strings of the `list-card-price` column to a format where it is convertible to an integer in order to build a machine learning model and made a new `price` column. Null values were dropped. The first 5 rows are shown here after.

![image](https://user-images.githubusercontent.com/72810148/146697633-d231cce6-ff32-4807-8d2a-0cfe99e5182e.png)

Upon cleaning and formatting the required values to an integer format, the finalized dataset is shown here
![image](https://user-images.githubusercontent.com/72810148/146697866-0044867a-ac11-4490-9977-d0e582e2f52e.png)

where `price` is the total price of the property, `sqft` is the number of square footage in that particular property, `bds` is the number of beds, and `ba` as the number of baths in the property. Further detail on the dataset cleaning process can be found by viewing the `data_clean.ipynb` under the `clean` branch.

### Exploratory Visualization
The next step in my workflow was to conduct an exploratory visual analysis. The visualization of the clean dataset is as shown here:

![image](https://user-images.githubusercontent.com/72810148/146698020-801f35e6-b4e9-4b4a-bd3c-b4f62c2c840d.png)

It is immediately noted that I saw a relationship between square footage `sqft` and price `price`. 
![image](https://user-images.githubusercontent.com/72810148/146698178-bb5f0a14-42a5-4891-b8a8-1a7eb0b946ab.png)

Therefore, I focused on building a linear regression model to uncover the relationship between price and square feet. A linear regression model was built based on those two variables.

### Linear Regression Model.
The result of the simple linear regression model based `sqft` and `price` is shown in the image below
![image](https://user-images.githubusercontent.com/72810148/146698329-3a816b5a-3d20-4bda-b0e1-c5f004091816.png)

The linear regression model that I built using only `sqft` and `price` had very low R^2 score around 0.003. In order to improve this, I suggested to myself to take into account the remaining variable such as the number of beds and baths and constructed a multivariable linear regression. This resulted to an increase in the R^2 score ranging around 0.36. Although it was a slight improvement, it did not satisfy an adequate R^2 square score of 0.7 which is commonly acceptable in the [finance](https://www.investopedia.com/terms/r/r-squared.asp#:~:text=In%20other%20fields%2C%20the%20standards,would%20show%20a%20low%20correlation.) realm.

A few thought provoking suggestions on why R^2 is low:
- I did not take into accounts of other variables such as property taxes, condominium fees, utility fees, etc. that may affect the result of the R^2 model
-  Foreign investment has been artificially driving prices high in British Columbia for the past years by buying unused property. This may not have to with housing at all but, outside behaviour of buyers and sellers.

Nevertheles, to keep things simple, as well as my limited knowledge of machine learning to only classification, regression, and clustering, I decided to utilize the multivariable linear regression to build my GUI application. 

Further detail on the analysis process can be found by viewing the `analysis.ipynb` file under the branch clean.

### GUI App
For the last step in my pipeline, I constructed a simple GUI app with the `tkinter` library. I imported my regression model via utilizing the `pickle` library. The final product is meant to act as a "calculator" of the selections that were chosen by the user.

Further detail on the GUI development can be found in the `GUI.ipynb` file under the branch `model_gui`




# Skills Acquired
- Cleaning Raw data from scraped website
- Formatting strings to numbers 
- Setting custom tick labels
