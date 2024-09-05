# Predicting Churn for Sparkify - Capstone Project

This repository includes the files that resulted from the Capstone project for the Udacity's Data Science Nanodegree - Predicting churn for Sparkify.

## Project Motivation

Customer churn is a problem that affects companies in a variety of industries. When a client departs, there is a significant loss to the company. Determining which consumers are most likely to cancel a service subscription based on how they use it is what customer churn prediction is. It identifies which customers are at a high risk of canceling their subscriptions or abandoning the product. Churn prediction allows us to tell whether a customer will leave and why. Data scientists and analysts regularly encounter predicting churn rates in any customer-facing business, and it is a challenging and common problem. 
In this project, I predicted churn for a fictional music streaming company, Sparkify. I used realistic datasets with Spark to engineer relevant features for predicting churn and Spark MLlib to build a machine learning model with large datasets, far beyond what could be done with non-distributed technologies like scikit-learn. 
Udacity provided the project data in the Udacity Spark course. The original dataset was 12 Gb. In this project, a small part of the dataset, 128Mb, was used in a local environment. The project was also developed on an IBM Watson Studio using a medium-size dataset (236Mb).

## Libraries
The main libraries used in the project included:
- spark-0.2.1 ,
- pyspark-3.5.2,
- findspark-2.0.1 
- numpy-2.1.1, 
- pandas-2.2.2 
- matplotlib-3.9.2.

## Files

The files in this repository are the results of this project and include:

- SparkifyNotebook_Local.ipynb: The notebook where the churn prediction was developed on the local environment.
- SparkifyNotebook_IBMWS.ipynb: The notebook where the churn prediction was developed on an IBM Watson Studio project.
- CapstoneProject_Report.pdf: The detailed technical report of the project.
- predictions.csv: Churn predictions in CSV format for the best model obtained in the local environment.
- mini_sparkify_event_data.json: the small database used in the local project
- medium-sparkify-event-data.json: the medium database used in the local project

## Summary of the results

Given the multiclassification setting of this project, with a churn variable predicting cancelation and downgrade, the algorithms used in the spark environment were Logistic Regression, assumed as a benchmark Decision Tree, Random Forest, and Multilayer Perceptron Classifier. Each of these algorithms was introduced in a pipeline and the spark CrossValidator was used to tune the hyperparameters selected for each and cross-validate the data three times. The best model observed in this analysis was a Decision Tree model with an F1-score of 0.96. The Logistic Regression and Multilayer Perceptron Classifier were the worst prediction-scoring models. 
To evaluate whether the model generalizes well to unseen data, considering already the best parameters obtained from the cross-validation, a sensitivity analysis in the local session was developed, due to time constraints in the standard session. The test set size was varied and the difference was observed in the f1-score to see the robustness of the model to data variations. The fact that the bets model was the decision tree in both the local and IBM Watson Studion project indicate  differences were small and show the robustness of the model with varying dataset compositions with a very high prediction score. A CSV with the predictions obtained in the local session was also obtained.

## Acknowledgments

I would like to thank Udacity for making the data accessible and providing support for the spark session both on a local environment and on IBM Watson Studio.




