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

```python

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
## [Array](http://scipy-lectures.org/intro/numpy/array_object.html) Creation
There are several ways to create arrays.

For example, you can create an array from a regular Python list or tuple using the array function. 
The type of the resulting array is deduced from the type of the elements in the sequences.
```python
>>> import numpy as np
>>> a = np.array([2,4,6])
>>> a
array([2, 4, 6])
>>> a.dtype
dtype('int64')
>>> b = np.array([1.2, 3.5, 5.1, 4.2, 6.9])
>>> b.dtype
dtype('float64')
```
A frequent error consists in calling array with multiple arguments, rather than providing a single sequence as an argument.
```python
>>> x = np.array(1, 2, 3, 4)                            #THIS IS WRONG
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: array() takes from 1 to 2 positional arguments but 4 were given
>>> x = np.array([1, 2, 3, 4])                          #THIS IS RIGHT
>>> x
array([1, 2, 3, 4])
```
array transforms sequences of sequences into two-dimensional arrays, sequences of sequences of sequences into three-dimensional arrays, and so on.
```python
>>> y = np.array([(1, 3, 5), (2, 4, 6)])
>>> y
array([[1, 3, 5],
       [2, 4, 6]])
```
The type of the array can also be explicitly specified at creation time:
```python
>>> m = np.array([(1, 3, 5), (2, 4, 6)], dtype=complex)
>>> m
array([[1.+0.j, 3.+0.j, 5.+0.j],
       [2.+0.j, 4.+0.j, 6.+0.j]])
```
The function ```zeros``` creates an array full of zeros, the function ones creates an array full of ones, and the function empty creates an array whose initial content is random and depends on the state of the memory. By default, the dtype of the created array is ```float64```.
```python
>>> np.zeros((2,3))
array([[0., 0., 0.],
       [0., 0., 0.]])
>>> np.ones((2,3,5), dtype=np.int32)                            # dtype can also be specified
array([[[1, 1, 1, 1, 1],
        [1, 1, 1, 1, 1],
        [1, 1, 1, 1, 1]],

       [[1, 1, 1, 1, 1],
        [1, 1, 1, 1, 1],
        [1, 1, 1, 1, 1]]], dtype=int32)
>>> np.empty( (2,3) )                                          # uninitialized
array([[6.93223152e-310, 6.93223152e-310, 0.00000000e+000],
       [0.00000000e+000, 8.92896519e+271, 7.20185289e+159]])

```
See More :

[array](https://numpy.org/doc/stable/reference/generated/numpy.array.html#numpy.array), 
[zeros](https://numpy.org/doc/stable/reference/generated/numpy.zeros.html#numpy.zeros), 
[zeros_like](https://numpy.org/doc/stable/reference/generated/numpy.zeros_like.html#numpy.zeros_like), 
[ones](https://numpy.org/doc/stable/reference/generated/numpy.ones.html#numpy.ones), 
[ones_like](https://numpy.org/doc/stable/reference/generated/numpy.ones_like.html#numpy.ones_like), 
[empty](https://numpy.org/doc/stable/reference/generated/numpy.empty.html#numpy.empty), 
[empty_like](https://numpy.org/doc/stable/reference/generated/numpy.empty_like.html#numpy.empty_like), 
[arange](https://numpy.org/doc/stable/reference/generated/numpy.arange.html#numpy.arange), 
[linspace](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html#numpy.linspace), 
numpy.random.Generator.rand, numpy.random.Generator.randn, 
[fromfunction](https://numpy.org/doc/stable/reference/generated/numpy.fromfunction.html#numpy.fromfunction), 
[fromfile](https://numpy.org/doc/stable/reference/generated/numpy.fromfile.html#numpy.fromfile)


