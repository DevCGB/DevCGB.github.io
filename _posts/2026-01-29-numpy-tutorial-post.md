---
layout: post
date: 2026-01-29 08:42:00 +0000
image: "/assets/images/numpy.png"
image_alt: "Picture of HTML code"
tags: [python, tutorial, beginner]
---

## How to get started with numpy

In the following article, we will be discussing how to use numpy and some of it's basic functions. Before we look at any functions, it may be useful for me to explain what Numpy is and why it's beneficial for us to use. To quote the Numpy page, it "is the fundemental package for scientific computing in Python". What does this actually mean though?

Below, I have created two normal Python lists:

```python
list_one = [1, 2, 3, 4]
list_two = [5, 6, 7, 8]
```

Let's say we wanted to add these two lists togehter. I'm sure your intuition may be to simply do:

```python
result = list_one + list_two
```

However, this is not the case. The result for this operation would be:

```python
[1, 2, 3, 4, 5, 6, 7, 8]
```

Here, Python is assuming that we want to add (or append) 'list_two' to the end of 'list_one', which of course is not what we're trying to achieve. If we wanted to get the functionality we were actually looking for, we would have to do:

```python
result = [] # Create blank list

for i in range(len(list_one)): # Loop over every item in list_one
    result.append(list_one[i] + list_two[i]) # Add the elements at the same index together
```

This will then give us out desired answer of:

```python
[6, 8, 10, 12]
```

I am sure you can already see the problem here. To do simple addition for two small lists, we have to create a whole seperate ```for``` loop. If there are thousands of elements in the lists, this process can take a really long time, meaning even small programs like the one above are too slow and inefficient to run. Think of it like this, if it takes a few seconds for you to simply add two lists together, imagine how long it will take the rest of your program to run!

### Numpy arrays

Numpy arrays are the solution to this problem. Numpy is a Python library that has preloaded functions that allows us to work with lists (arrays) in a much more efficient way. This library uses C, which is another programming language that allows the developer to manage memory themselves i.e. they can choose where in memory things are stored and how much memory to use (making for very efficient programs). Numpy uses C to make it's functions much faster than they could ever be if they were written in Python. This means that we are able to utilise the easy to use syntax of Python, along with the fast compuatation of C to obtain our desired results.

To use the package, you first have to make sure it's installed. There are many package managers for Python, but the main one is pip (which comes preinstalled with Python). To install Numpy, we simply have to use the command: ```pip install numpy```.

Note: You run this command in the terminal

Let's create a some Numpy arrays:

```python
import numpy as np

list_one = np.array([1, 2, 3, 4])
list_two = np.array([5, 6, 7, 8])
```

There are a few things going on here, so let me explain. First of all, we have the ```import``` line. This let's Python know that we want to use the numpy package in this file; in other words, it just allows us to use Numpy. We have then used ```as np``` after the import statement. This just simply means we want to use np as the identifier rather than numpy. For example:

```python
import numpy as any_word_you_want

list_one = any_word_you_want.array([1, 2, 3, 4])
```

However, with Numpy, the convention is to use np, so it's best to stick to that.

We then come to the lists themselves. We are first calling the function ```.array()``` from Numpy and parsing our list as parameters. This then creates a Numpy array. Now, we're finally able to add the two lists together:

```python
result = list_one + list_two
```

Now, addition isn't the only thing that Numpy is capable of. You can do addition, subtraction, multiplication, division and many more, which you can find on the [Numpy documentation page](https://numpy.org/devdocs/reference/routines.html)

### Other Numpy functions

Numpy is such an enormous library, so I won't be able to cover all of them in this article alone, however, I'll walk you through some other useful functions below.

#### Arange

The first function I want to cover is ```.arange()```. Let's say I want a list that ranges from 1 - 10. In normal Python, you would probably create a for loop for this. As we covered earlier, for loops can be very time consuming for computers to produce. This is where the arange function comes in. We provide the function with two arguments, the first number is where we want to start and the second number is where we want to end. Please note, the second argument is exclusive, so isn't included in the list.

For example:

```python
numbers = np.arange(1, 10)
print(numbers) # This prints 1, 2, 3, 4, 5, 6, 7, 8, 9 (NOT 10)
```

This function can also take a third argument. This argument is known as the 'step'. As an example, let's say we wanted that same list, ranging from 1 - 10, but we wanted to increment by 2 instead of one (e.g. 1, 3, 5, ...). 

```python
numbers = np.arange(1, 10, 2)
print(numbers) # Prints 1, 3, 5, 7, 9
```

Note: The step value doesn't have to be 2. It can be 10, 0.2, 3.93321 etc

#### Linspace

Another useful function is ```.linspace()```. This function can be confused with arange, but they work in slightly different ways. This function also allows us to create lists with populated values, but in linspaces case, it's with evenly spaced numbers. Let's say we wanted an array with 10 numbers that are evenly spaced between 1 and 0; we would do the following:

```python
spaced_numbers = np.linspace(0, 1, num=10)
print(spaced_numbers) # Prints 0, 0.11111111, 0.22222222, 0.33333333, ... , 1
```

Unlike the ```.arange()``` function, linspace includes both arguments provided. This is something to note with packages like Numpy; arguments will vary per function so make sure to read the documentation beforehand.

#### Mean, Median, Mode

Things like mean, median and mode are also possible with Numpy. As we've explained before, these are much faster than conventional Python methods. There are so many different statistical functions that you can do with Numpy, so I do recommend that you read [the documentation for this page](https://numpy.org/devdocs/reference/routines.statistics.html) to see what else is possible.

```python
values = np.arange(1, 11) # Array of integers from 1 - 10
mean = np.mean(values) # mean = 5.5
```

Above we have calculated the mean in just 2 lines, which would be impossible in standard Python. I've only shown you the mean function in this example, but the mode and median functions are the exact same.

### Conclusion

Hopefully after reading this article you can see the benefits of using Numpy and have some understanding on how to use it yourself. This is a fairly big library, so don't worry about learning it all at once. You'll find that as you work through projects, you'll find different use cases for different functions. There are so many that I didn't cover in this article, so do make sure to have a play aronud with it to see what else it can do.