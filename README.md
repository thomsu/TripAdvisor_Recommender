# TripAdvisor Recommender for European Cities

### Table of Contents
* [project objective](#project-objective)
* [technologies](#technologies)
* [file descriptions](#file-descriptions)


### Project Objective
This is the individual project for the data science immersive program at Flatiron School. The main project goal is to have a decent algorithm that offer suggestions similar in terms of hotel amenities and room rates based on any given European city hotel, which could be the top pick of a traveller who had stayed before.

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

*TripAdvisor Recommender.ipynb -- Jupyter notebook with the codes to scrape and parsed data from TripAdvisor website. It also contain algorithm for feature engineering, data exploration and most important, modelling of recommender system using Surprise library.

*tripadvisor_data.csv -- This file contains hotel information from the Tripadvisor hotel listing by city. The information is scraped using the process_hotel_list function found in the Jupyter notebook.

*tripadvisor_hotel.txt -- This information of this file is scraped from each individual hotel's Tripadvisor details webpage using process_hotel_details function. It contains more information than Tripadvisor hotel listing by city.

*tripadvisor_hotel.json -- This file contains all hotel details that will be used in the recommender function. It is derived from the tripadvisor_hotel.txt.

*tripadvisor_hotel_review.csv -- This file contains all the users' hotel reviews of hotels from any of the 16 European cities. The process_other_reviews function is used to scrape the details from website.

*tripadvisor_reviewer.csv -- This file contains reviewers information from TripAdvisor's hotel details webpage. Each reviewer is screened so that details of reviewers who have written more than 25 reviews at TripAdvisor are included in this file.

###
