---
attachments: [Clipboard_2022-12-27-19-51-45.png, Clipboard_2022-12-27-19-51-57.png, Clipboard_2022-12-27-19-52-36.png, Clipboard_2022-12-27-19-52-51.png, Clipboard_2022-12-27-19-54-09.png, Clipboard_2022-12-27-19-55-09.png, Clipboard_2022-12-27-19-57-36.png, Clipboard_2022-12-27-19-59-00.png]
tags: [intro]
title: '1: Introduction to AWS Machine Learning – Specialty Certification Preparation'
created: '2022-12-27T13:46:02.944Z'
modified: '2023-01-01T04:33:04.874Z'
---

# 1: Introduction to AWS Machine Learning – Specialty Certification Preparation

Hello. My name is Stephen Cole and I'm a trainer here at Cloud Academy.  Today, I'm here to talk with you about preparing for the AWS Certificated Machine Learning - Specialty exam.

![..](@attachment/Clipboard_2022-12-27-19-51-57.png)

According to `AWS`, this exam was designed to validate your ability to build, train, tune, and deploy machine learning models in the AWS Cloud.  
It's intended for people that work in data science roles as developers or analysts to demonstrate their knowledge and understanding of this specialty topic. 


Also, it is ideal for anyone looking to move into one of these roles going forward with their career; as the machine learning specialty certification is a great way to highlight your new skills.

With this in mind, we, my colleagues and I, here at Cloud Academy, have assembled a learning path designed to help you pass this exam.
I'm excited about what we have in the learning path today and am looking forward to augmenting it over time to keep pace with the innovation and releases made by AWS.
Like all AWS exams, the key to passing it is to do the work.  That said, for this exam, simply doing the work in the AWS cloud is not going to be enough.
You need to know the theories behind machine learning, understand Machine Learning outcomes & recognise when they're incorrect, how to improve them, and how to interpret the results.
The official blueprint for the exam lists four functional domains spread over 65 questions.  The questions are either multiple-choice or multiple-response and you'll have 180 minutes to take it.
The Blueprint can be found here. On this page, click on the button: Download the exam guide


There are four domains. They are Data Engineering, Exploratory Data Analysis, Modeling, and Machine Learning Implementation and Operations.

![](@attachment/Clipboard_2022-12-27-19-52-36.png)

The results for the exam are reported as a score from 100–1,000.  To pass you need a score of at least 750.

The AWS Certified Machine Learning - Specialty exam isn't like any other AWS exam.  
The other AWS exams cover cloud computing in-depth and expect you to be able to architect environments to solve specific problems.
To an extent, that is true of this exam too.  There are questions that will ask you to solve specific problems regarding Machine Learning and the AWS cloud.  However, what makes this exam unique is that it is not all about AWS technology.  
Instead, it also tests your knowledge and understanding on topics that include Machine Learning, Deep Learning, and Artificial Intelligence that are unrelated to AWS..
With that in mind, I want to briefly break down the exam's domains and what they cover.

**Domain 1** is Data Engineering and is 20% of the exam.  This means you should have about 13 questions that cover how to prepare and transform data.

![](@attachment/Clipboard_2022-12-27-19-52-51.png)

From the exam blueprint, there are three subdomains in domain 1.
You will be tested on your ability to create data repositories for machine learning, identify and implement a data-ingestion solution, and identify and implement a data-transformation solution.
This section should be straightforward for anyone who has experience working with Big Data on AWS.
The main services that are covered in this domain are streaming and data storage services.  This means services such as Amazon Kinesis, Data Pipeline, S3, DynamoDB, and RDS.

You can also expect, at a high level, services such as Amazon Athena and AWS Glue.
It is not important to understand all these services in great detail but you will need to know what they do and how they support machine learning workloads. 
For example, you need to know how to efficiently and effectively move data from RDS to S3 using AWS Data Pipeline and then how to get data from S3 into Amazon SageMaker.
Or, if you have unstructured and structured data in an S3 bucket and want to easily run SQL queries against it, you are looking at an excellent use case for Amazon Athena and AWS Glue.

For data transformation, AWS Lambda functions are an excellent use case but you'll need to know that Amazon Kinesis Data Firehose can do some transformations too. 

**Domain 2** is Exploratory Data Analysis and is 24% of the exam.  This is about 15 or 16 questions that cover cleaning data and feature engineering.
![](@attachment/Clipboard_2022-12-27-19-54-09.png)

From the exam blueprint, there are three subdomains for domain 2.
You will be tested on your ability to sanitise & prepare data for modeling, perform feature engineering, and analyze & visualize data* for machine learning.
Data is inherently messy.  In the exam, you're expected to know how to identify and correct errors that could negatively impact a predictive model.  
For example, you'll need to know how to deal with columns that have a single observation or value, a low variance, or have a few spikes.
Rows of data that have identical data are often useless and can be dangerously misleading during model evaluation.
Feature engineering efforts have two primary goals.
You have to prepare the dataset to be compatible with the machine learning algorithm's requirements and you need to ensure that the machine learning model is performant.
Techniques involved with feature engineering include--but are not limited to--imputation, managing outliers, binning, one-hot encoding, grouping operations, feature splitting, and scaling.  
Regarding visualisations, in the Data Analytics exam, you're asked what type of visualisation is best for a given data set.   
In contrast, in the Machine Learning exam, you will be shown a data visualisation or a confusion matrix and be asked what it means or represents. 
For example, from a confusion matrix, can you identify the true class frequency and predicted class frequency?  
Do you know how to calculate recall and precision?  
When reviewing a histogram for residual values, do you know what it means when the values form a zero-centered bell shaped curve?

**Domain 3** is Modeling and is 36% of the exam.  This means it is the largest and, probably, most significant part of the exam with about 23 or 24 questions.

![](@attachment/Clipboard_2022-12-27-19-55-09.png)

From the exam blueprint, there are 5 subdomains for domain 3.
You'll be tested on your ability to frame business problems as machine learning problems, whether or not you can select the appropriate model or models for a given machine learning problem, if you know how to train machine learning models, your understanding of hyper-parameter optimisation, and the evaluation of machine learning models.
Most of this domain is focused on Amazon SageMaker, so having hands-on experience with this service is essential. 
Specifically, it requires detailed knowledge of SageMaker with machine learning topics like algorithm selection and tuning deep learning models.
You need to know--at a high level--all of the available SageMaker algorithms, what they do, and their use cases.
While this is an AWS exam and it focuses on AWS technologies, you should have a general idea of how to incorporate frameworks like Spark and Tensor flow into SageMaker jobs.
You'll need to have an understanding of how to build a Docker container with a TensorFlow Estimator and how to use it to train a machine learning model.
If you get a question about PySpark, you'll need to know how to reuse PySpark code in order to do ETL and ingest data into Amazon SageMaker.  
If you're scratching your head at this reference, then my recommendation is to learn about AWS Glue.  You'll thank me later.

**Domain 4** covers Machine Learning Implementation and Operations and is worth 20% of the exam.  This is about 13 questions that relate to the deployment of  Machine Learning models using Sagemaker.

![](@attachment/Clipboard_2022-12-27-19-57-36.png)

There are four subdomains that are part of domain 4.
You'll be tested on your ability to measure machine learning solutions for performance, availability, scalability, resiliency, and fault tolerance.
You'll be asked to recommend and implement appropriate machine learning services and related features for a given problem.
This domain includes testing your understanding of basic AWS security practices involving machine learning as well as your ability to deploy and operationalize machine learning solutions.
It will also evaluate your understanding of the AWS AI services such as Poly, Lex, Comprehend, and Transcribe.
You will need to know what these AI services do and when you might need to use them.   For example, you might be asked to do sentiment analysis in multiple languages using one or more of those services.  It won't be enough to know--simply--what these services do.  You'll need to know what functionality is available.
The exam covers a lot of material and it is easy to feel overwhelmed by all of it.  The Learning Path that we've created for you will help keep you focused on what you need to study.  

The learning path provides interactive content comprising hands-on labs, video courses, and review questions that will help you prepare for this AWS certification. 

![](@attachment/Clipboard_2022-12-27-19-59-00.png)

There is a wide range of courses in the learning path,some are clearly for beginners.  They were included because we recognize that not all machine learning practitioners are the same.  Some might have limited experience in the breadth and depth of the material.  
Why it might seem silly to have a lectures called Introduction to Data and Machine Learning and  What is Machine Learning in a learning path designed for experts, it can be a challenging subject to explain and we recognize that some accidental data analysts--people that were put into a position of doing the work without getting a lot of formal training--might be well served with a review.
There's some programming with python in this learning path as well.  Will this make you an expert? No.  While there is no programming on the exam, a popular way to get started with SageMaker is to use the **Amazon SageMaker** Python SDK.  
With the SDK, you can train and deploy models using popular deep learning frameworks, algorithms provided by Amazon, or your own algorithms built into SageMaker-compatible Docker images.
The learning path also includes other AWS services.  While it's not exhaustive, they are ones you are likely to see on the exam.  
Better still, they are ones that you're likely to need in a production environment that is running machine learning workloads.
AWS regularly adds to its catalog of services and features.  We at Cloud Academy are doing the same.  We have lectures, labs, and assessments in the pipeline and will continue to augment our offerings.
With that, this learning path provides a good understanding of what's involved to prepare for the  AWS Certified Machine Learning - Specialty exam.  
Let's get started and, if you have any questions as you progress through your training, please reach out to us by emailing support@cloudacademy.com.
For Cloud Academy, I'm Stephen Cole, thank you for watching and letting us be part of your cloud journey.
