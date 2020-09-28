# Health Insurance Sale Analysis
Dataset describe our clients and we should predict, who can buy our insurance? So we should explore, which feature influence on it.

## Code and Resources Used
Python Version: 3.7

Packages: pandas, numpy, sklearn, matplotlib, seaborn

I got this datasets from Kaggle.com, thanks for Anmol Kumar. It was divided for test and train. This dataset have GPL 2 license.

Dataset link on Kaggle.com: https://www.kaggle.com/anmolkumar/health-insurance-cross-sell-prediction

Anmol Kumar link on Kaggle.com: https://www.kaggle.com/anmolkumar

## Goals and objectives
My goal to predict: who will buy our insurance?

To do this I should do next things:

To make exploratory data analysis

To prepare our data for Machine Learning

To build and upgrade our Machine Learning model


## Exploratory Data Analysis

I explored how did our features distribute, how they work together. For more you can look at my EDA part, there are a lot of graph, which is intesting and helpful. They helped we to understand, how our data works. Below you can see most important graphs.

Here we can see the distribution of age groups among our clients. It is very important because the largest age group (18-29) buys a small number of insurers, as compared to the other in percentage.
![Age_Groups](/images/age_groups.png)

Annual premium had many emissions that we eliminated in the next step, but after elimination we can see the normal distribution. As we can see, the number of people paying less than 10,000 is enough, so we need to work on that later. But that’s another task.
![Annual_Premium](/images/annual_premium.png)


Vintage is the number of days a customer has spent with the company. As we can see, people usually stop buying our insurance for 100 and 200 days.
![Vintage](/images/vintage_response.png)

## Data Preprocessing

In this part I cleaned and prepare data for model building. All of this code you can find in separate file, which we can use for embeding into the work process.


This is the plan, that I have done:

1. Explonatory part
2. Encoding Features
3. Dropping unnecessary features:
    - id and region_code
    - finding unnecessary features with RandomForestClassifier
4. Remove outliers - annual_premium
5. Feature scaling

## Model Building

In this part of the project I have to build model, that will predict, who will buy our health insurance. My goal was to build a classifier that would cover the greatest number of potential customers with a high chance of a sale, so that our sales managers could work more efficiently. So I have to concentrate on recall score. 

Firstly, I tested a lot of classifiers, which could work well with our data. Most effective was Extra Forest, Naive Bayes(which we would use later) and K-Neighbors Classifier. They were chosen to be tuned. After tuning they didn't give us a good performance, so I continue finding new ways to solve our problem.

Secondly, I tried ensemble model: Voting and AdaBoost, unfortunately they didn't give us good results too.

So, I stopped on Naive Bayes classification and tried several NB model. The best was Gaussian Naive Bayes Classifier. This model give us 97% of recall and 25% of precision, that was good results for us. But not only result was the reason of choosing it. This classifier give us an opportunity to work online, without teaching model every week or month.

## Conclusion

The model showed good results. If you want it, you can embed it into the workflow and put it into production. 
