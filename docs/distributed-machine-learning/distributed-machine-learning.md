# Distributed Machine Learning

## Introduction

Welcome back. In this lecture, we'll begin discussing what exactly distributed machine learning is. We discuss what motivations may exist that could require you to consider a distributed machine learning environment. Distributed machine learning refers to the concept in which machine learning processes have been scaled out and deployed across a cluster of compute resources. In doing so, distributed machine learning allows you to draw upon more compute resource, allowing you to paralyze the machine learning mechanics and mathematical operations, which in turn, expediates end results and outputs.

So what exactly might motivate you, and your business requirements into justifying a distributed machine learning architecture? Let's cover off some of the possible reasons.

![dml](./images/Screenshot%202023-01-07%20at%208.08.53%20AM.png)

## The Need


Large datasets. Some datasets, for example, petabyte-scale datasets, are just too big to be processed by a single machine.
Speed. A distributed machine learning environment affords you the ability to paralyze your machine learning processing requirements, allowing you to achieve quicker results comparatively to running the same processing on a single node environment.
Complexity.

![motives](./images/Screenshot%202023-01-07%20at%208.09.43%20AM.png)

The complexity of the dataset in terms of its features in the particular machine learning algorithm may exceed the capabilities of a single node setup.

## Accuracy

The accuracy of a machine learning model can be enhanced by processing more data. This, in turn, is connected back to the large datasets point above.

## Role Distributed Machine Learning plays

In summary, distributed machine learning is an important technique given the amount of data being generated in today's big data era. Leading on from this, the question is, which platform might we choose to help build out a distributed machine learning environment?

One such platform that has become very popular in recent times is Apache Spark.

## Apache Spark

As we'll see in the next lecture, Apache Spark is a specialized platform which excels at performing distributed computation and in more specialized cases, distributed machine learning. That concludes this lecture. Go ahead and close this and we'll see you shortly in the next lecture, where we'll introduce you to Apache Spark, a lightning-fast cluster computing engine, perfect for distributed machine learning.
