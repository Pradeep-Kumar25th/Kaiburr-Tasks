## Consumer Complaints Text Classification 
This repository contains Python code for a text classification project that uses a Multinomial Naive Bayes classifier to categorize consumer complaints based on their text descriptions. The code is designed to work with the Consumer Complaints Database provided by the Consumer Financial Protection Bureau (CFPB).

## Introduction
The purpose of this code is to demonstrate how to build a text classification model using the Multinomial Naive Bayes algorithm. The model is trained to predict the product category associated with consumer complaints based on the narrative text provided by consumers.

## Prerequisites

Python (3.x recommended)
Pandas
Scikit-learn (sklearn)

## Data Preparation
The code loads the consumer complaints dataset from the Consumer Financial Protection Bureau (CFPB) using the following URL: https://catalog.data.gov/dataset/consumer-complaint-database. This dataset contains information about consumer complaints, including the complaint narrative and the associated product category.

## Text Preprocessing
Before training the model, the code performs the following text preprocessing steps:

Handling missing values in the 'Consumer complaint narrative' column by replacing them with empty strings.
Splitting the data into training and testing sets using a 80-20 split ratio.
Text vectorization using TF-IDF (Term Frequency-Inverse Document Frequency) to convert the complaint text into numerical features that can be used by the model.
## Model Training
The code trains a Multinomial Naive Bayes classifier using the TF-IDF transformed training data. The classifier is used to predict the product categories for the test data.

## Model Evaluation
After training the model, the code evaluates its performance by generating a classification report, which includes metrics such as precision, recall, and F1-score for each product category. The zero_division parameter is set to 1 to handle cases where there are no true positives for a category.

## Making Predictions
The code also demonstrates how to make predictions using the trained model. You can provide a new complaint text as input, and the model will predict the associated product category.

![WebUiForms](screenshots/task4WebUIForm.png)
Copy code
new_complaint = ["This is a new complaint text."]
new_complaint_tfidf = tfidf_vectorizer.transform(new_complaint)
predicted_category = classifier.predict(new_complaint_tfidf)
print("Predicted Category:", predicted_category[0])


![Screenshot of code](screenshots/Task 6 ss3.png)


