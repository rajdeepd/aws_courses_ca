# Spark MLlib

## Introduction

Welcome back. In this lecture we'll introduce you to MLlib. MLlib is **Apache Spark's** scalable machine learning library. Spark MLlib enhances machine learning because of it's simplicity, scalability and easy integration with other tools in the Spark ecosystem. Apache Spark comes with a native machine learning library, MLlib that is designed for simplicity, scalability and easy integration with other Spark tools.

![spark mllib](./images/Screenshot%202023-01-08%20at%206.20.36%20PM.png)

With the scalability, language compatibility and speed of Spark, data scientists can solve and iterate 3D data problems faster. Spark MLlib can be used for a number of common business use cases and can be applied to many datasets to perform feature extraction, transformation, classification, regression and clustering amongst other things as well.

## Use Cases

Some example business use cases where MLlib excels are advertising and marketing optimization, anomaly and fraud detection, recommendation systems. 

![spark mllib](./images/Screenshot%202023-01-08%20at%206.21.31%20PM.png)

Spark MLlib implements many common machine learning algorithms.

## Algorithms supported

Depending on your problem type, whether it be **binary classification**, **multi-class classification**, or **regression**, then you can leverage any of the supported algorithms shown here. 

![spark mllib](./images/Screenshot%202023-01-08%20at%206.22.35%20PM.png)

Later on in our course when we build an end-to-end demonstration, using **Apache Spark** and **MLlib** we'll train our machine learning model using the decision tree algorithm.

## Code Examples

Let's take a quick look at a couple of MLlib code examples. For starters, we will use Scala as the language of choice for both examples. Note, we can also author the same code in either Java or Python. In this particular example, we first load the training data, we then create a data frame containing our labels and features.

![spark mllib](./images/Screenshot%202023-01-08%20at%206.21.49%20PM.png)

Next, we create and initialize a logistic regression model. 

![spark mllib](./images/Screenshot%202023-01-08%20at%206.31.22%20PM.png)

Finally, we train the model and then show the results. In the next example, we train a decision tree model using a 70/30 split for the training and test data. We then test the model for its accuracy in terms of making correct predictions. Finally, we print out the learning decision tree model.

## Summary

Okay, that concludes our basic introduction to Apache MLlib and the machine learning capabilities it provides. As you've just seen, MLlib supports training decision tree models which will be the focus of our next lecture. Go ahead and close this lecture and we'll see you shortly in the next one.
