# Numpy Introductino :
NumPy is the fundamental package for scientific computing in Python.
It is a Python library that provides a multidimensional array object, various derived objects (such as masked arrays and matrices),
and an assortment of routines for fast operations on arrays, including mathematical, logical, shape manipulation, sorting, selecting, 
I/O, discrete Fourier transforms, basic linear algebra, basic statistical operations, random simulation and much more.
### Prerequisites
You’ll need to know a bit of Python. For a refresher, see the Python tutorial.

To work the examples, you’ll need matplotlib installed in addition to NumPy.

#### Learner profile

This is a quick overview of algebra and arrays in NumPy. 
It demonstrates how n-dimensional (n>=2) arrays are represented and can be manipulated.
In particular, if you don’t know how to apply common functions to n-dimensional arrays (without using for-loops),
or if you want to understand axis and shape properties for n-dimensional arrays, this article might be of help.

#### Learning Objectives

After reading, you should be able to:

Understand the difference between one-, two- and n-dimensional arrays in NumPy;

Understand how to apply some linear algebra operations to n-dimensional arrays without using for-loops;

Understand axis and shape properties for n-dimensional arrays.

### Basics 
NumPy’s main object is the homogeneous multidimensional array. 
It is a table of elements (usually numbers), all of the same type, indexed by a tuple of non-negative integers. 
In NumPy dimensions are called axes.

NumPy’s array class is called ndarray. It is also known by the alias array.
Note that numpy.array is not the same as the Standard Python Library class array.array, which only handles one-dimensional arrays and offers less functionality. 
The more important attributes of an ndarray object are:

#### ndarray.ndim

the number of axes (dimensions) of the array.

#### ndarray.shape

the dimensions of the array. 
This is a tuple of integers indicating the size of the array in each dimension. 
For a matrix with n ``rows`` and m ``columns``, ``shape`` will be (n,m). The length of the shape tuple is therefore the number of axes, ``ndim``.

#### ndarray.size

the total number of elements of the array. This is equal to the product of the elements of shape.

#### ndarray.dtype

an object describing the type of the elements in the array. 
One can create or specify dtype’s using standard Python types.
Additionally NumPy provides types of its own. ``numpy.int32``, ``numpy.int16``, and ``numpy.float64`` are some examples.

#### ndarray.itemsize

the size in bytes of each element of the array. 
For example, an array of elements of type ``float64`` has itemsize 8 (=64/8), while one of type ``complex32`` has itemsize 4 (=32/8). 
It is equivalent to ``ndarray.dtype.itemsize``.

#### ndarray.data
the buffer containing the actual elements of the array.
Normally, we won’t need to use this attribute because we will access the elements in an array using indexing facilities.

## An Example

```

>>> import numpy as np
>>> a = np.arange(12).reshape(3, 4)
>>> a
array([[ 0,  1,  2,  3],
       [ 4,  5,  6,  7],
       [ 8,  9, 10, 11]])
>>> a.ndim
2
>>> a.shape
(3, 4)
>>> a.size
12
>>> a.dtype
dtype('int64')
>>> a.itemsize
8
>>> a.data
<memory at 0x7f1764151380> 

```
## Array Creation