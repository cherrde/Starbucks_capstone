# Starbucks Capstone
## Project Overview:
### Overview and Problem statement:
#### What question are we asking?
What types of offers are most successful and will drive more business and what features will drive successful offers?

So a two fold question:
- Which offers are the most successful
- Which features lead to successful offers?

Why are these questions important? The first will allow us to target the types of offers that are most likely to be successful and generate revenue based on that. The second question will allow us to target those offers to those most likely to participate and again, generate revenue.
## Project Statement / Metrics:
We're going to use accuracy and fscore for our measures. Accuracy, of course is good since it high accuracy means it is easy to pinpoint predictions that will be successful. But more importantly we are also using fscore since we are concerned with recall and precision. F1 is a weighted average of the precision and recall so if one or the other gets out of balance this helps keep our predictions on track. I will compare those scores, after we have some naive predictions with three more classifiers to get a good solid base to work from.
### Models to Try
We're going to compare three classifying models, SVC, KNeighbors and a Bagging Classifier. We'll train on three different amounts of the data (1%, 10% and all) we'll compare accuracy and f-scores to see which models seem the best for us.
Data Exploration and Analysis, visualizations
## Results Summary:
I started out with two main questions "What types of offers are most successful and will drive more business and what features will drive successful offers?" To get a better understanding of that we reviewed the data, manipulated and visualized it in a few different ways. We combined it and formatted it then created a solid feature set. We were able to view that data and determine a few different offers that tended to be successful (discount_10_10_2, discount 7_7_3 and bogo_5_5_5 and bogo 5_7_5). We created some visualizations of the demographics for those offers, but it wasn't very helpful.

We then we modeled a few different classifiers to find the a good solid model that would predict at a high level (around 80% for our Bagging Classifier) then used that model to determine the features that would be most important using feature_importances_ (age, time, reward, difficulty and duration).
## File List:
README.md - a markdown file containing this information
Starbucks_Capstone_Notebook.ipynb - a Jupyter Notebooks with calculations, models and visualizations
Starbucks_Capstone_Notebook.html - an html file saved from the Jupyter notebooks
## Installation:
None
## Acknowledgements:
A thanks to Udacity, the Mentor program and previous projects. Specifically code was reused from the visuals.py python script in the Arvato Project from Intro to Machine Learning, as well as Project 1 for this module.
