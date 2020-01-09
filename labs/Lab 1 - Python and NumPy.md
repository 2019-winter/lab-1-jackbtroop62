---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.1'
      jupytext_version: 1.2.4
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Name(s)
**PUT YOUR FULL NAME(S) HERE**


**Instructions:** This is an individual assignment, but you may discuss your code with your neighbors.


# Python and NumPy

While other IDEs exist for Python development and for data science related activities, one of the most popular environments is Jupyter Notebooks.

This lab is not intended to teach you everything you will use in this course. Instead, it is designed to give you exposure to some critical components from NumPy that we will rely upon routinely.

## Exercise 0
Please read and reference the following as your progress through this course. 

* [What is the Jupyter Notebook?](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/What%20is%20the%20Jupyter%20Notebook.ipynb#)
* [Notebook Tutorial](https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook)
* [Notebook Basics](https://nbviewer.jupyter.org/github/jupyter/notebook/blob/master/docs/source/examples/Notebook/Notebook%20Basics.ipynb)

**In the space provided below, what are three things that still remain unclear or need further explanation?**


How efficient is the python interpreter in a notebook, compared to using python in a cli? how does jupyter notebook handle version changes in python? do notebooks support other languages?


## Exercises 1-7
For the following exercises please read the Python appendix in the Marsland textbook and answer problems A.1-A.7 in the space provided below.


## Exercise 1

```python
# YOUR SOLUTION HERE

import numpy as np
a = np.ones((6,4)) * 2
print(a)
```

## Exercise 2

```python
# YOUR SOLUTION HERE
b = np.ones((6, 4)) + (np.eye(6, 4) * 2)
print(b)

```

## Exercise 3

```
a*b does element by element multiplication. matrix multiplication requires the inner dimensions must match.
```

## Exercise 4

```python
print(np.dot(np.transpose(a), b))
print(np.dot(a,np.transpose(b)))
# transposing an array makes it a completely different array, causing different operations for each cell
```

## Exercise 5

```python
def f():
  print("this is my function")
f()
```

## Exercise 6

```python
def rand():
    c = np.random.randint(0,10,(5, 5))
    print(c)
    print("sum: " + str(np.sum(c)))
    print("mean: " + str(np.sum(c)/25))
rand()
rand()
rand()
```

## Exercise 7

```python
def count_one(arr):
    count = 0;
    for a in range(len(arr)):
        if(arr[a] == 1):
            count += 1
    return count

def count_one_better(arr):
    c = np.where(arr == 1, arr, 0)
    return np.sum(c)
    
print(count_one_better(np.arange(10)))
print(count_one(np.arange(10)))
```

## Excercises 8-???
While the Marsland book avoids using another popular package called Pandas, we will use it at times throughout this course. Please read and study [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/getting_started/10min.html) before proceeding to any of the exercises below.


## Exercise 8
Repeat exercise A.1 from Marsland, but create a Pandas DataFrame instead of a NumPy array.

```python
import pandas as pd
import numpy as np
a = pd.DataFrame(pd.DataFrame(np.ones((6, 4)) * 2, columns=list('ABCD')))
print(a)
```

## Exercise 9
Repeat exercise A.2 using a DataFrame instead.

```python
a = pd.DataFrame(pd.DataFrame(np.ones((6, 4)) + (np.eye(6, 4) * 2), columns=list('ABCD')))
print(a)
```

## Exercise 10
Repeat exercise A.3 using DataFrames instead.

```python
# YOUR SOLUTION HERE
```

## Exercise 11
Repeat exercise A.7 using a dataframe.

```python
# YOUR SOLUTION HERE
```

## Exercises 12-14
Now let's look at a real dataset, and talk about ``.loc``. For this exercise, we will use the popular Titanic dataset from Kaggle. Here is some sample code to read it into a dataframe.

```python
titanic_df = pd.read_csv(
    "https://raw.githubusercontent.com/dlsun/data-science-book/master/data/titanic.csv"
)
titanic_df
```

Notice how we have nice headers and mixed datatypes? That is one of the reasons we might use Pandas. Please refresh your memory by looking at the 10 minutes to Pandas again, but then answer the following.


## Exercise 12
How do you select the ``name`` column without using .iloc?

```python

titanic_df['name']
```

## Exercise 13
After setting the index to ``sex``, how do you select all passengers that are ``female``? And how many female passengers are there?

```python
titanic_df.set_index('sex', inplace=True)
titanic_df.loc['female']
```

## Exercise 14
How do you reset the index?

```python
## YOUR SOLUTION HERE
```

```python

```
