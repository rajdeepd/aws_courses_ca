---
attachments: [Clipboard_2022-12-31-18-53-54.png, Clipboard_2022-12-31-19-00-58.png, Clipboard_2022-12-31-19-01-11.png, Clipboard_2022-12-31-19-01-45.png, Clipboard_2022-12-31-19-03-05.png, Clipboard_2022-12-31-19-03-28.png, Clipboard_2022-12-31-19-06-04.png, Clipboard_2022-12-31-19-06-41.png, Clipboard_2022-12-31-19-07-19.png, Clipboard_2022-12-31-19-07-37.png, Clipboard_2022-12-31-19-07-55.png, Clipboard_2022-12-31-19-08-44.png]
tags: [mlc]
title: '5: Machine Learning Concepts: Machine Learning Algorithms'
created: '2022-12-28T12:55:28.731Z'
modified: '2023-01-01T04:32:22.629Z'
---

# 5: Machine Learning Concepts: Machine Learning Algorithms

## Introduction

Welcome back. In this lecture, we'll start diving into a few of the commonly used machine learning algorithms. 

![](@attachment/Clipboard_2022-12-31-18-53-54.png)

We'll explain how each algorithm works and for what problems it is best suited towards. The chosen list of machine learning algorithms we cover often in this lecture covers the various machine learning methods and techniques available.

![](@attachment/Clipboard_2022-12-31-19-00-58.png)

For example, supervised verses unsupervised. And classification verses regression. Please note, there are many more machine learning algorithms beyond the list we will cover here. But before we start, and often asked question faced by beginners when presented with so many machine learning algorithms is whichever of them shall I use? There is no silver bullet answer to this question. However, there are certainly many attributes that you should consider about your data before you apply and select a machine learning algorithm.

![](@attachment/Clipboard_2022-12-31-19-01-11.png)

Some examples to consider are the size, quality, and nature of your data, the available computation time, the urgency of the task, and what you want to do with the data. More often than not, you will need to experiment with your data to determine which algorithm gives the best results. Let's move on and get familiar with some of these common and popular machine learning algorithms. Regression is a machine learning technique used to predict a numerical value outcome.

## Linear Regression

Linear regression attempts to establish a linear relationship between one or more independent variables and an outcome or dependent variable. The linear regression algorithm takes a set of data points and finds the best fitting line through the data set. For example here, the data set consists of a dependent variable `Y`, and an independent variable `X`. 

![](@attachment/Clipboard_2022-12-31-19-01-45.png)

Using linear regression, the best fitting line will be found such that the cumulative distance between each data point and the nearest point on the line is a minimum. Recall that the equation for a line in the form of `Y equals mX plus c`, where m is the gradient of the line, the `c` is the `Y` axis intercept.

The linear regression algorithm we use basic calculus applied to the data set in question to the values of m, the gradient, and c, the Y axis intercept. Additionally, linear regression can be further refined into two types. Simple linear regression, where only one independent variable is used, and multiple linear regression where multiple independent variables are defined. Although the name implies regression, logistic regression is actually a powerful and simple classification tool.

## Logistic Regression

Classification, using logistic regression, is a supervised learning method and therefore requires a labeled data set. In fact, logistic regression can be used to perform both binary and multi class classification. Logistic regression typically uses a function to push values towards a particular boundary. 

![](@attachment/Clipboard_2022-12-31-19-03-05.png)

As seen here in this example, the sigmoid function, also known as the logistic function, has the characteristic in the shape of a S-curve and such can squeeze and push the data set points towards the upper and lower boundaries and therefore, is very useful for performing binary classifications.

## Decision Trees
Decision trees are machine learning models that are in the form of tree structures. Decision trees are one of the most popular and widely used machine learning algorithms. A decision tree is a type of supervised learning algorithm and is nothing more than a tree in which each known leaf node represents a decision between a set of choices. And where the leaf nodes are the final decision or classification.

![](@attachment/Clipboard_2022-12-31-19-03-28.png)

There are two types of decision trees used in machine learning. The classification tree. An analysis where the predicted outcome is the class to which the data belongs. For example, the color is red or the person is male. Regression tree, an analysis where the predicted outcome can be considered a real number. For example, someone's income or the time it will take to solve a customer inquiry. Let's provide a quick example of how a decision tree works. A typical example involves trying to predict tomorrow's weather based on several features we know about today's weather. Let's assume we have been collecting the temperature, wind, and pressure attributes for each day of the past year, and whether or not it rained the following day.

Using this type of data set, together with a decision tree algorithm, we can train our machine learning model to help us forecast for possibility of rain or not any time in the future based on the weather attributes of the day before. The decision tree presented on this slide is an example of this model might end up looking like. Decision tree are a popular tool for machine learning practitioners for various reasons. Let's cover some of the important advantages associated with decision trees. Decision trees are simple to understand and interpret.

People are able to understand a decision tree models after a brief explanation as they mirror human decision making. Decision tree are able to handle both numerical and categorical data. Decision trees require little or minimal data preparation. And finally, decision trees perform well with very large datasets. 

## Naive Bayes

Naive Bayes can be used to produce classifiers or models that are used to predict labels for new data points and is such is used for classification problems. Naive Bayes is not a single algorithm, but in fact a collection of classification algorithms based on probability in the Bayes Theorem. Central to the way Naive Bayes works is the principle that every feature being classified is independent of the value of any other feature.

![](@attachment/Clipboard_2022-12-31-19-06-04.png)


Features often add always independent and it is this characteristic that leads to the machine learning technique being titled Naive. The Naive Bayes algorithm provides us with the ability to predict the class given the set of features using probability. For example, creating a fruit classifier, we could predict whether a fruit is an orange, banana or apple by analyzing its color, shape and weight, et cetera, the features. Although based on a fairly basic process, Naive Bayes often outperforms other more sophisticated machine learning algorithms and has been successfully integrated into common applications like email spam detection and document classification.

![](@attachment/Clipboard_2022-12-31-19-06-41.png)

**Naive Bayes models are known to work well with very large datasets**. Walking through a basic example as seen on this slide, the Naive Bayes equation predicts the probability that the data point is ClassA if it has features one and two. In other words, if you see features one and two, this is the probability that the data point is classified as ClassA. The equation can be understood as such. The probability of ClassA, given features one and two, is equal to the fraction where the fraction's numerator is the probability of feature one given ClassA multiplied by the probability of feature two given ClassA multiplied by the probability of ClassA. And the fraction's denominator is the probability feature one multiplied by the probability of feature two.

## SVM: Support Vector Machine

A support vector machine, or SVM for short, is a method of classification. With SVM, you take a plot of rural data points and then in dimensional space where it enters in the number of features. The algorithm attempts to find a line that separates and classifies the data points in such a way that the chosen line maximizes the separation of the nearest data points within each class to the line itself. The SVM lines are known as classifiers. 

![](@attachment/Clipboard_2022-12-31-19-07-19.png)

As seen here, each data point on the plot has two features, F one and F two. The data points are classified via the green line which maximizes the distance of separation to the line. Based on this line, the data points are being considered classified in two different groups.

# K-Nearest Neighbor (KNN)

K-Nearest Neighbors, or KNN for short, can be used for both classification and regression problems regardless, it is more often adopted for classification problems. And like other machine learning algorithms that are trained and tested on separate splits of a dataset the K-Nearest Neighbors algorithm is trained on the entire dataset. When attempting to classify a new data point, the KNN algorithm scans through the full dataset in search for the K-eth nearest data points to the new data point. Or in another way, it looks for the K number of data points most similar to the new data point. When using KNN for classification, the outcome is the most frequently discovered class.

![](@attachment/Clipboard_2022-12-31-19-07-37.png)

When using KNN for regression problems the outcome is the main of the results. In the simplified example shown here, the classification changes for the new instance as the value of K increases. When K is equal to one, the classification of the new instance is classified. When K increased to three, the classification of the new instance becomes class two. The K-Means algorithm is one of the most frequently used unsupervised machine learning algorithms. It is used to cluster similar or likewise data points. K-Means uses a non deterministic and reiterative approach to analyze and find K number of clusters within a given dataset.

![](@attachment/Clipboard_2022-12-31-19-07-55.png)

The value K represents the number of clusters defined and is a user supplied value seeded into the algorithm when it starts. The output of the K-Means algorithm is K clusters with the input data petitioned amongst these clusters. In the example that is shown here, K-Means algorithm was initialized with the K value of three and the algorithm has gone on and correctly identified three clusters, a blue cluster, red cluster, and green cluster.

## Random Forest

The Random forest algorithm is interestingly an extension of the decision tree algorithm in the sense that it can be considered as a collection of decision trees, hence the name forest. Each decision tree within the forest performs its own classification of the current data instance and essentially votes for that classification. The most votes wins. Random Forests are considered to be a very strong and accurate modeling algorithm. More so than when compared with using a single decision tree. Their ability to aggregate many decision trees affords them the ability to minimize over fitting and as such can yield highly accurate predictions.

![](@attachment/Clipboard_2022-12-31-19-08-44.png)

Each decision tree within the Random Forest has been created based on a different random sampling of data taken from a training dataset. As can be seen on the slide, this simplified conceptual view of a Random Forest consists of three decision trees. A data point is passed into each of the three decision trees. Each tree processed the instance and results in a voted classification. The first tree votes for class one, second tree votes for class two, and the third tree voted for class two as well. Based on the majority voting rule, the data point in question is finally classified as class two.

## Summary

That concludes our lecture on machine learning algorithms. In the next lecture, we'll introduce you to deep learning and deep neural networks as another specialized method of performing machine learning. Go ahead and close this lecture and we'll see you shortly in the next one.


