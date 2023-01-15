---
attachments: [Clipboard_2022-12-28-10-23-28.png, Clipboard_2022-12-28-10-23-56.png, Clipboard_2022-12-28-10-33-58.png, Clipboard_2022-12-28-10-34-50.png, Clipboard_2022-12-28-10-35-24.png, Clipboard_2022-12-28-10-35-56.png, Clipboard_2022-12-28-10-36-47.png, Clipboard_2022-12-28-10-37-45.png]
tags: [mlc]
title: '2: Machine Learning Concepts: Basics'
created: '2022-12-27T16:21:38.996Z'
modified: '2023-01-01T04:31:40.660Z'
---

# 2: Machine Learning Concepts: Basics

Welcome back. In this lecture, we'll now start diving into the concepts of machine learning. Okay, let's begin.

![](../../attachment/Clipboard_2022-12-28-10-23-28.png)

## What is Machine Learning?

Machine learning is a subfield of artificial intelligence, AI. It provides systems and applications with the capability to learn and improve from experience without being explicitly programmed.

![](@attachment/Clipboard_2022-12-28-10-23-56.png)

![](@attachment/Clipboard_2022-12-28-10-33-58.png)

 The key objective of machine learning is to empower computers to learn automatically without requiring ongoing human assistance or churning. 
Here the concept of learning is performed through the use of machine learning algorithms whose performance improves over time as more and more data is analyzed and processed. Discovered patterns within datasets can be used to make informed and insightful predictions about future events, etc.

In 1959 Arthur Samuel, an American pioneer in the field of artificial intelligence, defined machine learning as a field of study that gives computers the ability to learn without being explicitly programmed. Later on, Tom Mitchell, another American computer scientist, provided a more formal definition of machine learning.

![](@attachment/Clipboard_2022-12-28-10-34-50.png)

A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience E. 

## Industries Application

Machine learning's proven success and application within and across a wide-ranging spectrum of business use cases is attributable to its ability to continually learn and improve. 

![](@attachment/Clipboard_2022-12-28-10-35-24.png)

Machine learning algorithms by their nature are iterative and are continually self-churning seeking to optimize predictions. Machine learning can be applied to many business use cases.


Machine learning technology has been proven incredibly successful for the following business functions: Recommendation engines, demand forecasting, computer vision, fraud detection, medical diagnosis, stock market forecasting, and sentiment analysis. 

## Terminology
Before we continue on in the course, let's first cover off some basic but key machine learning terminology that we will continually encounter throughout the remainder of the course.

![](@attachment/Clipboard_2022-12-28-10-35-56.png)

### Features
 Features, each item or piece of data is described by a number of features. Labels, again, each item or piece of data may be tagged with a known classification result. And Instances, an instance or sample is an item within the dataset, each instance will have a set of features, and may also have a label assigned to it.

#### Terminology usage
In this slide, we can see the terminology in use. We have three different houses, each being an instance within the dataset. Each house has a set of features. Features, for example, are the number of rooms, the size of the house, the number of levels in the house, and the color of the house. Each house has a label associated to it. In this case, the label represents the purchase price.

## Machine Learning Phases
Applying machine learning in practice requires a number of individual steps performed in a particular sequence. In general, the sequence required is as following: Dataset collection. You need to have access to a dataset of past observations. Featurisation. You will need to prepare the dataset and ensure that each data point has the necessary features available. Model Training.

![](@attachment/Clipboard_2022-12-28-10-36-47.png)

## Training
Once you have selected a machine learning algorithm, you will need to train it, usually with a subset of the data, the outcome of which will be a model able to perform predictions. Model Testing. The machine learning model created will need to be tested for accuracy. The testing is usually done with a different subset of the original dataset. The durations of model training and testing are done until the model is determined to be fit for purpose. That is, it can be used to predict useful and accurate results.

## Machine Learning Types
Machine learning algorithms are categorised into those that are used for supervised learning and those that are used for unsupervised learning. For example, you are training a model in which each of your data points has a corresponding target, or label. Then this is called supervised learning.

![](@attachment/Clipboard_2022-12-28-10-37-45.png)

### Supervised
Your machine learning algorithm seeks to build a map from the data points to their respective labels. If the labels can be expressed in terms of types or classes, then this is considered a classification learning task. Alternatively, if the target space in continuous, it is considered a regression learning task.

### Unsupervised
Alternatively, if you are training your machine learning task with just a set of imports and no labels, then this is called unsupervised learning. Unsupervised learning can be used to find structure in relationships between different data points. Unsupervised learning is frequently used to perform clustering but can also be used to perform anomaly detection. We'll dive deeper into the concepts and key differences between supervised and unsupervised training in the following lectures.
That concludes our lecture for the intro into machine learning concepts. In the next lecture we'll dive deeper into supervised learning as a method of building and training machine learning models. Go ahead and close this lecture, and we'll see you shortly in the next one.
