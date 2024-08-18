---
layout: "post"
title: "How to Create a Python Package: My Journey from Curiosity to Implementation"
date: "2024-08-18 01:54"
excerpt: "This is a skeleton template for creating a Python package."
comments: true
---

# How to Create a Python Package 🐍

You know, I’ve always been curious about how Python packages are made—like, who’s the wizard behind the curtain? It’s kind of like wondering how One Piece’s Devil Fruits get their powers (but without the whole turning into rubber thing). 😂

It all started when I was working at Vodacom, and my manager, Jaco Du Toit, introduced me to this whole new world of probabilistic machine learning. He was all about using it for operational data in network management because, let’s be honest, that data is noisier than a group of ninjas trying to sneak through Konoha at night. 🥷

So, I thought, “Hey, why not challenge myself?” I remembered Richard Feynman once said something like, “If you can’t explain it simply, you don’t understand it.” (Or was it “If you can’t explain it to a five-year-old…?” Meh, same difference, right? 🤷‍♂️). Anyway, I decided the best way to deepen my understanding was to actually create a Python package. And let me tell you, it was a wild ride!

## How to Do It? 🚀

Alright, here’s how you can create your own Python package. It’s kind of like putting together a pirate crew—you need all the right pieces to make it work. Here’s your skeleton code:



```
my_module/
    README.md
    LICENSE
    setup.py
    my_module/
        __init__.py
        module_functions.py
```

### What’s in the Package? 📦

- **README.md**: Think of this as your map to the Grand Line. It describes your module, what it does, and how people can use it.
- **LICENSE**: This is like your Pirate Code. It specifies the terms under which others can use your module.
- **setup.py**: This is your Log Pose—your guide to installing the package with `pip`. It contains all the information about your module and its dependencies.
- **my_module/**: This is the heart of your ship, where all your code lives.
- **\_\_init\_\_.py**: This is the navigator (hello, Nami!), initializing your module and making its functions and classes available to other Python scripts.
- **module_functions.py**: This is where the magic happens—your treasure chest of functions and classes.

### Let’s Write Some Code! 💻

Here’s what your **setup.py** file might look like:

```python
from setuptools import setup, find_packages

setup(
    name='my_module',
    version='0.1',
    author='Your Name',
    author_email='your.email@example.com',
    description='A short description of your module',
    long_description=open('README.md').read(),
    url='https://github.com/your-username/my_module',
    packages=find_packages(),
    install_requires=[
        'numpy',
        'scipy',
        # other dependencies
    ],
    classifiers=[
        'Development Status :: 3 - Alpha',
        'Intended Audience :: Developers',
        'License :: OSI Approved :: MIT License',
        'Programming Language :: Python :: 3',
        'Programming Language :: Python :: 3.6',
        'Programming Language :: Python :: 3.7',
        'Programming Language :: Python :: 3.8',
    ],
)

```

And **my_module/__init__.py**, you can import your module's functions and classes like this:

```python
from .module_functions import my_function, MyClass
```

Finally, in **my_module/module_functions.py**,  here’s where you can define your functions and classes:

```python
import numpy as np

def my_function(arg1, arg2):
    """
    A short description of your function.

    Parameters
    ----------
    arg1 : int
        Description of arg1.
    arg2 : numpy.ndarray
        Description of arg2.

    Returns
    -------
    numpy.ndarray
        Description of the return value.
    """
    # function code here
    pass

class MyClass:
    def __init__(self, arg1, arg2):
        """
        A short description of your class.

        Parameters
        ----------
        arg1 : int
            Description of arg1.
        arg2 : numpy.ndarray
            Description of arg2.
        """
        # class initialization code here
        pass

    def my_method(self, arg):
        """
        A short description of your method.

        Parameters
        ----------
        arg : int
            Description of arg.

        Returns
        -------
        numpy.ndarray
            Description of the return value.
        """
        # method code here
        pass
```


## Time to Install It! 🛠️
Once you’ve written your module, you can install it using `pip`. Just run this in your terminal:
```
pip install /path/to/my_module
```
And boom, you’re ready to go—like setting sail with your new ship!

_________
## How to Publish Your Module to Python Package Index (PyPI) 🚢
_________

So, you want to share your treasure with the world, huh? Here’s how you can publish your Python module to PyPI:

Here are the steps to publish your Python module to PyPI:

1 . Register for an account on PyPI [https://pypi.org/account/register/](https://pypi.org/account/register/). It’s like getting your pirate flag ready. 🏴‍☠️

1. Install `twine` and `setuptools` by running the following commands in your terminal:
    ```
    pip install twine setuptools
    ```

2. In your module's root directory, create a `setup.py` file that contains information about your module and its dependencies, as well as instructions for installation using pip. See the example code in my previous answer for a skeleton `setup.py` file.

3. In your terminal, navigate to your module's root directory and run the following command to create a source distribution package:
    ``` 
    python setup.py sdist
    ```
    This will create a `.tar.gz` file in the `dist` directory.

4. Run the following command to create a wheel distribution package:
    ```
    python setup.py bdist_wheel
    ```
    This will create a `.whl` file in the `dist` directory.

5. Verify that your distribution packages are valid by running the following command:
    ```
    twine check dist/*
    ```

6. Upload your distribution packages to PyPI by running the following command and entering your PyPI credentials when prompted:
    ```
    twine upload dist/*
    ```
    
    This will upload your distribution packages to PyPI and make them available for installation using pip.


Once you have successfully published your module to PyPI, users can install it using pip by running the following command:

```
pip install my_module
```

where **my_module** is the name of your module as specified in your **setup.py** file.

And that’s it! You’ve just created and published your very own Python package. Now go out there and make Richard Feynman (and Jaco!) proud. 😉

So that’s how you create a Python package, my friend. It’s like setting off on your own little adventure, learning along the way, and maybe even finding a few treasures (or bugs) here and there. 🍀

# My 1st Package 🎉

So after all that hard work and plenty of *Kamehameha* energy, I finally created my first Python package! It's called [Bayesian Filtering Package](https://pypi.org/project/tfilterpy/). It’s pretty basic—kind of like Goku when he first landed on Earth, but the goal was just to go Super Saiyan on my understanding of how this whole package thing is done. 💪

Hmm, should I make a detailed post about it? Maybe. But I guess you’ll just have to *tune in next time on Dragon Ball Z* to find out... Will Thabang master the art of Python packaging? Will his code stand the test of time? Or will he face a new bug that makes him power up for three episodes straight? Stay tuned! 😉
