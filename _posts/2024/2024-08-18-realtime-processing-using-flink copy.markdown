---
layout: "post"
title: "How to create python package"
date: "2024-08-18 01:54"
excerpt: "This is a skeleton template for creating a Python package."
comments: true
---

________________
# How to create python package
_________________

This is a skeleton template for creating a Python package.

_______
## How to do it?
_______

Here is a skeleton code for writing a Python module that can be installed using pip:

```
my_module/
    README.md
    LICENSE
    setup.py
    my_module/
        __init__.py
        module_functions.py
```

- **README.md**: A file that describes your module, including its purpose and usage.
- **LICENSE**: A file that specifies the licensing terms for your module.
- **setup.py**: A file that contains information about your module and its dependencies, as well as instructions for installation using pip.
- **my_module/**: A directory that contains your module's code.
- **__init__.py**: A file that initializes your module and makes its functions and classes available to other Python scripts.
- **module_functions.py**: A file that contains the functions and classes of your module.

In **setup.py**, you will need to include the following code:

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

In **my_module/__init__.py**, you can import your module's functions and classes like this:

```python
from .module_func   tions import my_function, MyClass
```

In **my_module/module_functions.py**, you can define your module's functions and classes:

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

Once you have written your module, you can install it using pip by running the following command in your terminal:

```
pip install /path/to/my_module
```

_________
## How to publish my module to python package index (PyPI) 
_________

Alternatively, you can publish your module to the Python Package Index (PyPI) and make it available for installation using pip by other users.

Here are the steps to publish your Python module to PyPI:

1 . Register for an account on PyPI [https://pypi.org/account/register/](https://pypi.org/account/register/).

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

