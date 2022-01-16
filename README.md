# Starbucks Capstone
## Project Overview:
For the Starbucks Capstone project we are provided a set of "data that mimics customer behavior on the Starbucks rewards mobile app." This data set comes in three files (noted below in the Files section). Some of the offers in the data are discounts, some are informational and some are buy on get one (bogo) offers. There is additionally data on transactions, persons and information about the offers. The task provided was to cleanse and combine the data set into some useful form and then determine some information about this data.
## Project Statement / Metrics:
### Overview and Problem statement:
#### (i.e.) What question are we asking?
I will focus on two specific questions. What types of offers are most successful and will drive more business and what features will drive successful offers?

So a two fold question:
- Which offers are the most successful
- Which features lead to successful offers?

Why are these questions important? The first will allow us to target the types of offers that are most likely to be successful and generate revenue based on that. The second question will allow us to target those offers to those most likely to participate and again, generate revenue.
### Methodology
My plan is to first cleanse the data and merge it. As I'm not certain what each data set will look like when merged, this may be an iterative process. Then I will review the data and see if I can find which offers tend to be successful and if there are characterizations of those offers in the demographic data. I will use visualizations when possible to help illustrate the data. I will then get information about a basic Naive predictor and calculate the Accuracy and F1 Score for comparison to models I build later.  Why use Accuracy and F1 Score? Accuracy, of course is good since it high accuracy means it is easy to pinpoint predictions that will be successful. Since we're note overly concerned about false positives and false negatives, this will be a good measure. Additionally, I will also use the F1 score since it will provide more information about recall and precision. F1 is a weighted average of the precision and recall so if one or the other gets out of balance this helps keep our predictions on track. I will compare those scores with three more classifiers to get a good solid base to work from.
### Models to Try
The data we have is categorical. Using the following link (https://scikit-learn.org/stable/tutorial/machine_learning_map/index.html) I reviewed which model might make the most sense. I decided on the following three: Support Vector Machine, K-Nearest Neighbor and the Bagging Classifier method. I investigated and experimented with ADA Boost, Decision Trees and Random Forest Classifiers as well. We'll train on three different amounts of the data (1%, 10% and all) we'll compare accuracy and f-scores to see which models seem the best for us.
Data Exploration and Analysis, visualizations
## Results Summary:
I started out with two main questions "What types of offers are most successful and will drive more business and what features will drive successful offers?" To get a better understanding of that we reviewed the data, manipulated and visualized it in a few different ways. We combined it and formatted it then created a solid feature set. We were able to view that data and determine a few different offers that tended to be successful (discount_10_10_2, discount 7_7_3 and bogo_5_5_5 and bogo 5_7_5). We created some visualizations of the demographics for those offers, but it wasn't very helpful.

I modeled a few different classifiers starting with a Naive Predictor. The Accuracy was about 45% and F1 Score 0.51 (middle of the road, not very good). I then tested the models discussed above to find the a good solid model that would predict at a high level. The SVC model had an Accuracy in the testing set between 77% and 80% and an F1 Score range from 0.75 to 0.76. Pretty solid, much better than the Naive predictor. The KNeighbors ranged from 72% to 77%, not as good with F1 Scores from .70 to .75. Finally the Bagging Classifier ranged from 75% to 80% with F1 Scores from .74 to .79. The Bagging Classifier was marginally better than the SVC, but the final determinant was the speed. The Bagging Classifier was much, much faster taking significantly less time to deliver results than the SVC with all the data used in the Training and Testing sets.
I then used that model to determine the features that would be most important using feature_importances_. This resulted in age, time, reward, difficulty and duration. Which leads me to conclude that the type of offer, combined with its rewards are major factors in whether it will be successful. Additionally the age of the respondent as well as what appears to be newer members (2018 and 2016) figured significantly in our top ten predictive features.

Finally, a blog post discussing the findings and visualizations can be found at https://github.com/cherrde/cherrde.github.io/starbucks_capstone.html
## File List:
- README.md - a markdown file containing this information
- Starbucks_Capstone_Notebook.ipynb - a Jupyter Notebooks with calculations, models and visualizations
- Starbucks_Capstone_Notebook.html - an html file saved from the Jupyter notebooks
- data/merged_data.csv - a datafile will merged cleaned datafile
- data/portfolio.json - a json file with portfolio data (provided at start)
- data/portfolio_clean.csv - a datafile with cleaned porfolio datafile
- data/profile.json - a json file with profile data (provided at start)
- data/profile_clean.csv - a datafile with cleaned profile datafile
- data/profile_offer_feature.csv - a datafile with merged profile offer data in feature form
- data/transcript.json - a json file with transcript data (provided at start)
- data/transcript_clean.csv - a datafile with cleaned transcript data
## Installation:
None
## Acknowledgements:
A thanks to Udacity, the Mentor program and previous projects. Specifically code was reused from the visuals.py python script in the Arvato Project from Intro to Machine Learning, as well as Project 1 for this module.
