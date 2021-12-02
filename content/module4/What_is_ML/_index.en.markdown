---
date: "2016-04-09T16:50:16+02:00"
title: Machine Learning
output: 
  learnr::tutorial
weight: 1
---

### Machine Learning

This section introduces you to fundamental Machine Learning (ML) concepts and algorithms. Impowered by modern computing capabilities and statistical modelling machine scale analysis can capture hidden values in big data that are otherwise limited to human scale thinking. In 1959 in a paper [Some Studies in Machine Learning Using the Game of Checkers]( https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=5392560) Arthur Samuel used term **_machine learning_**  in the game of checkers in the form we know it today: _“to verify the fact that a computer can be programmed so that it will learn to play better game of checkers than can be played by the person who wrote the program”_. The paper conveys the process of passing our own methods of learning to a machine as a subfield of statistical computing. It is the application of statistical modelling to obtain a general understanding of the data to make predictions and to improve performance based on data and empirical information.   

![ML](/module4/What_is_ML/images/ml_diagram.png?width=20pc)

ML can learn from the data that is processed and analysed and the more data it processes, the more it can learn. But, to create such intelligent machines it is useful to develop un understanding of classical statistics that is the LifeBlood of ML algorithms. Coated by the layers of k-nearest neighbours, linear regression, random forest, naïve bayes… machines can develop cognitive abilities of today’s Artificial Intelligence (AI). 

Translating the statistical methodologies that can run on machines through the coding and programming is another vital part of ML. As such, R is a powerful statistical language for learning of important and desirable ML skill: code writing for statistical modelling. Using R greatly simplifies machine learning. Using R we can focus on developing understanding on how each algorithm can solve a problem, for which we can simply use a written package to quickly generate prediction models on data with a few command lines.

### Types of ML

We will touch up on a few most popular ML algorithms from a vast set of its algorithmic tools for understanding data. These tools are broadly classified as **supervised** or **unsupervised**. In general, _supervised learning_ involves building a statistical model for estimating or predicting an output based on one or more inputs. There are many examples of their application in pharma and medicine such as disease identification/diagnosis and personalised treatments, or prising in business to name a few. With _unsupervised learning_, there are inputs but no supervising output; nevertheless, we can learn relationships and structure from such data. One of the most popular examples is a recommender system as a reflection of our consumer behaviour.  Other examples can be found in biological genomic studies, market research, security with the most used example of anomaly detection of malicious activity in an organization’s network etc.

![ML_Types](/module4/What_is_ML/images/ML_Types.png?width=75%)

Fuelled by powered computer technologies ML models have evolved considerably in the last decade advancing into third category known as _**reinforcement**_. Unlike supervised and unsupervised learning, _reinforcement learning_ continuously improve its model advancing from the previous iterations. Unlike the other two categories of ML which reach an indefinite stage after the model is formulated from the **training** and **test** data segments. The examples can be found in computer gaming, skill acquisition such as real time discussion etc.  

#### Supervised Versus Unsupervised Learning

Majority od data analysis problems fall into one of the two ML categories: _supervised_ or _unsupervised_. Sometimes we deal with a problem in which for each observation we have a predictor(s) `\(x_i\)`, `\(i = 1, 2, … n\)` there is a response `\(y_i\)`. In those cases, we seek to find a model that reflects the possible relationship between response and predictor(s), with the aim to be able to predict the response values for future observation accurately with greater understanding of the relationship between the two. In statistical terms, we wish to conduct:
-	the prediction of `\(y\)`’s for future values of `\(x\)`’s and 
-	the inference about the nature of the relationship between `\(X\)` and `\(Y\)`

The best known statistical modelling techniques that fall into this ML category that are commonly used are linear regression, logistic regression, Generalised Additive Models (GAM), boosting and Support Vector Machines (SVM).

To the problems where for each observation `\(i = 1, 2, … n\)` we have a set of measurements `\(x_i\)`, but no associated responses `\(y_i\)` based on which we can “supervise” the analysis to understand the relationship between the variables or between the observations, we referred to as unsupervised learning. Commonly used methodology in this setting is _clustering_. The goal of cluster analysis is to group the observation in the data set into disjoint clusters of similar samples. It is commonly used in market segmentation where you, for example, need to develop marketing strategies for identified groups of customers clustered into them based on their behaviour. 

Previously we recognised that when dealing with the measured response variable in statistical modelling we tend to use regression. If, however we have attribute response variable such as defaults on a debt, gender, ethnicity, to name a few, we tend to use classification modelling. In multifactor data analysis selecting appropriate statistical modelling technique is not so straight forward as it is in bivariate statistical modelling situations, for which we fit a model based on the type of the response variable. Here, we can use logistic regression for the models with binary response attribute variable as it estimates class probabilities, which on the other hand can be thought of as a regression method as well. Methods such as K-nearest neighbours and boosting can be used for both measured and attribute response variables. When dealing with multifactor statistical modelling, we have to think carefully not just about the type of the response variable, but most of all about type of the problems we wish to address. 

#### Assessing Model Accuracy

Selecting the most efficient approach can be one of the most challenging parts of performing statistical modelling in practice as the choice of the model that has worked on one data set may not perform as well on the other, but similar data. Therefore, evaluating the performance of a chosen statistical method is seen as an important part of statistical modelling. 


___
**YOUR TURN 👇**

Identify a data set from your own work experience or from amongst many available freely on Internet and describe a problem that can be addressed using this data. Write a brief report describing identified data and a problem that can be addressed using this data. Discuss further in your report which of the categories of ML would be applicable for the analysis of this problem? Try to justify your thinking.


-----------------------------
© 2020 Tatjana Kecojevic
