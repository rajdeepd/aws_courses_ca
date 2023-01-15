---
attachments: [Clipboard_2022-12-31-19-21-34.png, Clipboard_2022-12-31-19-21-47.png, Clipboard_2022-12-31-19-28-21.png, Clipboard_2022-12-31-19-28-29.png, Clipboard_2022-12-31-19-28-38.png, Clipboard_2022-12-31-19-28-46.png, Clipboard_2022-12-31-19-28-54.png, Clipboard_2022-12-31-19-29-02.png, Clipboard_2022-12-31-19-29-12.png, Clipboard_2022-12-31-19-29-20.png, Clipboard_2022-12-31-19-29-28.png, Clipboard_2022-12-31-19-30-56.png, Clipboard_2022-12-31-19-31-04.png]
tags: [mlc]
title: '6: Machine Learning Concepts: Deep Learning and Deep Neural Networks'
created: '2022-12-31T13:40:37.358Z'
modified: '2023-01-01T04:32:44.449Z'
---

# 6: Machine Learning Concepts: Deep Learning and Deep Neural Networks

## Introduction

Welcome back. And in this lecture, we'll introduce you to deep learning, and deep neural networks as a more specialized form of machine learning. This lecture will be a basic level introduction. Deep neural networks involve a lot of mathematical computation involving aspects of linear algebra, and calculus. In this lecture we'll focus on the higher level concepts. Deep learning is a sub field of machine learning, where its algorithms are inspired by the structure, and design of the human brain. Here the algorithms are known as artificial neural networks.

![](@attachment/Clipboard_2022-12-31-19-21-47.png)

Conceptually the idea of a neural network is quite simple. At its core a neural network is made up of multiple layers of connected neurons. A connection is equivalent to the function of a synapse connecting neurons within a brain. A neuron contains an activation function. Which acts on its inputs from the previous layer, and produces an output value passed along the connections to the neurons in the next layer. As can be seen in this diagram. Taking a closer look at the function, and design of a single neuron. We can see that it does several things.

![](@attachment/Clipboard_2022-12-31-19-28-21.png)

Firstly, it takes several inputs, these are the connections, all weighted here as $W$, within the neural network. Each input has an associated weight, when the neural network is initialized these weights are randomly assigned. The neuron performs a summing function across all the individual products of the inputs $X$, and weights, $W$. The summing function result is then passed through an activation function. To produce an output, $Y$. As we will see, there are several common activation functions that can be used. The same behavior is exhibited by every neuron within a deep neural network.

![](@attachment/Clipboard_2022-12-31-19-28-29.png)

The variables $X^{1}$, $X^{2}$ to $X^{n}$. Hold the data to be evaluated. For example there may be pixel values from an image. Samples from an audio signal. Or stock market prices on successive days, etc. Neurons are organized within three types of layers. An input layer, a hidden layer, and the output layer. A deep neural network, as the name suggests, can have multiple hidden layers. The more hidden layers involved the deeper the neural network becomes. The nodes of the input layer are passive. Meaning they do not modify the data. And in comparison the nodes of the hidden, and output layers are considered active. This means they modify the data as per the summing, and activation functions described in the previous slide.

Activation functions are used within the neurons. The role of the activation function is to add non-linearity into the system. So, that complex problems can be solved. As we will see later on, training a deep neural network involves multiple forward, and backward passes. The backward pass involves a process called back propagation. Or gradient descent. Where the weights on the network are adjusted in order to have the neural network learn or converge to an optimal solution. We'll go onto this in more detail in one of the later slides.

![](@attachment/Clipboard_2022-12-31-19-28-38.png)


For the learning process to occur it's important to understand that the activation functions need to be differentiable. There are several different activation functions. That are commonly used. Such as, the sigmoid, TanH, and rectified linear unit. We'll now dive into the detail for each of these activation functions. The sigmoid activation function has the mathematical form as shown here on this slide. It takes a real valued number, and squashes it into a range between zero and one. Very large negative numbers are pushed towards zero, and very large positive numbers are pushed towards one.

## Sigmoid Function

The sigmoid function was historically the activation function of choice. As it neatly models the binary firing behavior of a neuron. Where one represents the neuron firing, and zero represents the neuron not firing. 

![](@attachment/Clipboard_2022-12-31-19-28-46.png)

In recent times the sigmoid activation function has been surpassed by the behavior, and performance of other activation functions. Note, the sigmoid activation function is none zero centered. Not being zero centered impacts the optimization or learning process, making it harder.


## TanH Function

The TanH activation function has the mathematical form as shown here on this slide. It takes a real valued number and squashes it into a range between negative one, and one. The on or off activation behavior of the TanH function is similar to that of the sigmoid function.

![](@attachment/Clipboard_2022-12-31-19-28-54.png)

But unlike the sigmoid its output is zero centered. For this reason more often than not, the TanH activation function is preferred over the sigmoid activation function. The final activation function we will cover is the rectified linear unit, or ReLu for short. The ReLu activation function has the mathematical form as shown here on this slide. The ReLu has become very popular in recent times. It simply computes the function F of X, equal to either the max of zero, or X itself.

## ReLu function

The ReLu activation function improves on the previous functions by speeding up training. The gradient computation is very simple. Either zero, or one. Depending on the sign of the current value. Optimization and learning within the model converges quicker, as the function no longer needs to perform any exponential multiplication, and, or, division operations. Of which the previous functions needed to.

![](@attachment/Clipboard_2022-12-31-19-29-02.png)

For a deep neural network to learn it needs to measure how accurate the predicated values it makes. It does so by computing a delta between the predicted value outputted from the network, and the actual result. The computed delta is then used to begin a process in which the weights of the network are adjusted, and churned during the next training iteration. The delta itself is computed by using a particular loss function.

## Loss function

![](@attachment/Clipboard_2022-12-31-19-29-12.png)

![](@attachment/Clipboard_2022-12-31-19-29-20.png)
The loss function computes the error for a single training example. loss functions play an important part in deep neural networks. They are used to measure the delta between the predicted value, and the actual label. The delta is a non-negative value. Where the accuracy of the model increases as the delta decreases. The objective of model training is to have the delta tail off towards zero. loss functions come in a variety of forms.

Popular functions include the cross entropy loss function and the main squared error loss function. As shown here the goal of the forward pass, or forward propagation, is to perform calculations on data that is fed forward through the layers. And through each of the connected neurons. The calculations are continually done in sequence through the network. Layer by layer. Until we reach the final output layer. Which outputs a prediction.

## Forward Propagation

Computation starts from the first layer. The input layer. Forward through the hidden layers. All the way to the last layer. The output layer. 

![](@attachment/Clipboard_2022-12-31-19-29-28.png)

As shown here, the goal of the backward pass, or back propagation, is to churn, and adjust each weight in the network in proportion to how much it contributes to the overall error. Iteratively reducing each weight's error margin eventually allows the network to converge to an optimal solution. And as such allows it to produce accurate predictions. This process is how the neural network learns.

## Backward propagation

Computation starts from the last layer, the output layer. In reverse back through the hidden layers. All the way to the first layer. The input layer. 

![](@attachment/Clipboard_2022-12-31-19-30-56.png)

A single backward and forward pass combined together makes for one iteration. An epoch is one complete presentation of the training data set to the neural network. 

![](@attachment/Clipboard_2022-12-31-19-31-04.png)

Neural networks learn, and converge to optimal solutions by training themselves using many, many epochs.

## Summary
That concludes our basic introduction to deep learning, and deep neural networks. In the final lecture, we'll to a quick review of the key points we've addressed within this machine learning concepts course. Go ahead and close this lecture. And we'll see you shortly in the next one.
