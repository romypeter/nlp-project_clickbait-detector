# Clickbait Detector

Through NLP and text classification, our project aims to classify a headline as clickbait or non-clickbait.  

Clickbait refers to an article headline whose purpose is to use sensationalist language to lure in a viewer to click through to a certain webpage. That webpage typically generates ad revenue on the user's clicks or monetizes the user's activity data. The clickbait article itself is not written with journalistic integrity, research or really any deeper or practical meaning - it is simply a vehicle to grab clicks and activity.

With the explosion of social media, smartphones and so many people connected to the internet daily, there is no shortage of ‘information' and online objects vying for our attention, but all are not equal. The ease of sharing and reposting on social media has allowed clutter like clickbait to run wild. And the often profitable nature of publishing and capitalizing on clickbait has also given way to the increase in clickbait.

With clickbait becoming increasingly common and, generally considered as a nuisance, we wanted to see if a headline could be classified using machine learning and what that looks like.

#### Use case scenarios:
This could be implemented on a larger scale - on social media/various websites, as a 'clickbait blocker', and clickbait could be flagged or filtered out as such even before a user sees them.

## The Dataset
52,000 headlines from clickbait and non-clickbait sources from roughly around 2007 - 2020.
- 30,000: 2007 - 2016 headlines from https://www.kaggle.com/amananandrai/clickbait-dataset
- 22,000: 2019 - 2020 headlines that we scraped/requested from Twitter, APIs, online publications.

Clickbait sources: Buzzfeed, Upworthy, ViralNova, BoredPanda, Thatscoop, Viralstories, PoliticalInsider, Examiner, TheOdyssey

Non-clickbait sources: The New York Times, The Washington Post, The Guardian, Bloomberg, The Hindu, WikiNews, Reuters

## The Process

1. Gather the data
2. Clean and process the data, including feature engineering
3. Explore data through EDA for initial insights and understanding
4. Model & evaluate: Train classifiers and evaluate test predictions, interpret model performance and so on

## Results of Exploratory Data Analysis 

### Target distribution
![](/Images/classes.png)
### Distribution & comparison of engineered features on each class
![](/Images/num_words_comparison.png)
![](/Images/numstart.png)
![](/Images/question2.png)
### Most frequent words for each class
Clickbait:  
![clickbait](/Images/wc4.png)
<br/>Non-clickbait:  
![nonclickbait](/Images/wc5.png)

## Models & Interpretations
#### Baseline Dummy Classifier
![](/Images/dc_cm.png)
#### Naive Bayes
![](/Images/nb_cm.png)
![](/Images/CB_coefs_nb.png)
#### Logistic Regression 
![](/Images/lr_cm.png)
![](/Images/noncb_lr_coeff.png)


## Conclusion

We were able to use machine learning algorithms such as Naive Bayes, Logistic regression and SVM to accurately classify clickbait versus non-clickbait headlines. The results were quite good - within the 90-93% range for accuracy scores and 90-93% range for recall scores. We slightly prioritized recall as it was understood that it would be more valuable to minimize false negatives (classifying clickbait as non-clickbait) and as such Naive Bayes performed the best.

As machine learning was able to work so well, there is definitely a real world use case for deploying a machine learning solution to filter out / flag clickbait before a reader even has to visualize and discern the headline for themselves!

By analyzing the coefficients of the models that performed the best, We were able to interpret and get some insight into how the models determined if a headline is clickbait or not.


## Demo & App

Try the deployed version (deployed using Heroku & Streamlit): https://nlp-project-clickbait-detector.herokuapp.com/


## Repository Navigation 

1. Datasets folder - contains all the relevant CSV files to be loaded in Google Colab (if running the source code).
2. Code Snippets folder - contains codes for scraping data, API requests, cleaning & EDA, modeling and so on.
3. Clickbait_Final_Code.ipynb - The final notebook showcasing the end to end project.
4. app.py, pkls, setup.sh, requirements.txt, runtime.txt, procfile - files required by Streamlit Dashboard.
5. Images - this folder contains images that show up on the Github repo.

## Code Interpretation Instructions

- Firstly, start with the cleaning&EDA notebook under the 'Code Snippets' folder - this compiles all relevant CSVs (found in the Dataset folder) and sets up the data for the project.  Feature engineering code is located here and processing for EDA is also found here.

- Secondly, the modeling notebook (also in 'Code Snippets') - code here is used to further process the data for modeling and then creating/evaluating classifiers.

- Lastly, the Clickbait_Final_Code notebook gives an overview of the whole process - this notebook can be used for a clear picture of the end to end process but areas like data cleaning are just explained in markdown and hence the working notebooks in 'Code Snippets' can be utilized for all details. 


## Citations 


Kaggle dataset: https://www.kaggle.com/amananandrai/clickbait-dataset

Streamlit reference: https://docs.streamlit.io/en/stable/api.html
