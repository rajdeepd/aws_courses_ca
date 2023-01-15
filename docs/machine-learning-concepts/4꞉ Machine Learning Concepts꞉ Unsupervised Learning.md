---
attachments: [Clipboard_2022-12-28-10-46-34.png, Clipboard_2022-12-28-10-46-50.png, Clipboard_2022-12-28-10-47-15.png, Clipboard_2022-12-28-10-47-42.png, Clipboard_2022-12-28-10-48-22.png, Clipboard_2022-12-28-10-48-50.png, Clipboard_2022-12-28-18-20-27.png, Clipboard_2022-12-28-18-20-50.png, Clipboard_2022-12-28-18-21-25.png, Clipboard_2022-12-28-18-21-53.png, Clipboard_2022-12-28-18-22-10.png, Clipboard_2022-12-28-18-22-44.png, Clipboard_2022-12-28-18-23-12.png]
tags: [mlc]
title: '4: Machine Learning Concepts: Unsupervised Learning'
created: '2022-12-28T05:09:27.144Z'
modified: '2023-01-01T04:32:16.908Z'
---

# 4: Machine Learning Concepts: Unsupervised Learning

Welcome back. In this lecture, we'll start diving into unsupervised learning, and how you use it to train machine learning models.

![](@attachment/Clipboard_2022-12-28-10-46-34.png)

Let's start with the following statement. 

![](@attachment/Clipboard_2022-12-28-10-46-50.png)

I have a data set containing no answers. I need to discover a pattern or relationship embedded within the data set that might help me find answers? How might I use machine learning to predict the answers I seek. Contrary to supervised training, unsupervised training takes a different approach in that the associated algorithms are designed to work with unlabeled data sets. Unsupervised learning algorithms don't rely on pre-labeled training data to learn.

![](@attachment/Clipboard_2022-12-28-10-47-15.png)

The machine learning algorithm in this situation will hunt for patterns in structure buried within the data set. Having discovered any patterns or structure, the model can then be used to make predictions and/or decisions when new data is introduced into the problem. Pattern recognition, within the data set, can involve concepts of clustering, anomaly detection, and association discovery. A typical unsupervised machine learning example is that of identifying close-knit groups of friends within a social network. As mentioned previously, unsupervised training is tasked with finding patterns, relationships, and/or correlations between data points within the data set being processed.

## Pattern Types
These patterns, relationships, and/or correlations come in different types. 

![](@attachment/Clipboard_2022-12-28-10-47-42.png)

For example, as can be seen on this slide, if we consider our data set to be a table of instances, each with the same set of features, then we can begin to see the different types of these so-called patterns. 

### Clustering

Clustering is concerned with finding similar instances. Anomaly detection is concerned with finding unusual instances, and association discovery is concerned with finding feature rules that may exist between and across instances. Let's take a closer look at each of these patterns. Reiterating as per the earlier slide, clustering is concerned with finding similar instances.

![](@attachment/Clipboard_2022-12-28-10-48-22.png)

In the example given here, we can clearly see a clustering pattern, in which Mary undertakes travel to or from New York on the first of each month at the cost of $30. 

### Anamoly Detection
Anomaly detection, on the other hand, is concerned with finding unusual instances. 

![](@attachment/Clipboard_2022-12-28-10-48-50.png)

In the example given here, we can clearly see an anomaly in which Mary appears to have spent $2000 on entertainment in New York on a day that she didn't bill any travel costs, and finally, 

![](@attachment/Clipboard_2022-12-28-18-20-27.png)

association discovery is concerned with finding feature rules that may exist between and across instances within the data set.

![](@attachment/Clipboard_2022-12-28-18-20-50.png)

In the example given here, we can clearly see a number of potential feature associations. As can be seen on this slide, many of the unsupervised learning algorithms fall into the clustering category. For example, we can use either the K. Means Hierarchical or the Gaussian Mixture for clustering analysis. The training phase for unsupervised training is similar to that used within supervised training, the key differentiator being the loss of labels, or that the supervised training algorithms do not take, as part of their inputs, a label or answer.

## Training Process

![](@attachment/Clipboard_2022-12-28-18-21-25.png)

Instead, the unsupervised training algorithm number crunches the feature vectors for all data instances looking for cluster patterns, anomalies, and/or association rules. 

## Business Analytics

![](@attachment/Clipboard_2022-12-28-18-21-53.png)

As such, the generated model itself returns answers that suggest cluster citizenship, or whether the data point should be considered an anomaly. Unsupervised machine learning can be used to answer many business problems. The important thing to consider when attempting to answer these questions is where and what data sources are available. Some examples are given here.

## DataSet Summary

![](@attachment/Clipboard_2022-12-28-18-22-10.png)

Do these customers have similar likes? Here, we would train our model with the customer profiles data set. Is this transaction a fraud? Here, we would train our model with the previous and past transactions data set. And finally, were these products purchased together? Here, we would train our model with the examples of previous purchases data sets. Okay, let's quickly summarize unsupervised training, its important characteristics, how it is used, and some example algorithms. Most importantly, the training data set has only examples and no specific label or outcome.

## Training Summary

These types of data sets are actually fairly common as the process of labeling is typically expensive.

![](@attachment/Clipboard_2022-12-28-18-22-44.png)

 The goal of unsupervised training is to search for and find patterns, anomalies, and rule associations. Unsupervised training tends to be more complex because the data has not outcome and cannot be evaluated. Each discovery method has its own quality measures. 
 
 ## Algorithm Summary

 ![](@attachment/Clipboard_2022-12-28-18-23-12.png)

 Unsupervised training algorithms can be used to perform the following tasks, clustering, for example, we can use the K. Means Algorithm, which we'll discuss in more detail in the next lecture, anomaly detection, and/or association discovery.

That concludes our lecture on unsupervised training. In the next lecture, we'll start focusing on the actual machine learning algorithms themselves that are commonly used. Go ahead and close this lecture, and we'll see you shortly in the next one.
