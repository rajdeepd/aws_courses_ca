---
tags: [dmli]
title: '5: Setup Walkthrough'
created: '2023-01-01T08:33:25.765Z'
modified: '2023-01-01T13:20:43.970Z'
---

# 5: Setup Walkthrough

Hello everyone. In this video, we're going to see how to download the course material and how to set up your laptop for the course. So let's start from the course material. In order to obtain the code for this course, you have to go to GitHub and point your browser to `github.com/Dataweekends/zero_to_deep_learning_video`. Once you reach our page, you will see the course repository. The instructions you're going to follow are detailed in the read me file of the video course. So all you need to do is just follow the instructions and you'll be up and running in no time.
	
![](@attachment/Screenshot 2023-01-01 at 2.02.16 PM.png)	

The first thing you've got to do is to clone the repository on your laptop. So we are going to copy this command line here 

```
git clone https://github.com/Dataweekends/zero_to_deep_learning_video.git
```
which is `git clone` and the URL of the course, and we're going to paste it into a terminal. If you are on Windows, you are going to do exactly the same thing. You're going to clone the repository, and you do that in the Anaconda Prompt that you will find if you have installed Anaconda. So we paste the same line in Windows and this will give us the same results.

Once we have downloaded the repository, of course we have already downloaded and installed Anaconda, so the next step is to change to the course folder and to create the environment. So I'll go ahead and do this on both machines, so I'll do this conda env create on my Mac, as well as on Windows, 
`cd zero_to_deep_learning_video`, and then 

```
conda env create
```

While it's running, let me explain what's going on here. So we have provided in the repository an environment file which contains all the necessary packages for the course to run smoothly. 

![](@attachment/Screenshot 2023-01-01 at 2.33.23 PM.png)
![](@attachment/Screenshot 2023-01-01 at 2.34.39 PM.png)

So as you can see, it has a name, `ztdl`, which is the name of the environment, and a list of dependencies. All these dependencies come with Anaconda, so we have Python 3.6 and a set of libraries including scikit-learn and tensorflow. 

We also installed keras, the most recent version, from pip, and that's why it's included as a pip dependency instead of an Anaconda dependency. Environment creation takes a few minutes, so give it the time to complete and come back to the video once the environment is created. 

![](@attachment/Screenshot 2023-01-01 at 2.39.01 PM.png)

Once the environment is created, you should see these lines that say, "To activate this environment, use the `conda activate` command as shown below 

```
conda activate ztdl
```

On Windows, the same thing should appear, so it's exactly the same command as explained in the instruction. As you can see the next command is precisely conda activate ztdl. 

![](@attachment/Screenshot 2023-01-01 at 2.39.36 PM.png)

So let's go ahead and do it, conda activate ztdl, and you shall see that this changes your command prompt to ztdl in parenthesis at the beginning. On Windows, exactly the same thing happens, `conda activate ztdl`. This will change the command prompt to the ztdl environment. This tells us that we are running Python from within the ztdl environment that we have just created, which is a correct thing. 

> **_NOTE:_**  Please refer to the link below for installing Tensorflow on Macbook M1 Max https://developer.apple.com/metal/tensorflow-plugin/

The next step in the instructions is to launch Jupyter notebook. So we'll go ahead and type jupyter notebook in the command prompt.

I'll do the same thing here, 

```
jupyter notebook
```
This will start the notebook server in the backend as well as launch your browser. Once your browser opens, you will see that it opens to a page containing the content of the course repository. So you'll see all the folders you've cloned on your local environment replicated here, and all you've got to do is open the course folder and run the first notebook. On Windows, the same thing will happen, it should open your default browser and show you the course content. If you click on course, you can open the first notebook and get up and running. 

If we open that `0_Check_Environment`, on the path 

http://localhost:8888/notebooks/course/0_Check_Environment.ipynb

This notebook performs a few checks and makes sure that you're running the notebooks from the correct environment. So what you're going to do is click on Cell, Run All,and if everything is done correctly, you should see that you're running Python 3.6 or above from within your environment folder you're running Jupyter, and this cell should evaluate to Houston we are go! That means that all the packages are in the correct major version. 

```python
import pip
import numpy
import jupyter
import matplotlib
import sklearn
import scipy
import pandas
import PIL
import seaborn
import tensorflow

print(1)
def check_version(pkg, version):
    
    actual = pkg.__version__.split('.')
    print(actual)
    if len(actual) == 3:
        actual_major = '.'.join(actual[:2])
    elif len(actual) == 2:
        actual_major = '.'.join(actual)
    else:
        raise NotImplementedError(pkg.__name__ +
                                  "actual version :"+
                                  pkg.__version__)
    try:
        assert(actual_major >= version)
    except Exception as ex:
        print("{} {}\t=> {}".format(pkg.__name__,
                                    version,
                                    pkg.__version__))
        raise ex

check_version(pip, '21.0')
check_version(numpy, '1.19')
check_version(matplotlib, '3.3')
check_version(sklearn, '0.24')
check_version(scipy, '1.6')
check_version(pandas, '1.2')
check_version(PIL, '8.2')
check_version(seaborn, '0.11')
check_version(tensorflow, '2.5')

print("Houston we are go!")
```

If you see an error here, then go back to the read me and look at the Troubleshooting instructions. We've provided instructions for the most common failure modes including how to deactivate the environment, how to remove the environment, how to update conda, as well as instructions on how to run the course in a GPU-enabled environment. So make sure to check the read me and you'll be good to go. 

For my environment i got the following output

```
['22', '3', '1']
['1', '24', '1']
['3', '6', '2']
['1', '2', '0']
['1', '9', '3']
['1', '5', '2']
['9', '3', '0']
['0', '12', '2']
['2', '9', '0']
Houston we are go!
```

## Summary

This concludes the instructions on how to get the code and how to get your machine up and running. I'll see you in the next video.

