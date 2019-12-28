---
published: true
title: "Disaster Response Pipeline Project"
date: 2019-12-28
categories:
  -
  -
---

Disaster Response Pipeline Project
==================================

[![Adithya Balaji](https://miro.medium.com/fit/c/96/96/1*Kfv4bEfT1WkjRVjmTFI49A@2x.jpeg)](https://medium.com/@adibrao?source=post_page-----1010a60c6e95----------------------)[Adithya Balaji](https://medium.com/@adibrao?source=post_page-----1010a60c6e95----------------------)Follow[Jun 7](https://medium.com/@adibrao/disaster-response-pipeline-project-1010a60c6e95?source=post_page-----1010a60c6e95----------------------) · 2 min read

<img class="cp t u fz ak" src="https://miro.medium.com/max/2560/1\*JsPapspi5t5ti2y8NWjb1A.jpeg" width="1280" height="720" role="presentation"/>

This project includes a web app where an emergency worker can input a new message and get classification results in several categories. The web app will also display visualizations of the data. This project is to analyze disaster data from Figure Eight to build a model for an API that classifies disaster messages. Visit [https://github.com/adithyab94/Disaster-Response-Pipeline-Project](https://github.com/adithyab94/Disaster-Response-Pipeline-Project) to access the project

File Description
================

```
.  
├── app       
│   ├── run.py                           # Flask file that runs app  
│   └── templates     
│       ├── go.html                      # Classification result page of web app  
│       └── master.html                  # Main page of web app      
├── data                     
│   ├── disaster\_categories.csv          # Dataset including all the categories    
│   ├── disaster\_messages.csv            # Dataset including all the messages  
│   └── process\_data.py                  # Data cleaning  
├── models  
│   └── train\_classifier.py              # Train ML model             
└── README.md
```

The Project contains three components mainly,

1\. ETL Pipeline
================

Python script, `process_data.py`,

*   Loads the `messages` and `categories` datasets
*   Merges the two datasets
*   Cleans the data
*   Stores it in a SQLite database

2\. ML Pipeline
===============

Python script, `train_classifier.py`,

*   Loads data from the SQLite database
*   Splits the dataset into training and test sets
*   Builds a text processing and machine learning pipeline
*   Trains and tunes a model using GridSearchCV
*   Outputs results on the test set
*   Exports the final model as a pickle file

3\. Flask Web App
=================

Outputs the classification according to the input

Example
=======

Type in: We have a lot of problem at Delma 75 Avenue Albert Jode, those people need water and food.

<img class="cp t u fz ak" src="https://miro.medium.com/max/6720/1\*hC2pcz\_nqc9EuYxoXi6Y3w.png" width="3360" height="4138" role="presentation"/>

Instructions to run the project: (Run run.py directly if DisasterResponse.db and claasifier.pkl already exist.)
===============================================================================================================

1.  Run the following commands in the project’s root directory to set up your database and model.

*   To run ETL pipeline that cleans data and stores in database `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
*   To run ML pipeline that trains classifier and saves `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2\. Run the following command in the app’s directory to run your web app. `python run.py`

3\. Go to [http://0.0.0.0:3001/](http://0.0.0.0:3001/)