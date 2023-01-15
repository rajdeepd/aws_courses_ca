---
tags: [dmli]
title: '7: First Deep Learning Model'
created: '2023-01-01T15:31:07.437Z'
modified: '2023-01-02T14:06:53.369Z'
---

# 7: First Deep Learning Model

Hello, and welcome to our first coding session. In this video, we'll familiarize with the IPython Notebook Environment and we will run a first deep learning model. Don't worry if you don't understand everything in the code, because this is just to wet your appetite. And we will have plenty of occasions in the course to actually understand what we are doing. The Jupyter Notebook is an interactive environment that allows us to execute Python code in cells. This, for example, is a cell, but this too is a cell. This is a markdown cell that we can use to add text to comment our work. Comment our work. If I double click on a cell, the cell becomes active and I can edit it. For example, I can change this and say author. For example, I can change this and add a word. Hello, this is our first model. To execute the cell, I can either hit cell run, which will run it or, more simply, I can hit shift return. This will also run the cell. Running a markdown cell just renders it in markdown. 

Running a cell that contains code executes the code contained in the cell. If I run a cell with an error, the error will be shown. If you're new to Python, it's important that you understand how to read error messages. The most important part of an error message is the last part. Here it's saying SyntaxError, invalid syntax. And then it indicates where the problem is. In this case, since there's only a line, it's very simple to correct the error. 


![](@attachment/Screenshot 2023-01-01 at 8.57.12 PM.png)

But keep in mind that when there's a long error message always look for the last message or the last line first. That contains the clue of solving the problem. Okay, so the first line here imports numpy, which is the library that contains all the linear algebra functions, like vectors, matrices, and so on. It's always good to import it when you're doing data work. 


Then, in this cell, we import matplotlib and use a cell magic. 

```python
%matplotlib inline
import matplotlib.pyplot as plt
```
A cell magic is a very special IPython construct that allows us to add functionality to the IPython Notebook Environment. In this particular case, we are setting the inline instruction to the matplotlib plotter. What this means is that, when we generate the plot using matplotlib, it will be displayed in the notebook itself. 
Then we import a generator of samples from a library called scikit-learn. **Scikit-learn** is Python's primary machine learning library and it comes with a lot of utilities like, for example, a data samples generator.

```python
from sklearn.datasets import make_circles
```
 We import the make_circles and you will understand immediately what this does. 

> **_NOTE:_**  
 def make_circles(
    n_samples=100, *, shuffle=True, noise=None, random_state=None, factor=0.8
):
    """Make a large circle containing a smaller circle in 2d.
    A simple toy dataset to visualize clustering and classification
    algorithms.
    Read more in the :ref:`User Guide <sample_generators>`.
    Parameters
    ----------
    n_samples : int or tuple of shape (2,), dtype=int, default=100
        If int, it is the total number of points generated.
        For odd numbers, the inner circle will have one point more than the
        outer circle.
        If two-element tuple, number of points in outer circle and inner
        circle.
        .. versionchanged:: 0.23
           Added two-element tuple.
    shuffle : bool, default=True
        Whether to shuffle the samples.
    noise : float, default=None
        Standard deviation of Gaussian noise added to the data.
    random_state : int, RandomState instance or None, default=None
        Determines random number generation for dataset shuffling and noise.
        Pass an int for reproducible output across multiple function calls.
        See :term:`Glossary <random_state>`.
    factor : float, default=.8
        Scale factor between inner and outer circle in the range `(0, 1)`.
    Returns
    -------
    X : ndarray of shape (n_samples, 2)
        The generated samples.
    y : ndarray of shape (n_samples,)
        The integer labels (0 or 1) for class membership of each sample.

In the next cell, we call the `make_circles` function with some parameters, let's look at them. We have number of samples, we say `1000`, a certain level of noise, a `factor of 0.2` and we'll see what that means, and we also set the `random_state`. Don't worry about this. 

You can find more details here:

```python
X, y = make_circles(n_samples=1000,
                    noise=0.1,
                    factor=0.2,
                    random_state=0)
```

What's important is that this function has two outputs. We assign them to the variables X and y. So let's look at X first. X is a matrix, so it has rows and columns, and if we look at the shape, it has 1000 rows and two columns. 

![](@attachment/Screenshot 2023-01-01 at 8.58.10 PM.png)

This corresponds to the number of samples and we have two features for each sample. Let's plot the values of X and let's plot them in two different colors. In blue, for the points of X that correspond to y equals to zero and in red, with a cross, for the points that corresponds to the label of y equals to one. 

![](@attachment/Screenshot 2023-01-01 at 8.58.27 PM.png)

This is our training data. We have data on the outer circle, that belongs to a certain class, and data in the inner space here the crosses that is belongs to the other class. In machine learning, we often want to train models to separate two classes. In this case, a model should learn that there is kind of a circular boundary between the red crosses and the blue dots. Now, let's go ahead build our first deep learning model. I will not explain what each of these line does, because we will go through these for the rest of the course. 

Let's just see how simple it is to define a deep learning model. It's literally these three lines, where we import the relevant classes from keras. 

```python
from tensorflow.keras.models import Sequential
from tensorflow.keras.layers import Dense
from tensorflow.keras.optimizers import SGD
```
Keras is the library we will use for the whole course for doing deep learning. And then one, two, three, four, four lines to define the model and a fifth line to fit the model. Now, what's important is, when you execute the line that fits the model on the training data `X` and `y`, you can define a number of `epochs` and we will learn what these are in the course. 

![](@attachment/Screenshot 2023-01-01 at 9.37.29 PM.png)



Now, focus your attention on the output here.
```
Epoch 1/20
32/32 [==============================] - 1s 8ms/step - loss: 0.6934 - accuracy: 0.6410
Epoch 2/20
32/32 [==============================] - 0s 5ms/step - loss: 0.6143 - accuracy: 0.7760
Epoch 3/20
32/32 [==============================] - 0s 6ms/step - loss: 0.5001 - accuracy: 0.8540
Epoch 4/20
32/32 [==============================] - 0s 6ms/step - loss: 0.3740 - accuracy: 0.9140
Epoch 5/20
....
Epoch 14/20
32/32 [==============================] - 0s 6ms/step - loss: 0.0571 - accuracy: 1.0000
Epoch 15/20
32/32 [==============================] - 0s 6ms/step - loss: 0.0521 - accuracy: 1.0000
Epoch 16/20
32/32 [==============================] - 0s 6ms/step - loss: 0.0481 - accuracy: 1.0000
Epoch 17/20
32/32 [==============================] - 0s 5ms/step - loss: 0.0446 - accuracy: 1.0000
Epoch 18/20
32/32 [==============================] - 0s 6ms/step - loss: 0.0416 - accuracy: 0.9990
Epoch 19/20
32/32 [==============================] - 0s 6ms/step - loss: 0.0390 - accuracy: 0.9990
Epoch 20/20
32/32 [==============================] - 0s 5ms/step - loss: 0.0367 - accuracy: 1.0000
```

The output here tells us a certain number, loss, which seems to be decreasing over time. And another number, called acc, which stands for accuracy, which seems to increasing over time. Again, we will have the whole course to learn about these numbers and what they mean, but keep in mind this, we are running a fitting procedure over a thing called epoch. So first epoch, second epoch, third epoch, et cetera. 

And a number called loss is decreasing, while a number called accuracy is increasing. Now, what we do in the rest of the notebook is just to draw the decision boundary of our model. 

To do this, we define a grid of points using a function from numpy called `linspace`. Linspace generates a sequence of numbers, exactly in this case 101 numbers, between the minimum value of `minus 1.5` and the maximum value of `1.5`. We call these horizontal ticks. And then we have vertical ticks, which have the same grid space. Then we do a bit of manipulation here to generate the grid of points that we end up called `ab`. So `ab` is a grid of points that, both in X and y, are have coordinates between minus 1.5 and 1.5. 

```python
hticks = np.linspace(-1.5, 1.5, 101)
vticks = np.linspace(-1.5, 1.5, 101)
aa, bb = np.meshgrid(hticks, vticks)
ab = np.c_[aa.ravel(), bb.ravel()]
c = model.predict(ab)
cc = c.reshape(aa.shape)
```

Then we predict, with our model, the values of the grid and we reshape the prediction to have the same shape as the grid. Don't worry if you don't understand this line. It's just boilerplate in order to generate the next figure. In the next figure, we plot the same data and we overlay a contour function, a contour plot, of our prediction grid. 

```python
plt.figure(figsize=(5, 5))
plt.contourf(aa, bb, cc, cmap='bwr', alpha=0.2)
plt.plot(X[y==0, 0], X[y==0, 1], 'ob', alpha=0.5)
plt.plot(X[y==1, 0], X[y==1, 1], 'xr', alpha=0.5)
plt.xlim(-1.5, 1.5)
plt.ylim(-1.5, 1.5)
plt.legend(['0', '1'])
plt.title("Blue circles and Red crosses")
```
As you can see, our model has learned a profile that separates really well the internal red crosses from the outer blue dots.

![](@attachment/boundary_prediction.png)

I hope this served to wet your appetite. Maybe you've not understood everything, but I hope I've convinced you that building a deep learning model with keras is actually very, very simple. Before I go, I want to teach you a little trick of IPython Notebook. If you're in a cell, you can see that the cell is surrounded by a green rectangle. If you hit the button escape, the rectangle becomes blue, light blue. This means we are in notebook mode and in notebook mode, we can access some keyboard shortcuts to facilitate our navigation of the notebook environment. The most important shortcut is the letter h. If I press h in notebook mode, it will display all the keyboard shortcuts in a help. So look how many keyboard shortcuts there are. I strongly encourage you to have looked at these keyboard shortcuts. In particular, how to run a cell. We've already seen that, it's shift return. But also how to add cells and how to delete cells. This will make you very proficient in the use of IPython Notebook. Thank you for watching and see you in the next video.
