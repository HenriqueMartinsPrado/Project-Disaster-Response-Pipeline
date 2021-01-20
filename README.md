## PROJECT DISASTER RESPONSE PIPELINE
### Table of Contents
1. [Project Motivation](#motivation) 
2. [File Descriptions](#files) 
3. [How to Interact with my project / Results](#results) 
4. [Licensing, Authors, and Acknowledgements](#licensing)

## 1. Project Motivation<a name="motivation"></a>
<p align="justify">The motivation for developing this project was to analyze disaster data offered by the Figure Eight data set. In this data set, real messages sent during disaster events were found. Thus, using this data set, a machine learning pipeline was created so that it was possible to send the messages to an appropriate disaster relief agency.</p>

## 2. File Descriptions<a name="files"></a>
    .
    ├── app     
    │   ├── run.py                           # Flask file to execute the web app
    │   └── templates   
    │       ├── go.html                      # HTML that shows the results of classification task
    │       └── master.html                  # HTML Featured as main page   	
    ├── data                   
    │   ├── disaster_categories.csv          # Data in CSV format composed of categories  
    │   ├── disaster_messages.csv            # Data in CSV format composed os messages
    │   └── process_data.py                  # Data Wrangling
    ├── models
    │   └── train_classifier.py              # ML Model Used for Training
		
<p align="justify">Just to highlight, the following import libraries were used in the project:</p>

	import pandas as pd
	import numpy as np
	import json

	from nltk.stem import WordNetLemmatizer
	from nltk.tokenize import word_tokenize

	from flask import Flask
	from flask import render_template, request, jsonify

	import plotly
	from plotly.graph_objs import Bar
	from sklearn.externals import joblib
	from sqlalchemy import create_engine

## 3. How to Interact with my project / Results<a name="results"></a>

Instructions:

1. Run the following commands in the project's root directory to set up your database and model.	
	To run ETL pipeline that cleans data and stores in database: 
		python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db
	
	To run ML pipeline that trains classifier and saves: 
		python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl

2. Run the following command in the app's directory to run your web app. 
		python run.py

3. Go to http://0.0.0.0:3001/ or http://localhost:3001/

## 4. Licensing, Authors, Acknowledgements, etc.<a name="licensing"></a>
<ul> <li><p align="justify">Book: Hands-On Machine Learning with Scikit-Learn and TensorFlow Concepts, Tools, and Techniques to Build Intelligent Systems-O’Reilly Media</p> <li><p 
	align="justify">https://www.kaggle.com/hassanamin/customer-churn</p>
</ul>
