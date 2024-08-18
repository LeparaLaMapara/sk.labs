---
layout: "post"
title: "How to use conda and pip to install packages within Jupyter notebook?"
date: "2019-03-10 11:04"
excerpt: "Netcool is an IBM software product that provides network and service management capabilities, including event management, fault management, and performance management."
comments: true
---


![Conda and Pip Image](images\jupyter_notebooks\jupyter-notebook.png)

## Pip vs. Conda

Conda and pip are often considered as being the same. Although some of the functionality of these two tools overlap, they were designed and should be used for different purposes. Their difference is most related to the environment:

- **pip** installs Python packages in any environment.
- **conda** installs any package in conda environments.

Whether to use conda or pip depends on how you installed Python, and then the choice on which to use:

- If you installed Python using Anaconda or Miniconda, then use conda to install Python packages. If conda tells you the package you want doesn't exist, then use pip (or try conda-forge, which has more packages available than the default conda channel).
- If you installed Python any other way (from source, using pyenv, virtualenv, etc.), then use pip to install Python packages.

Finally, because it often comes up, I should mention that you should NEVER use `sudo pip install`.

It will always lead to problems in the long term, even if it seems to solve them in the short term. For example, if `pip install` gives you a permission error, it likely means you're trying to install/update packages in a system Python, such as `/usr/bin/python`. Doing this can have bad consequences, as often the operating system itself depends on particular versions of packages within that Python installation. For day-to-day Python usage, you should isolate your packages from the system Python, using either virtual environments or Anaconda/Miniconda—I personally prefer conda for this, but I know many who prefer virtualenv.

## How to Use Conda from the Jupyter Notebook

If you’re in the Jupyter notebook and you want to install a package with conda, you might be tempted to use the `!` notation to run conda directly as a shell command from the notebook:

```python
# Don't do this
!conda install pandas --yes OR !pip install pandas
```

Note that we use `--yes` to automatically answer `y` if and when conda asks for user confirmation. This will not generally work. Here is a short snippet that should work in general:

```python
# Dont do this
import sys
!{sys.executable} -m pip install pandas
```

That bit of extra boiler-plate makes certain that you are running the pip version associated with the current Python kernel, so that the installed packages can be used in the current notebook.


## Conclusion

In this post, I tried to answer once and for all the perennial question: How do I install Python packages in the Jupyter notebook?

## Resources
1.  [Understanding Conda and Pip](https://www.anaconda.com/understanding-conda-and-pip/)
2.  [Conda: Myths and Misconceptions](https://jakevdp.github.io/blog/2016/08/25/conda-myths-and-misconceptions/)
3.  [Installing Python Packages from a Jupyter Notebook](http://jakevdp.github.io/blog/2017/12/05/installing-python-packages-from-jupyter/#pip-vs.-conda)

