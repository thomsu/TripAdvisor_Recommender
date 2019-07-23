# TripAdvisor Recommender for European Cities

### Table of Contents
* [project objective](#project-objective)
* [technologies](#technologies)
* [file descriptions](#file-descriptions)
* [step one: collecting data](#step-one:-collecting-data)
* [step two: data cleaning](#step-two:-data-cleaning)
* [step three: data exploration](#step-three:-data-exploration)
* [step four: model building](#step-four:-model-building)


### Project Objective
This is an individual project for the data science immersive program at Flatiron School. The main project goals are to scrape data from a popular hotel website like TripAdvisor, use it to explore the different recommender algorithms in the Surprise library and to select the best one of these models.

### Technologies
This project is created in Jupyter notebook using mainly:
* Python version: 3.7.1
* BeautifulSoup4 version: 4.6.3
* Requests version: 2.19.1
* Selenium version: 3.141.0
* Urllib3 version: 1.24.1
* Pandas version: 0.23.4
* Numpy version: 1.15.4
* Matplotlib version: 3.0.2
* Seaborn version: 0.9.0
* Surprise version: 1.0.6

### File Descriptions

The files included in this repository are:

*Top_Predictions -- This file which is in pickle format, contains the top 10 recommendations for hotels in the grouped_combined_reviews.

*TripAdvisor Recommender.ipynb -- Jupyter notebook with the codes to scrape and parsed data from TripAdvisor website. It also contain algorithm for feature engineering, data exploration and most important, modelling of recommender system using Surprise library.

*tripadvisor_data.csv -- This file contains hotel information from the Tripadvisor hotel listing by city. The information is scraped using the process_hotel_list function found in the Jupyter notebook.

*tripadvisor_hotel.txt -- This information of this file is scraped from each individual hotel's Tripadvisor details webpage using process_hotel_details function. It contains more information than Tripadvisor hotel listing by city.

*tripadvisor_hotel.json -- This file contains all hotel details that will be used in the recommender function. It is derived from the tripadvisor_hotel.txt.

*tripadvisor_hotel_review.csv -- This file contains all the users' hotel reviews of hotels from any of the 16 European cities. The process_other_reviews function is used to scrape the details from website.

*tripadvisor_reviewer.csv -- This file contains reviewers information from TripAdvisor's hotel details webpage. Each reviewer is screened so that details of reviewers who have written more than 25 reviews at TripAdvisor are included in this file.

### Step One: Collecting Data

All of the data are scraped from TripAdvisor website. The data contains information of 16 European cities, London, Paris, Rome, Barcelona, Berlin, Vienna, Prague, Budapest, Florence, Milan, Madrid, Lisbon, Edinburgh, Amsterdam and Brussels for the travel period from July 1, 2019 to July 15, 2019. This search parameters gives a general picture of the room rate variations during the peak of travel season. The information was scraped with 4 sets of functions and saved in 4 different files. One of those functions, 'process_other_reviews', utilize Selenium to automate the data gathering process. Be sure to install the correct version of Chromedriver from (https://sites.google.com/a/chromium.org/chromedriver/downloads) before using this function to scrape data.

### Step Two: Data Cleaning

Most of the data did not go through any processing as the data were 'selectively processed' in data collection. Due to the wide range of nightly room rates, the price was transformed with a logarithmic function. Hotels with a rating of below 3 were dropped as the plan is to create a model that only suggests decent or better hotels. Some of the data like hotel address and amenities needed separated in different columns for readability.

### Step Three: Data Exploration

Although this process does not seem necessary for building a recommender system, having an EDA may reveal some patterns and insights of hotels in the data. There are 4 histograms, each showing a different aspect of the data. One of the most interesting discoveries from these plots is that the nightly rates variation of hotels with the same rating are most distinguished with rating 4.5 and 5. The rates are generally much higher for hotels in this group that have 15 or more deals being offered.  

### Step Four: Model Building

Using the Surprise library, a benchmark with 11 different recommender algorithms was created. The top 4 models were then selected and grid searches were performed on one each of them to get the optimum parameters. The second best model, SVD, was ultimately chosen as it is very close to the best, SVDpp, but it is much less expensive.
