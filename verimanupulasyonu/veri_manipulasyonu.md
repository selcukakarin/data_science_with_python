# Neden NumPy?


```python
a = [1,2,3,4]
b = [2,3,4,5]
```


```python
ab = []                        

for i in range(0, len(a)):
  ab.append(a[i]*b[i])

ab
```




    [2, 6, 12, 20]




```python
import numpy as np
```


```python
a = np.array([1,2,3,4])
b = np.array([2,3,4,5])
```


```python
a * b
```




    array([ 2,  6, 12, 20])



# NumPy Array'i Oluşturmak


```python
import numpy as np
```


```python
np.array([1,2,3,4,5])
```




    array([1, 2, 3, 4, 5])




```python
a = np.array([1,2,3,4,5])
```


```python
type(a)
```




    numpy.ndarray




```python
np.array([3.14, 4, 2, 13], dtype = "int")
```




    array([ 3,  4,  2, 13])




```python
#sifirdan array olusturma 
```


```python
np.zeros(10, dtype = int)
```




    array([0, 0, 0, 0, 0, 0, 0, 0, 0, 0])




```python
np.ones((3,5), dtype = int)
```




    array([[1, 1, 1, 1, 1],
           [1, 1, 1, 1, 1],
           [1, 1, 1, 1, 1]])




```python
np.full((3,5), 3)
```




    array([[3, 3, 3, 3, 3],
           [3, 3, 3, 3, 3],
           [3, 3, 3, 3, 3]])




```python
np.arange(0,31, 3)
```




    array([ 0,  3,  6,  9, 12, 15, 18, 21, 24, 27, 30])




```python
np.linspace(0,1,10)
```




    array([0.        , 0.11111111, 0.22222222, 0.33333333, 0.44444444,
           0.55555556, 0.66666667, 0.77777778, 0.88888889, 1.        ])




```python
np.random.normal(10, 4, (3,4)) # 4 = stndard deviation - standart sapma
```




    array([[12.23242643, -1.16266435,  7.7918724 , 10.06559184],
           [ 6.71829286, 11.81279626, 11.88636279, 14.6699796 ],
           [ 7.18991645,  8.90509629,  9.07740848,  9.61974651]])




```python
np.random.randint(0,10, (3,3))
```




    array([[7, 8, 4],
           [0, 4, 8],
           [1, 5, 9]])



# Özellikleri

* **ndim**: _boyut sayısı_
* shape: boyut bilgisi
* size: toplam eleman sayısı
* dtype: array veri tipi


```python
import numpy as np
```


```python
np.random.randint(10, size = 10)
```




    array([3, 5, 2, 5, 7, 8, 5, 7, 7, 3])




```python
a = np.random.randint(10, size = 10)
```


```python
a.ndim
```




    1




```python
a.shape
```




    (10,)




```python
a.size
```




    10




```python
a.dtype
```




    dtype('int32')




```python
b = np.random.randint(10, size = (3,5))
```


```python
b
```




    array([[3, 5, 1, 7, 7],
           [8, 8, 3, 4, 9],
           [0, 6, 1, 1, 5]])




```python
b.ndim
```




    2




```python
b.shape
```




    (3, 5)




```python
b.size
```




    15




```python
b.dtype
```




    dtype('int32')



# Yeniden Şekillendirme (Reshaping)


```python
import numpy as np
```


```python
np.arange(1,10)
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
np.arange(1,10).reshape((3,3))
```




    array([[1, 2, 3],
           [4, 5, 6],
           [7, 8, 9]])




```python
a = np.arange(1,10)
```


```python
a
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
a.ndim
```




    1




```python
b = a.reshape((1,9))
```


```python
b.ndim
```




    2




```python
b
```




    array([[1, 2, 3, 4, 5, 6, 7, 8, 9]])



# Array Birlestirme (Concatenation)


```python
import numpy as np
```


```python
x = np.array([1,2,3])
y = np.array([4,5,6])
```


```python
np.concatenate([x, y])
```




    array([1, 2, 3, 4, 5, 6])




```python
z = np.array([7,8,9])
```


```python
np.concatenate([x, y, z])
```




    array([1, 2, 3, 4, 5, 6, 7, 8, 9])




```python
#iki boyut
```


```python
a = np.array([[1,2,3], 
              [4,5,6]])
```


```python
np.concatenate([a,a])
```




    array([[1, 2, 3],
           [4, 5, 6],
           [1, 2, 3],
           [4, 5, 6]])




```python
np.concatenate([a,a], axis = 1) # axis = 0 satır bazında axis = 1 sütun bazında birleştirme yapar
```




    array([[1, 2, 3, 1, 2, 3],
           [4, 5, 6, 4, 5, 6]])



# Array Ayırma (Splitting)


```python
import numpy as np
```


```python
x = np.array([1,2,3,99,99,3,2,1])
```


```python
np.split(x, [3,5])
```




    [array([1, 2, 3]), array([99, 99]), array([3, 2, 1])]




```python
a,b,c = np.split(x, [3,5])
```


```python
a
```




    array([1, 2, 3])




```python
b
```




    array([99, 99])




```python
c
```




    array([3, 2, 1])




```python
#iki boyutlu ayırma
```


```python
m = np.arange(16).reshape(4,4)
m
```




    array([[ 0,  1,  2,  3],
           [ 4,  5,  6,  7],
           [ 8,  9, 10, 11],
           [12, 13, 14, 15]])




```python
np.vsplit(m, [2])
```




    [array([[0, 1, 2, 3],
            [4, 5, 6, 7]]), array([[ 8,  9, 10, 11],
            [12, 13, 14, 15]])]




```python
ust, alt = np.vsplit(m, [2])
```


```python
ust
```




    array([[0, 1, 2, 3],
           [4, 5, 6, 7]])




```python
alt
```




    array([[ 8,  9, 10, 11],
           [12, 13, 14, 15]])




```python
m
```




    array([[ 0,  1,  2,  3],
           [ 4,  5,  6,  7],
           [ 8,  9, 10, 11],
           [12, 13, 14, 15]])




```python
np.hsplit(m, [2])
```




    [array([[ 0,  1],
            [ 4,  5],
            [ 8,  9],
            [12, 13]]), array([[ 2,  3],
            [ 6,  7],
            [10, 11],
            [14, 15]])]




```python
sag, sol = np.hsplit(m, [2])
```


```python
sag
```




    array([[ 0,  1],
           [ 4,  5],
           [ 8,  9],
           [12, 13]])




```python
sol
```




    array([[ 2,  3],
           [ 6,  7],
           [10, 11],
           [14, 15]])



# Array Sıralama (Sorting)


```python
import numpy as np
```


```python
v = np.array([2,1,4,3,5])
```


```python
v
```




    array([2, 1, 4, 3, 5])




```python
np.sort(v)
```




    array([1, 2, 3, 4, 5])




```python
v
```




    array([2, 1, 4, 3, 5])




```python
v.sort()
```


```python
v
```




    array([1, 2, 3, 4, 5])




```python
#iki boyutlu array siralama
```


```python
m = np.random.normal(20,5, (3,3))
```


```python
m
```




    array([[16.32881824, 18.769658  , 25.61487963],
           [17.05004131, 30.44669048, 23.06955609],
           [14.12436696, 21.34136993, 21.68836983]])




```python
np.sort(m, axis = 1)
```




    array([[16.32881824, 18.769658  , 25.61487963],
           [17.05004131, 23.06955609, 30.44669048],
           [14.12436696, 21.34136993, 21.68836983]])




```python
np.sort(m, axis = 0)
```




    array([[14.12436696, 18.769658  , 21.68836983],
           [16.32881824, 21.34136993, 23.06955609],
           [17.05004131, 30.44669048, 25.61487963]])



# Index ile Elemanlara Erişmek


```python
import numpy as np
a = np.random.randint(10, size = 10)
a
```




    array([9, 5, 6, 0, 1, 5, 9, 5, 7, 9])




```python
a[0]
```




    9




```python
a[-1]
```




    9




```python
a[0] = 100
```


```python
a
```




    array([100,   5,   6,   0,   1,   5,   9,   5,   7,   9])




```python
m = np.random.randint(10, size = (3,5))
m
```




    array([[3, 3, 4, 1, 5],
           [8, 7, 7, 1, 0],
           [7, 2, 3, 1, 7]])




```python
m[0,0]
```




    3




```python
m[1,1]
```




    7




```python
m[1, 4]
```




    0




```python
m[1, 4] = 99
```


```python
m
```




    array([[ 3,  3,  4,  1,  5],
           [ 8,  7,  7,  1, 99],
           [ 7,  2,  3,  1,  7]])




```python
m[1,4] = 2.2
```


```python
m
```




    array([[3, 3, 4, 1, 5],
           [8, 7, 7, 1, 2],
           [7, 2, 3, 1, 7]])



# Slicing ile Elemanlara Erişmek (Array Alt Kümesine Erişmek)


```python
import numpy as np
```


```python
a = np.arange(20,30)
a
```




    array([20, 21, 22, 23, 24, 25, 26, 27, 28, 29])




```python
a[0:3]
```




    array([20, 21, 22])




```python
a[:3]
```




    array([20, 21, 22])




```python
a[3:]
```




    array([23, 24, 25, 26, 27, 28, 29])




```python
a[1::2]
```




    array([21, 23, 25, 27, 29])




```python
a[0::2]
```




    array([20, 22, 24, 26, 28])




```python
a[2::2]
```




    array([22, 24, 26, 28])




```python
a[0::3]
```




    array([20, 23, 26, 29])




```python
#iki boyutlu slice islemleri
```


```python
m = np.random.randint(10, size = (5,5))
```


```python
m
```




    array([[1, 3, 1, 7, 3],
           [9, 2, 6, 4, 4],
           [3, 3, 2, 7, 7],
           [7, 3, 4, 3, 7],
           [1, 3, 6, 1, 1]])




```python
m[:,0]
```




    array([1, 9, 3, 7, 1])




```python
m[:,1]
```




    array([3, 2, 3, 3, 3])




```python
m[:,4]
```




    array([3, 4, 7, 7, 1])




```python
m
```




    array([[1, 3, 1, 7, 3],
           [9, 2, 6, 4, 4],
           [3, 3, 2, 7, 7],
           [7, 3, 4, 3, 7],
           [1, 3, 6, 1, 1]])




```python
m[0,:]
```




    array([1, 3, 1, 7, 3])




```python
m[0]
```




    array([1, 3, 1, 7, 3])




```python
m[1,:]
```




    array([9, 2, 6, 4, 4])




```python
m[0:2, 0:3]
```




    array([[1, 3, 1],
           [9, 2, 6]])




```python
m[:,0:2]
```




    array([[1, 3],
           [9, 2],
           [3, 3],
           [7, 3],
           [1, 3]])




```python
m
```




    array([[1, 3, 1, 7, 3],
           [9, 2, 6, 4, 4],
           [3, 3, 2, 7, 7],
           [7, 3, 4, 3, 7],
           [1, 3, 6, 1, 1]])




```python
m[1:3, 0:2]
```




    array([[9, 2],
           [3, 3]])



# Alt Küme Üzerinde İşlem Yapmak


```python
import numpy as np
a = np.random.randint(10, size = (5, 5))
a
```




    array([[8, 0, 6, 9, 1],
           [6, 6, 8, 2, 0],
           [9, 0, 7, 2, 0],
           [3, 1, 3, 1, 8],
           [7, 6, 3, 6, 9]])




```python
alt_a = a[0:3, 0:2]
alt_a
```




    array([[8, 0],
           [6, 6],
           [9, 0]])




```python
alt_a[0,0] = 99999
alt_a[1,1] = 888
```


```python
alt_a
```




    array([[99999,     0],
           [    6,   888],
           [    9,     0]])




```python
a
```




    array([[99999,     0,     6,     9,     1],
           [    6,   888,     8,     2,     0],
           [    9,     0,     7,     2,     0],
           [    3,     1,     3,     1,     8],
           [    7,     6,     3,     6,     9]])




```python
m = np.random.randint(10, size = (5, 5))
m
```




    array([[1, 1, 6, 4, 2],
           [0, 6, 2, 0, 4],
           [0, 4, 6, 4, 8],
           [0, 2, 1, 5, 7],
           [7, 3, 8, 7, 5]])




```python
alt_b = m[0:3, 0:2].copy()
alt_b
```




    array([[1, 1],
           [0, 6],
           [0, 4]])




```python
alt_b[0,0] = 9999
```


```python
alt_b
```




    array([[9999,    1],
           [   0,    6],
           [   0,    4]])




```python
m
```




    array([[1, 1, 6, 4, 2],
           [0, 6, 2, 0, 4],
           [0, 4, 6, 4, 8],
           [0, 2, 1, 5, 7],
           [7, 3, 8, 7, 5]])



# Fancy Index ile Elemanlara Erişmek


```python
import numpy as np
v = np.arange(0, 30, 3)
v
```




    array([ 0,  3,  6,  9, 12, 15, 18, 21, 24, 27])




```python
v[1]
```




    3




```python
v[3]
```




    9




```python
v[5]
```




    15




```python
[v[1], v[3], v[5]]
```




    [3, 9, 15]




```python
al_getir = [1,3,5]
```


```python
v
```




    array([ 0,  3,  6,  9, 12, 15, 18, 21, 24, 27])




```python
v[al_getir]
```




    array([ 3,  9, 15])




```python
#iki boyutta fancy
```


```python
m = np.arange(9).reshape((3,3))
```


```python
m
```




    array([[0, 1, 2],
           [3, 4, 5],
           [6, 7, 8]])




```python
satir = np.array([0,1])
sutun = np.array([1,2])
```


```python
m[satir, sutun]
```




    array([1, 5])




```python
#basit index ile fancy index
```


```python
m
```




    array([[0, 1, 2],
           [3, 4, 5],
           [6, 7, 8]])




```python
m[0, [1,2]]
```




    array([1, 2])




```python
#slice ile fancy
```


```python
m[0:, [1,2]]
```




    array([[1, 2],
           [4, 5],
           [7, 8]])



# Koşullu Eleman İşlemleri


```python
import numpy as np
v = np.array([1, 2, 3, 4, 5])
```


```python
v < 3
```




    array([ True,  True, False, False, False])




```python
v[v < 3]
```




    array([1, 2])




```python
v[v > 3]
```




    array([4, 5])




```python
v[v >= 3]
```




    array([3, 4, 5])




```python
v[v <= 3]
```




    array([1, 2, 3])




```python
v[v == 3]
```




    array([3])




```python
v[v != 3]
```




    array([1, 2, 4, 5])




```python
v
```




    array([1, 2, 3, 4, 5])




```python
v * 2
```




    array([ 2,  4,  6,  8, 10])




```python
v / 5
```




    array([0.2, 0.4, 0.6, 0.8, 1. ])




```python
v*5/10
```




    array([0.5, 1. , 1.5, 2. , 2.5])




```python
v**2
```




    array([ 1,  4,  9, 16, 25], dtype=int32)



# Matematiksel İşlemler


```python
import numpy as np
v = np.array([1, 2, 3, 4, 5])
```


```python
v - 1
```




    array([0, 1, 2, 3, 4])




```python
v * 5
```




    array([ 5, 10, 15, 20, 25])




```python
v / 5
```




    array([0.2, 0.4, 0.6, 0.8, 1. ])




```python
v*5/10 - 1
```




    array([-0.5,  0. ,  0.5,  1. ,  1.5])




```python
#ufunc
```


```python
np.subtract(v, 1)
```




    array([0, 1, 2, 3, 4])




```python
np.add(v, 1)
```




    array([2, 3, 4, 5, 6])




```python
np.multiply(v,4)
```




    array([ 4,  8, 12, 16, 20])




```python
np.divide(v, 3)
```




    array([0.33333333, 0.66666667, 1.        , 1.33333333, 1.66666667])




```python
v**2
```




    array([ 1,  4,  9, 16, 25], dtype=int32)




```python
v**3
```




    array([  1,   8,  27,  64, 125], dtype=int32)




```python
np.power(v, 3)
```




    array([  1,   8,  27,  64, 125], dtype=int32)




```python
v % 2
```




    array([1, 0, 1, 0, 1], dtype=int32)




```python
np.mod(v, 2)
```




    array([1, 0, 1, 0, 1], dtype=int32)




```python
np.absolute(np.array([-3]))
```




    array([3])




```python
np.sin(360)
```




    0.9589157234143065




```python
np.cos(180)
```




    -0.5984600690578582




```python
v = np.array([1,2,3])
```


```python
np.log(v)
```




    array([0.        , 0.69314718, 1.09861229])




```python
np.log2(v)
```




    array([0.       , 1.       , 1.5849625])




```python
np.log10(v)
```




    array([0.        , 0.30103   , 0.47712125])




```python
?np
```


    [1;31mType:[0m        module
    [1;31mString form:[0m <module 'numpy' from 'C:\\Program Files (x86)\\Microsoft Visual Studio\\Shared\\Anaconda3_64\\lib\\site-packages\\numpy\\__init__.py'>
    [1;31mFile:[0m        c:\program files (x86)\microsoft visual studio\shared\anaconda3_64\lib\site-packages\numpy\__init__.py
    [1;31mDocstring:[0m  
    NumPy
    =====
    
    Provides
      1. An array object of arbitrary homogeneous items
      2. Fast mathematical operations over arrays
      3. Linear Algebra, Fourier Transforms, Random Number Generation
    
    How to use the documentation
    ----------------------------
    Documentation is available in two forms: docstrings provided
    with the code, and a loose standing reference guide, available from
    `the NumPy homepage <http://www.scipy.org>`_.
    
    We recommend exploring the docstrings using
    `IPython <http://ipython.scipy.org>`_, an advanced Python shell with
    TAB-completion and introspection capabilities.  See below for further
    instructions.
    
    The docstring examples assume that `numpy` has been imported as `np`::
    
      >>> import numpy as np
    
    Code snippets are indicated by three greater-than signs::
    
      >>> x = 42
      >>> x = x + 1
    
    Use the built-in ``help`` function to view a function's docstring::
    
      >>> help(np.sort)
      ... # doctest: +SKIP
    
    For some objects, ``np.info(obj)`` may provide additional help.  This is
    particularly true if you see the line "Help on ufunc object:" at the top
    of the help() page.  Ufuncs are implemented in C, not Python, for speed.
    The native Python help() does not know how to view their help, but our
    np.info() function does.
    
    To search for documents containing a keyword, do::
    
      >>> np.lookfor('keyword')
      ... # doctest: +SKIP
    
    General-purpose documents like a glossary and help on the basic concepts
    of numpy are available under the ``doc`` sub-module::
    
      >>> from numpy import doc
      >>> help(doc)
      ... # doctest: +SKIP
    
    Available subpackages
    ---------------------
    doc
        Topical documentation on broadcasting, indexing, etc.
    lib
        Basic functions used by several sub-packages.
    random
        Core Random Tools
    linalg
        Core Linear Algebra Tools
    fft
        Core FFT routines
    polynomial
        Polynomial tools
    testing
        NumPy testing tools
    f2py
        Fortran to Python Interface Generator.
    distutils
        Enhancements to distutils with support for
        Fortran compilers support and more.
    
    Utilities
    ---------
    test
        Run numpy unittests
    show_config
        Show numpy build configuration
    dual
        Overwrite certain functions with high-performance Scipy tools
    matlib
        Make everything matrices.
    __version__
        NumPy version string
    
    Viewing documentation using IPython
    -----------------------------------
    Start IPython with the NumPy profile (``ipython -p numpy``), which will
    import `numpy` under the alias `np`.  Then, use the ``cpaste`` command to
    paste examples into the shell.  To see which functions are available in
    `numpy`, type ``np.<TAB>`` (where ``<TAB>`` refers to the TAB key), or use
    ``np.*cos*?<ENTER>`` (where ``<ENTER>`` refers to the ENTER key) to narrow
    down the list.  To view the docstring for a function, use
    ``np.cos?<ENTER>`` (to view the docstring) and ``np.cos??<ENTER>`` (to view
    the source code).
    
    Copies vs. in-place operation
    -----------------------------
    Most of the functions in `numpy` return a copy of the array argument
    (e.g., `np.sort`).  In-place versions of these functions are often
    available as array methods, i.e. ``x = np.array([1,2,3]); x.sort()``.
    Exceptions to this rule are documented.




```python
#cheatsheet
```

# İstatistiksel Hesaplamalar


```python
v
```




    array([1, 2, 3])




```python
np.mean(v)
```




    2.0




```python
v.sum()
```




    6




```python
v.min()
```




    1




```python
np.std(v)
```




    0.816496580927726



* np.mean(arr,axis=0) | Returns mean along specific axis

* arr.sum() | Returns sum of arr

* arr.min() | Returns minimum value of arr

* arr.max(axis=0) | Returns maximum value of specific axis

* np.var(arr) | Returns the variance of array

* np.std(arr,axis=1) | Returns the standard deviation of specific axis

* arr.corrcoef() | Returns correlation coefficient of array

# NumPy ile İki Bilinmeyenli Denklem Çözümü


```python
import numpy as np
```

**5 * x0 + x1 = 12  
x0 + 3 * x1 = 10**


```python
a = np.array([[5,1], [1,3]])
b = np.array([12,10])
```


```python
a
```




    array([[5, 1],
           [1, 3]])




```python
b
```




    array([12, 10])




```python
x = np.linalg.solve(a, b)
x
```




    array([1.85714286, 2.71428571])



# BOLUM SONU DEGERLENDIRMESI


```python

```

# Pandas Serisi Oluşturmak


```python
import pandas as pd 
```


```python
pd.Series([10,88,3,4,5])
```




    0    10
    1    88
    2     3
    3     4
    4     5
    dtype: int64




```python
seri = pd.Series([10,88,3,4,5])
```


```python
type(seri)
```




    pandas.core.series.Series




```python
seri.axes
```




    [RangeIndex(start=0, stop=5, step=1)]




```python
seri.dtype
```




    dtype('int64')




```python
seri.size
```




    5




```python
seri.ndim
```




    1




```python
seri.values
```




    array([10, 88,  3,  4,  5], dtype=int64)




```python
seri.head(3)
```




    0    10
    1    88
    2     3
    dtype: int64




```python
seri.tail(3)
```




    2    3
    3    4
    4    5
    dtype: int64




```python
#index isimlendirmesi
```


```python
pd.Series([99,22,332,94,5])
```




    0     99
    1     22
    2    332
    3     94
    4      5
    dtype: int64




```python
pd.Series([99,22,332,94,5], index = [1,3,5,7,9])
```




    1     99
    3     22
    5    332
    7     94
    9      5
    dtype: int64




```python
pd.Series([99,22,332,94,5], index = ["a","b","c","d","e"])
```




    a     99
    b     22
    c    332
    d     94
    e      5
    dtype: int64




```python
seri = pd.Series([99,22,332,94,5], index = ["a","b","c","d","e"])
```


```python
seri["a"]
```




    99




```python
seri["a":"c"]
```




    a     99
    b     22
    c    332
    dtype: int64




```python
#sozluk uzerinden liste olusturmak
```


```python
sozluk = {"reg":10, "log":11, "cart": 12}
```


```python
seri = pd.Series(sozluk)
```


```python
seri
```




    reg     10
    log     11
    cart    12
    dtype: int64




```python
#iki seriyi birlestirerek seri olusturma
```


```python
pd.concat([seri,seri])
```




    reg     10
    log     11
    cart    12
    reg     10
    log     11
    cart    12
    dtype: int64



# Eleman İşlemleri


```python
import numpy as np
a = np.array([1,2,33,444,75])
seri = pd.Series(a)
seri
```




    0      1
    1      2
    2     33
    3    444
    4     75
    dtype: int32




```python
seri[0]
```




    1




```python
seri[0:3]
```




    0     1
    1     2
    2    33
    dtype: int32




```python
seri = pd.Series([121,200,150,99], 
                 index = ["reg","loj","cart","rf"])
```


```python
seri
```




    reg     121
    loj     200
    cart    150
    rf       99
    dtype: int64




```python
seri.index
```




    Index(['reg', 'loj', 'cart', 'rf'], dtype='object')




```python
seri.keys
```




    <bound method Series.keys of reg     121
    loj     200
    cart    150
    rf       99
    dtype: int64>




```python
list(seri.items())
```




    [('reg', 121), ('loj', 200), ('cart', 150), ('rf', 99)]




```python
seri.values
```




    array([121, 200, 150,  99], dtype=int64)




```python
#eleman sorgulama
```


```python
"reg" in seri
```




    True




```python
"a" in seri
```




    False




```python
seri["reg"]
```




    121




```python
#fancy eleman
```


```python
seri[["rf", "reg"]]
```




    rf      99
    reg    121
    dtype: int64




```python

```


```python
seri["reg"] = 130
```


```python
seri["reg"]
```




    130




```python
seri["reg":"loj"]
```




    reg    130
    loj    200
    dtype: int64



# Pandas DataFrame Oluşturma


```python
import pandas as pd
```


```python
l = [1,2,39,67,90]
```


```python
l
```




    [1, 2, 39, 67, 90]




```python
pd.DataFrame(l, columns = ["degisken_ismi"])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>degisken_ismi</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>39</td>
    </tr>
    <tr>
      <th>3</th>
      <td>67</td>
    </tr>
    <tr>
      <th>4</th>
      <td>90</td>
    </tr>
  </tbody>
</table>
</div>




```python
import numpy as np
m = np.arange(1,10).reshape((3,3))
m
```




    array([[1, 2, 3],
           [4, 5, 6],
           [7, 8, 9]])




```python
pd.DataFrame(m, columns = ["var1","var2","var3"])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7</td>
      <td>8</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
#df isimlendirme
```


```python
df = pd.DataFrame(m, columns = ["var1","var2","var3"])
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7</td>
      <td>8</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.columns = ("deg1","deg2","deg3")
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>deg1</th>
      <th>deg2</th>
      <th>deg3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7</td>
      <td>8</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
type(df)
```




    pandas.core.frame.DataFrame




```python
df.axes
```




    [RangeIndex(start=0, stop=3, step=1),
     Index(['deg1', 'deg2', 'deg3'], dtype='object')]




```python
df.shape
```




    (3, 3)




```python
df.ndim
```




    2




```python
df.size
```




    9




```python
df.values
```




    array([[1, 2, 3],
           [4, 5, 6],
           [7, 8, 9]])




```python
type(df.values)
```




    numpy.ndarray




```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>deg1</th>
      <th>deg2</th>
      <th>deg3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
      <td>2</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>4</td>
      <td>5</td>
      <td>6</td>
    </tr>
    <tr>
      <th>2</th>
      <td>7</td>
      <td>8</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.tail(1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>deg1</th>
      <th>deg2</th>
      <th>deg3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>7</td>
      <td>8</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
a = np.array([1,2,3,4,5])
```


```python
pd.DataFrame(a, columns = ["deg1"])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>deg1</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>4</td>
    </tr>
    <tr>
      <th>4</th>
      <td>5</td>
    </tr>
  </tbody>
</table>
</div>



# Eleman İşlemleri


```python
import numpy as np
s1 = np.random.randint(10, size = 5)
s2 = np.random.randint(10, size = 5)
s3 = np.random.randint(10, size = 5)
```


```python
sozluk = {"var1": s1, "var2": s2, "var3": s3}
```


```python
sozluk
```




    {'var1': array([4, 6, 8, 0, 0]),
     'var2': array([1, 2, 1, 1, 4]),
     'var3': array([8, 7, 2, 9, 9])}




```python
df = pd.DataFrame(sozluk)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4</td>
      <td>1</td>
      <td>8</td>
    </tr>
    <tr>
      <th>1</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>2</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[0:1]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4</td>
      <td>1</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.index
```




    RangeIndex(start=0, stop=5, step=1)




```python
df.index = ["a","b","c","d","e"]
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>4</td>
      <td>1</td>
      <td>8</td>
    </tr>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["c":"e"]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
#silme
```


```python
df.drop("a", axis = 0)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>a</th>
      <td>4</td>
      <td>1</td>
      <td>8</td>
    </tr>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.drop("a", axis = 0, inplace = True) # dataframe'de kalıcı değişiklik yapmak için kullanılır
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
#fancy 
```


```python
l = ["c","e"]
```


```python
df.drop(l, axis = 0)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
#degiskenler icin
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
"var1" in df
```




    True




```python
l = ["var1","var4","var2"]
```


```python
for i in l:
    print(i in df)
```

    True
    False
    True



```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["var1"]
```




    b    6
    c    8
    d    0
    e    0
    Name: var1, dtype: int32




```python
df["var4"] = df["var1"] / df["var2"]
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
      <th>var4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#degisken silmek
```


```python
df.drop("var4", axis = 1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
      <th>var4</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.drop("var4", axis = 1, inplace = True)
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>6</td>
      <td>2</td>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>8</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>0</td>
      <td>1</td>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>0</td>
      <td>4</td>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>




```python
l = ["var1","var2"]
```


```python
df.drop(l, axis = 1)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>b</th>
      <td>7</td>
    </tr>
    <tr>
      <th>c</th>
      <td>2</td>
    </tr>
    <tr>
      <th>d</th>
      <td>9</td>
    </tr>
    <tr>
      <th>e</th>
      <td>9</td>
    </tr>
  </tbody>
</table>
</div>



# Gözlem ve Değişken Seçimi: loc & iloc


```python
import numpy as np
import pandas as pd
m = np.random.randint(1,30, size = (10,3))
df = pd.DataFrame(m, columns = ["var1","var2","var3"])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4</td>
      <td>27</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>28</td>
      <td>16</td>
      <td>28</td>
    </tr>
    <tr>
      <th>2</th>
      <td>5</td>
      <td>21</td>
      <td>16</td>
    </tr>
    <tr>
      <th>3</th>
      <td>28</td>
      <td>23</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6</td>
      <td>9</td>
      <td>11</td>
    </tr>
    <tr>
      <th>5</th>
      <td>8</td>
      <td>10</td>
      <td>13</td>
    </tr>
    <tr>
      <th>6</th>
      <td>29</td>
      <td>9</td>
      <td>9</td>
    </tr>
    <tr>
      <th>7</th>
      <td>5</td>
      <td>21</td>
      <td>18</td>
    </tr>
    <tr>
      <th>8</th>
      <td>11</td>
      <td>25</td>
      <td>13</td>
    </tr>
    <tr>
      <th>9</th>
      <td>25</td>
      <td>13</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
#loc: tanımlandığı şekli ile seçim yapmak için kullanılır.
```


```python
df.loc[0:3]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4</td>
      <td>27</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>28</td>
      <td>16</td>
      <td>28</td>
    </tr>
    <tr>
      <th>2</th>
      <td>5</td>
      <td>21</td>
      <td>16</td>
    </tr>
    <tr>
      <th>3</th>
      <td>28</td>
      <td>23</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
#iloc: alışık olduğumuz indeksleme mantığı ile seçim yapar.
```


```python
df.iloc[0:3]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4</td>
      <td>27</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>28</td>
      <td>16</td>
      <td>28</td>
    </tr>
    <tr>
      <th>2</th>
      <td>5</td>
      <td>21</td>
      <td>16</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[0,0]
```




    4




```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4</td>
      <td>27</td>
      <td>22</td>
    </tr>
    <tr>
      <th>1</th>
      <td>28</td>
      <td>16</td>
      <td>28</td>
    </tr>
    <tr>
      <th>2</th>
      <td>5</td>
      <td>21</td>
      <td>16</td>
    </tr>
    <tr>
      <th>3</th>
      <td>28</td>
      <td>23</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6</td>
      <td>9</td>
      <td>11</td>
    </tr>
    <tr>
      <th>5</th>
      <td>8</td>
      <td>10</td>
      <td>13</td>
    </tr>
    <tr>
      <th>6</th>
      <td>29</td>
      <td>9</td>
      <td>9</td>
    </tr>
    <tr>
      <th>7</th>
      <td>5</td>
      <td>21</td>
      <td>18</td>
    </tr>
    <tr>
      <th>8</th>
      <td>11</td>
      <td>25</td>
      <td>13</td>
    </tr>
    <tr>
      <th>9</th>
      <td>25</td>
      <td>13</td>
      <td>8</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.iloc[:3,:2]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4</td>
      <td>27</td>
    </tr>
    <tr>
      <th>1</th>
      <td>28</td>
      <td>16</td>
    </tr>
    <tr>
      <th>2</th>
      <td>5</td>
      <td>21</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[0:3, "var3"]
```




    0    22
    1    28
    2    16
    3     2
    Name: var3, dtype: int32




```python
df.loc[0:3, "var3"]
```




    0    22
    1    28
    2    16
    3     2
    Name: var3, dtype: int32




```python
df.iloc[0:3]["var3"]
```




    0    22
    1    28
    2    16
    Name: var3, dtype: int32



# Koşullu Eleman İşlemleri


```python
import numpy as np
import pandas as pd
m = np.random.randint(1,30, size = (10,3))
df = pd.DataFrame(m, columns = ["var1","var2","var3"])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>21</td>
      <td>5</td>
      <td>15</td>
    </tr>
    <tr>
      <th>1</th>
      <td>29</td>
      <td>26</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>18</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>9</td>
      <td>20</td>
      <td>28</td>
    </tr>
    <tr>
      <th>5</th>
      <td>26</td>
      <td>24</td>
      <td>13</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1</td>
      <td>11</td>
      <td>3</td>
    </tr>
    <tr>
      <th>7</th>
      <td>21</td>
      <td>26</td>
      <td>12</td>
    </tr>
    <tr>
      <th>8</th>
      <td>21</td>
      <td>6</td>
      <td>6</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1</td>
      <td>5</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["var1"]
```




    0    21
    1    29
    2    19
    3    21
    4     9
    5    26
    6     1
    7    21
    8    21
    9     1
    Name: var1, dtype: int32




```python
df[0:2][["var1","var2"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>21</td>
      <td>5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>29</td>
      <td>26</td>
    </tr>
  </tbody>
</table>
</div>




```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>21</td>
      <td>5</td>
      <td>15</td>
    </tr>
    <tr>
      <th>1</th>
      <td>29</td>
      <td>26</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>18</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>9</td>
      <td>20</td>
      <td>28</td>
    </tr>
    <tr>
      <th>5</th>
      <td>26</td>
      <td>24</td>
      <td>13</td>
    </tr>
    <tr>
      <th>6</th>
      <td>1</td>
      <td>11</td>
      <td>3</td>
    </tr>
    <tr>
      <th>7</th>
      <td>21</td>
      <td>26</td>
      <td>12</td>
    </tr>
    <tr>
      <th>8</th>
      <td>21</td>
      <td>6</td>
      <td>6</td>
    </tr>
    <tr>
      <th>9</th>
      <td>1</td>
      <td>5</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.var1
```




    0    21
    1    29
    2    19
    3    21
    4     9
    5    26
    6     1
    7    21
    8    21
    9     1
    Name: var1, dtype: int32




```python
df[df.var1 > 15]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>21</td>
      <td>5</td>
      <td>15</td>
    </tr>
    <tr>
      <th>1</th>
      <td>29</td>
      <td>26</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>1</td>
      <td>2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>18</td>
      <td>23</td>
    </tr>
    <tr>
      <th>5</th>
      <td>26</td>
      <td>24</td>
      <td>13</td>
    </tr>
    <tr>
      <th>7</th>
      <td>21</td>
      <td>26</td>
      <td>12</td>
    </tr>
    <tr>
      <th>8</th>
      <td>21</td>
      <td>6</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[(df.var1 > 15) & (df.var3 < 5)]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>1</td>
      <td>2</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.loc[(df.var1 > 15), ["var1","var2"]] # fancy
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>21</td>
      <td>5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>29</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>18</td>
    </tr>
    <tr>
      <th>5</th>
      <td>26</td>
      <td>24</td>
    </tr>
    <tr>
      <th>7</th>
      <td>21</td>
      <td>26</td>
    </tr>
    <tr>
      <th>8</th>
      <td>21</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>




```python
df[(df.var1 > 15)][["var1","var2"]]
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>21</td>
      <td>5</td>
    </tr>
    <tr>
      <th>1</th>
      <td>29</td>
      <td>26</td>
    </tr>
    <tr>
      <th>2</th>
      <td>19</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>21</td>
      <td>18</td>
    </tr>
    <tr>
      <th>5</th>
      <td>26</td>
      <td>24</td>
    </tr>
    <tr>
      <th>7</th>
      <td>21</td>
      <td>26</td>
    </tr>
    <tr>
      <th>8</th>
      <td>21</td>
      <td>6</td>
    </tr>
  </tbody>
</table>
</div>



# Birleştirme (Join) İşlemleri


```python
import numpy as np
import pandas as pd
m = np.random.randint(1,30, size = (5,3))
df1 = pd.DataFrame(m, columns = ["var1","var2","var3"])
df1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>3</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17</td>
      <td>2</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>14</td>
      <td>21</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20</td>
      <td>11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>13</td>
      <td>27</td>
      <td>25</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2 = df1 + 99
```


```python
df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>106</td>
      <td>102</td>
      <td>106</td>
    </tr>
    <tr>
      <th>1</th>
      <td>116</td>
      <td>101</td>
      <td>119</td>
    </tr>
    <tr>
      <th>2</th>
      <td>119</td>
      <td>113</td>
      <td>120</td>
    </tr>
    <tr>
      <th>3</th>
      <td>101</td>
      <td>119</td>
      <td>110</td>
    </tr>
    <tr>
      <th>4</th>
      <td>112</td>
      <td>126</td>
      <td>124</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([df1,df2])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>3</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17</td>
      <td>2</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>14</td>
      <td>21</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20</td>
      <td>11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>13</td>
      <td>27</td>
      <td>25</td>
    </tr>
    <tr>
      <th>0</th>
      <td>106</td>
      <td>102</td>
      <td>106</td>
    </tr>
    <tr>
      <th>1</th>
      <td>116</td>
      <td>101</td>
      <td>119</td>
    </tr>
    <tr>
      <th>2</th>
      <td>119</td>
      <td>113</td>
      <td>120</td>
    </tr>
    <tr>
      <th>3</th>
      <td>101</td>
      <td>119</td>
      <td>110</td>
    </tr>
    <tr>
      <th>4</th>
      <td>112</td>
      <td>126</td>
      <td>124</td>
    </tr>
  </tbody>
</table>
</div>




```python
?pd.concat
```


    [1;31mSignature:[0m [0mpd[0m[1;33m.[0m[0mconcat[0m[1;33m([0m[0mobjs[0m[1;33m,[0m [0maxis[0m[1;33m=[0m[1;36m0[0m[1;33m,[0m [0mjoin[0m[1;33m=[0m[1;34m'outer'[0m[1;33m,[0m [0mjoin_axes[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mignore_index[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mkeys[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mlevels[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mnames[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mverify_integrity[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0msort[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mcopy[0m[1;33m=[0m[1;32mTrue[0m[1;33m)[0m[1;33m[0m[0m
    [1;31mDocstring:[0m
    Concatenate pandas objects along a particular axis with optional set logic
    along the other axes.
    
    Can also add a layer of hierarchical indexing on the concatenation axis,
    which may be useful if the labels are the same (or overlapping) on
    the passed axis number.
    
    Parameters
    ----------
    objs : a sequence or mapping of Series, DataFrame, or Panel objects
        If a dict is passed, the sorted keys will be used as the `keys`
        argument, unless it is passed, in which case the values will be
        selected (see below). Any None objects will be dropped silently unless
        they are all None in which case a ValueError will be raised
    axis : {0/'index', 1/'columns'}, default 0
        The axis to concatenate along
    join : {'inner', 'outer'}, default 'outer'
        How to handle indexes on other axis(es)
    join_axes : list of Index objects
        Specific indexes to use for the other n - 1 axes instead of performing
        inner/outer set logic
    ignore_index : boolean, default False
        If True, do not use the index values along the concatenation axis. The
        resulting axis will be labeled 0, ..., n - 1. This is useful if you are
        concatenating objects where the concatenation axis does not have
        meaningful indexing information. Note the index values on the other
        axes are still respected in the join.
    keys : sequence, default None
        If multiple levels passed, should contain tuples. Construct
        hierarchical index using the passed keys as the outermost level
    levels : list of sequences, default None
        Specific levels (unique values) to use for constructing a
        MultiIndex. Otherwise they will be inferred from the keys
    names : list, default None
        Names for the levels in the resulting hierarchical index
    verify_integrity : boolean, default False
        Check whether the new concatenated axis contains duplicates. This can
        be very expensive relative to the actual data concatenation
    sort : boolean, default None
        Sort non-concatenation axis if it is not already aligned when `join`
        is 'outer'. The current default of sorting is deprecated and will
        change to not-sorting in a future version of pandas.
    
        Explicitly pass ``sort=True`` to silence the warning and sort.
        Explicitly pass ``sort=False`` to silence the warning and not sort.
    
        This has no effect when ``join='inner'``, which already preserves
        the order of the non-concatenation axis.
    
        .. versionadded:: 0.23.0
    
    copy : boolean, default True
        If False, do not copy data unnecessarily
    
    Returns
    -------
    concatenated : object, type of objs
        When concatenating all ``Series`` along the index (axis=0), a
        ``Series`` is returned. When ``objs`` contains at least one
        ``DataFrame``, a ``DataFrame`` is returned. When concatenating along
        the columns (axis=1), a ``DataFrame`` is returned.
    
    Notes
    -----
    The keys, levels, and names arguments are all optional.
    
    A walkthrough of how this method fits in with other tools for combining
    pandas objects can be found `here
    <http://pandas.pydata.org/pandas-docs/stable/merging.html>`__.
    
    See Also
    --------
    Series.append
    DataFrame.append
    DataFrame.join
    DataFrame.merge
    
    Examples
    --------
    Combine two ``Series``.
    
    >>> s1 = pd.Series(['a', 'b'])
    >>> s2 = pd.Series(['c', 'd'])
    >>> pd.concat([s1, s2])
    0    a
    1    b
    0    c
    1    d
    dtype: object
    
    Clear the existing index and reset it in the result
    by setting the ``ignore_index`` option to ``True``.
    
    >>> pd.concat([s1, s2], ignore_index=True)
    0    a
    1    b
    2    c
    3    d
    dtype: object
    
    Add a hierarchical index at the outermost level of
    the data with the ``keys`` option.
    
    >>> pd.concat([s1, s2], keys=['s1', 's2',])
    s1  0    a
        1    b
    s2  0    c
        1    d
    dtype: object
    
    Label the index keys you create with the ``names`` option.
    
    >>> pd.concat([s1, s2], keys=['s1', 's2'],
    ...           names=['Series name', 'Row ID'])
    Series name  Row ID
    s1           0         a
                 1         b
    s2           0         c
                 1         d
    dtype: object
    
    Combine two ``DataFrame`` objects with identical columns.
    
    >>> df1 = pd.DataFrame([['a', 1], ['b', 2]],
    ...                    columns=['letter', 'number'])
    >>> df1
      letter  number
    0      a       1
    1      b       2
    >>> df2 = pd.DataFrame([['c', 3], ['d', 4]],
    ...                    columns=['letter', 'number'])
    >>> df2
      letter  number
    0      c       3
    1      d       4
    >>> pd.concat([df1, df2])
      letter  number
    0      a       1
    1      b       2
    0      c       3
    1      d       4
    
    Combine ``DataFrame`` objects with overlapping columns
    and return everything. Columns outside the intersection will
    be filled with ``NaN`` values.
    
    >>> df3 = pd.DataFrame([['c', 3, 'cat'], ['d', 4, 'dog']],
    ...                    columns=['letter', 'number', 'animal'])
    >>> df3
      letter  number animal
    0      c       3    cat
    1      d       4    dog
    >>> pd.concat([df1, df3])
      animal letter  number
    0    NaN      a       1
    1    NaN      b       2
    0    cat      c       3
    1    dog      d       4
    
    Combine ``DataFrame`` objects with overlapping columns
    and return only those that are shared by passing ``inner`` to
    the ``join`` keyword argument.
    
    >>> pd.concat([df1, df3], join="inner")
      letter  number
    0      a       1
    1      b       2
    0      c       3
    1      d       4
    
    Combine ``DataFrame`` objects horizontally along the x axis by
    passing in ``axis=1``.
    
    >>> df4 = pd.DataFrame([['bird', 'polly'], ['monkey', 'george']],
    ...                    columns=['animal', 'name'])
    >>> pd.concat([df1, df4], axis=1)
      letter  number  animal    name
    0      a       1    bird   polly
    1      b       2  monkey  george
    
    Prevent the result from including duplicate index values with the
    ``verify_integrity`` option.
    
    >>> df5 = pd.DataFrame([1], index=['a'])
    >>> df5
       0
    a  1
    >>> df6 = pd.DataFrame([2], index=['a'])
    >>> df6
       0
    a  2
    >>> pd.concat([df5, df6], verify_integrity=True)
    Traceback (most recent call last):
        ...
    ValueError: Indexes have overlapping values: ['a']
    [1;31mFile:[0m      c:\program files (x86)\microsoft visual studio\shared\anaconda3_64\lib\site-packages\pandas\core\reshape\concat.py
    [1;31mType:[0m      function




```python
pd.concat([df1,df2], ignore_index=True)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>3</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17</td>
      <td>2</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>14</td>
      <td>21</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20</td>
      <td>11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>13</td>
      <td>27</td>
      <td>25</td>
    </tr>
    <tr>
      <th>5</th>
      <td>106</td>
      <td>102</td>
      <td>106</td>
    </tr>
    <tr>
      <th>6</th>
      <td>116</td>
      <td>101</td>
      <td>119</td>
    </tr>
    <tr>
      <th>7</th>
      <td>119</td>
      <td>113</td>
      <td>120</td>
    </tr>
    <tr>
      <th>8</th>
      <td>101</td>
      <td>119</td>
      <td>110</td>
    </tr>
    <tr>
      <th>9</th>
      <td>112</td>
      <td>126</td>
      <td>124</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1.columns
```




    Index(['var1', 'var2', 'var3'], dtype='object')




```python
df2.columns = ["var1","var2","deg3"]
```


```python
df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>deg3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>106</td>
      <td>102</td>
      <td>106</td>
    </tr>
    <tr>
      <th>1</th>
      <td>116</td>
      <td>101</td>
      <td>119</td>
    </tr>
    <tr>
      <th>2</th>
      <td>119</td>
      <td>113</td>
      <td>120</td>
    </tr>
    <tr>
      <th>3</th>
      <td>101</td>
      <td>119</td>
      <td>110</td>
    </tr>
    <tr>
      <th>4</th>
      <td>112</td>
      <td>126</td>
      <td>124</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>3</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17</td>
      <td>2</td>
      <td>20</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>14</td>
      <td>21</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20</td>
      <td>11</td>
    </tr>
    <tr>
      <th>4</th>
      <td>13</td>
      <td>27</td>
      <td>25</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([df1, df2])
```

    C:\Program Files (x86)\Microsoft Visual Studio\Shared\Anaconda3_64\lib\site-packages\ipykernel_launcher.py:1: FutureWarning: Sorting because non-concatenation axis is not aligned. A future version
    of pandas will change to not sort by default.
    
    To accept the future behavior, pass 'sort=True'.
    
    To retain the current behavior and silence the warning, pass sort=False
    
      """Entry point for launching an IPython kernel.





<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>deg3</th>
      <th>var1</th>
      <th>var2</th>
      <th>var3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>NaN</td>
      <td>7</td>
      <td>3</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>NaN</td>
      <td>17</td>
      <td>2</td>
      <td>20.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>NaN</td>
      <td>20</td>
      <td>14</td>
      <td>21.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>NaN</td>
      <td>2</td>
      <td>20</td>
      <td>11.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>NaN</td>
      <td>13</td>
      <td>27</td>
      <td>25.0</td>
    </tr>
    <tr>
      <th>0</th>
      <td>106.0</td>
      <td>106</td>
      <td>102</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>119.0</td>
      <td>116</td>
      <td>101</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>120.0</td>
      <td>119</td>
      <td>113</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>110.0</td>
      <td>101</td>
      <td>119</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>124.0</td>
      <td>112</td>
      <td>126</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([df1, df2], join = "inner")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>3</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>14</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20</td>
    </tr>
    <tr>
      <th>4</th>
      <td>13</td>
      <td>27</td>
    </tr>
    <tr>
      <th>0</th>
      <td>106</td>
      <td>102</td>
    </tr>
    <tr>
      <th>1</th>
      <td>116</td>
      <td>101</td>
    </tr>
    <tr>
      <th>2</th>
      <td>119</td>
      <td>113</td>
    </tr>
    <tr>
      <th>3</th>
      <td>101</td>
      <td>119</td>
    </tr>
    <tr>
      <th>4</th>
      <td>112</td>
      <td>126</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.concat([df1, df2], join_axes = [df2.columns], ignore_index=True)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>var1</th>
      <th>var2</th>
      <th>deg3</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>7</td>
      <td>3</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>17</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>20</td>
      <td>14</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2</td>
      <td>20</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>4</th>
      <td>13</td>
      <td>27</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>5</th>
      <td>106</td>
      <td>102</td>
      <td>106.0</td>
    </tr>
    <tr>
      <th>6</th>
      <td>116</td>
      <td>101</td>
      <td>119.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>119</td>
      <td>113</td>
      <td>120.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>101</td>
      <td>119</td>
      <td>110.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>112</td>
      <td>126</td>
      <td>124.0</td>
    </tr>
  </tbody>
</table>
</div>



# İleri Birleştirme İşlemleri


```python
import pandas as pd
```


```python
#birebir birlestirme
```


```python
df1 = pd.DataFrame({'calisanlar': ['Ali', 'Veli', 'Ayse', 'Fatma'],
                    'grup': ['Muhasebe', 'Muhendislik', 'Muhendislik', 'İK']})

df1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>grup</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ali</td>
      <td>Muhasebe</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Veli</td>
      <td>Muhendislik</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Fatma</td>
      <td>İK</td>
    </tr>
  </tbody>
</table>
</div>




```python
df2 = pd.DataFrame({'calisanlar': ['Ayse', 'Ali', 'Veli', 'Fatma'],
                    'ilk_giris': [2010, 2009, 2014, 2019]})

df2
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>ilk_giris</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ayse</td>
      <td>2010</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ali</td>
      <td>2009</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Veli</td>
      <td>2014</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Fatma</td>
      <td>2019</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(df1, df2)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>grup</th>
      <th>ilk_giris</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ali</td>
      <td>Muhasebe</td>
      <td>2009</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Veli</td>
      <td>Muhendislik</td>
      <td>2014</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
      <td>2010</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Fatma</td>
      <td>İK</td>
      <td>2019</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(df1, df2, on = "calisanlar")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>grup</th>
      <th>ilk_giris</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ali</td>
      <td>Muhasebe</td>
      <td>2009</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Veli</td>
      <td>Muhendislik</td>
      <td>2014</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
      <td>2010</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Fatma</td>
      <td>İK</td>
      <td>2019</td>
    </tr>
  </tbody>
</table>
</div>




```python
#coktan teke 
```


```python
df3 = pd.merge(df1, df2)
```


```python
df3
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>grup</th>
      <th>ilk_giris</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ali</td>
      <td>Muhasebe</td>
      <td>2009</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Veli</td>
      <td>Muhendislik</td>
      <td>2014</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
      <td>2010</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Fatma</td>
      <td>İK</td>
      <td>2019</td>
    </tr>
  </tbody>
</table>
</div>




```python
df4 = pd.DataFrame({'grup': ['Muhasebe', 'Muhendislik', 'İK'],
                    'mudur': ['Caner', 'Mustafa', 'Berkcan']})

df4
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>grup</th>
      <th>mudur</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Muhasebe</td>
      <td>Caner</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Muhendislik</td>
      <td>Mustafa</td>
    </tr>
    <tr>
      <th>2</th>
      <td>İK</td>
      <td>Berkcan</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(df3,df4)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>grup</th>
      <th>ilk_giris</th>
      <th>mudur</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ali</td>
      <td>Muhasebe</td>
      <td>2009</td>
      <td>Caner</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Veli</td>
      <td>Muhendislik</td>
      <td>2014</td>
      <td>Mustafa</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
      <td>2010</td>
      <td>Mustafa</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Fatma</td>
      <td>İK</td>
      <td>2019</td>
      <td>Berkcan</td>
    </tr>
  </tbody>
</table>
</div>




```python
# çoktan çoka
```


```python
df5 = pd.DataFrame({'grup': ['Muhasebe', 'Muhasebe',
                              'Muhendislik', 'Muhendislik', 'İK', 'İK'],
                    'yetenekler': ['matematik', 'excel', 'kodlama', 'linux',
                               'excel', 'yonetim']})

df5
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>grup</th>
      <th>yetenekler</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Muhasebe</td>
      <td>matematik</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Muhasebe</td>
      <td>excel</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Muhendislik</td>
      <td>kodlama</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Muhendislik</td>
      <td>linux</td>
    </tr>
    <tr>
      <th>4</th>
      <td>İK</td>
      <td>excel</td>
    </tr>
    <tr>
      <th>5</th>
      <td>İK</td>
      <td>yonetim</td>
    </tr>
  </tbody>
</table>
</div>




```python
df1
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>grup</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ali</td>
      <td>Muhasebe</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Veli</td>
      <td>Muhendislik</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Fatma</td>
      <td>İK</td>
    </tr>
  </tbody>
</table>
</div>




```python
pd.merge(df1, df5)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>calisanlar</th>
      <th>grup</th>
      <th>yetenekler</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Ali</td>
      <td>Muhasebe</td>
      <td>matematik</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Ali</td>
      <td>Muhasebe</td>
      <td>excel</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Veli</td>
      <td>Muhendislik</td>
      <td>kodlama</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Veli</td>
      <td>Muhendislik</td>
      <td>linux</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
      <td>kodlama</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Ayse</td>
      <td>Muhendislik</td>
      <td>linux</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Fatma</td>
      <td>İK</td>
      <td>excel</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Fatma</td>
      <td>İK</td>
      <td>yonetim</td>
    </tr>
  </tbody>
</table>
</div>



# Toplulaştırma ve Gruplama (Aggregation & Grouping)

Basit toplulaştırma fonksiyonları:

* count()
* first()
* last()
* mean()
* median()
* min()
* max()
* std()
* var()
* sum()


```python
import seaborn as sns
```


```python
?sns.load_dataset
```


    [1;31mSignature:[0m [0msns[0m[1;33m.[0m[0mload_dataset[0m[1;33m([0m[0mname[0m[1;33m,[0m [0mcache[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mdata_home[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [1;33m**[0m[0mkws[0m[1;33m)[0m[1;33m[0m[0m
    [1;31mDocstring:[0m
    Load a dataset from the online repository (requires internet).
    
    Parameters
    ----------
    name : str
        Name of the dataset (`name`.csv on
        https://github.com/mwaskom/seaborn-data).  You can obtain list of
        available datasets using :func:`get_dataset_names`
    cache : boolean, optional
        If True, then cache data locally and use the cache on subsequent calls
    data_home : string, optional
        The directory in which to cache data. By default, uses ~/seaborn-data/
    kws : dict, optional
        Passed to pandas.read_csv
    [1;31mFile:[0m      c:\program files (x86)\microsoft visual studio\shared\anaconda3_64\lib\site-packages\seaborn\utils.py
    [1;31mType:[0m      function




```python
df = sns.load_dataset("planets")
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>method</th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>269.300</td>
      <td>7.10</td>
      <td>77.40</td>
      <td>2006</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>874.774</td>
      <td>2.21</td>
      <td>56.95</td>
      <td>2008</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>763.000</td>
      <td>2.60</td>
      <td>19.84</td>
      <td>2011</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>326.030</td>
      <td>19.40</td>
      <td>110.62</td>
      <td>2007</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>516.220</td>
      <td>10.50</td>
      <td>119.47</td>
      <td>2009</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.shape
```




    (1035, 6)




```python
df.mean()
```




    number               1.785507
    orbital_period    2002.917596
    mass                 2.638161
    distance           264.069282
    year              2009.070531
    dtype: float64




```python
df["mass"].mean()
```




    2.6381605847953233




```python
df["mass"].count()
```




    513




```python
df["mass"].min()
```




    0.0036




```python
df["mass"].max()
```




    25.0




```python
df["mass"].sum()
```




    1353.37638




```python
df["mass"].std()
```




    3.8186166509616046




```python
df["mass"].var()
```




    14.58183312700122




```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>1035.000000</td>
      <td>992.000000</td>
      <td>513.000000</td>
      <td>808.000000</td>
      <td>1035.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.785507</td>
      <td>2002.917596</td>
      <td>2.638161</td>
      <td>264.069282</td>
      <td>2009.070531</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1.240976</td>
      <td>26014.728304</td>
      <td>3.818617</td>
      <td>733.116493</td>
      <td>3.972567</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>0.090706</td>
      <td>0.003600</td>
      <td>1.350000</td>
      <td>1989.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>1.000000</td>
      <td>5.442540</td>
      <td>0.229000</td>
      <td>32.560000</td>
      <td>2007.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1.000000</td>
      <td>39.979500</td>
      <td>1.260000</td>
      <td>55.250000</td>
      <td>2010.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2.000000</td>
      <td>526.005000</td>
      <td>3.040000</td>
      <td>178.500000</td>
      <td>2012.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>7.000000</td>
      <td>730000.000000</td>
      <td>25.000000</td>
      <td>8500.000000</td>
      <td>2014.000000</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.describe().T
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>number</th>
      <td>1035.0</td>
      <td>1.785507</td>
      <td>1.240976</td>
      <td>1.000000</td>
      <td>1.00000</td>
      <td>1.0000</td>
      <td>2.000</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>orbital_period</th>
      <td>992.0</td>
      <td>2002.917596</td>
      <td>26014.728304</td>
      <td>0.090706</td>
      <td>5.44254</td>
      <td>39.9795</td>
      <td>526.005</td>
      <td>730000.0</td>
    </tr>
    <tr>
      <th>mass</th>
      <td>513.0</td>
      <td>2.638161</td>
      <td>3.818617</td>
      <td>0.003600</td>
      <td>0.22900</td>
      <td>1.2600</td>
      <td>3.040</td>
      <td>25.0</td>
    </tr>
    <tr>
      <th>distance</th>
      <td>808.0</td>
      <td>264.069282</td>
      <td>733.116493</td>
      <td>1.350000</td>
      <td>32.56000</td>
      <td>55.2500</td>
      <td>178.500</td>
      <td>8500.0</td>
    </tr>
    <tr>
      <th>year</th>
      <td>1035.0</td>
      <td>2009.070531</td>
      <td>3.972567</td>
      <td>1989.000000</td>
      <td>2007.00000</td>
      <td>2010.0000</td>
      <td>2012.000</td>
      <td>2014.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.dropna().describe().T # na'ları drop et
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>number</th>
      <td>498.0</td>
      <td>1.734940</td>
      <td>1.175720</td>
      <td>1.0000</td>
      <td>1.00000</td>
      <td>1.000</td>
      <td>2.0000</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>orbital_period</th>
      <td>498.0</td>
      <td>835.778671</td>
      <td>1469.128259</td>
      <td>1.3283</td>
      <td>38.27225</td>
      <td>357.000</td>
      <td>999.6000</td>
      <td>17337.5</td>
    </tr>
    <tr>
      <th>mass</th>
      <td>498.0</td>
      <td>2.509320</td>
      <td>3.636274</td>
      <td>0.0036</td>
      <td>0.21250</td>
      <td>1.245</td>
      <td>2.8675</td>
      <td>25.0</td>
    </tr>
    <tr>
      <th>distance</th>
      <td>498.0</td>
      <td>52.068213</td>
      <td>46.596041</td>
      <td>1.3500</td>
      <td>24.49750</td>
      <td>39.940</td>
      <td>59.3325</td>
      <td>354.0</td>
    </tr>
    <tr>
      <th>year</th>
      <td>498.0</td>
      <td>2007.377510</td>
      <td>4.167284</td>
      <td>1989.0000</td>
      <td>2005.00000</td>
      <td>2009.000</td>
      <td>2011.0000</td>
      <td>2014.0</td>
    </tr>
  </tbody>
</table>
</div>



# Gruplama İşlemleri


```python
df = pd.DataFrame({'gruplar': ['A', 'B', 'C', 'A', 'B', 'C'],
                   'veri': [10,11,52,23,43,55]}, columns=['gruplar', 'veri'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gruplar</th>
      <th>veri</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>10</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>11</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>52</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A</td>
      <td>23</td>
    </tr>
    <tr>
      <th>4</th>
      <td>B</td>
      <td>43</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>55</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("gruplar")
```




    <pandas.core.groupby.groupby.DataFrameGroupBy object at 0x000001B261D9AD68>




```python
df.groupby("gruplar").mean()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>veri</th>
    </tr>
    <tr>
      <th>gruplar</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>16.5</td>
    </tr>
    <tr>
      <th>B</th>
      <td>27.0</td>
    </tr>
    <tr>
      <th>C</th>
      <td>53.5</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("gruplar").sum()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>veri</th>
    </tr>
    <tr>
      <th>gruplar</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>33</td>
    </tr>
    <tr>
      <th>B</th>
      <td>54</td>
    </tr>
    <tr>
      <th>C</th>
      <td>107</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = sns.load_dataset("planets")
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>method</th>
      <th>number</th>
      <th>orbital_period</th>
      <th>mass</th>
      <th>distance</th>
      <th>year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>269.300</td>
      <td>7.10</td>
      <td>77.40</td>
      <td>2006</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>874.774</td>
      <td>2.21</td>
      <td>56.95</td>
      <td>2008</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>763.000</td>
      <td>2.60</td>
      <td>19.84</td>
      <td>2011</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>326.030</td>
      <td>19.40</td>
      <td>110.62</td>
      <td>2007</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Radial Velocity</td>
      <td>1</td>
      <td>516.220</td>
      <td>10.50</td>
      <td>119.47</td>
      <td>2009</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("method")
```




    <pandas.core.groupby.groupby.DataFrameGroupBy object at 0x000001B2630C2320>




```python
df.groupby("method")["orbital_period"].mean()
```




    method
    Astrometry                          631.180000
    Eclipse Timing Variations          4751.644444
    Imaging                          118247.737500
    Microlensing                       3153.571429
    Orbital Brightness Modulation         0.709307
    Pulsar Timing                      7343.021201
    Pulsation Timing Variations        1170.000000
    Radial Velocity                     823.354680
    Transit                              21.102073
    Transit Timing Variations            79.783500
    Name: orbital_period, dtype: float64




```python
df.groupby("method")["orbital_period"].describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>count</th>
      <th>mean</th>
      <th>std</th>
      <th>min</th>
      <th>25%</th>
      <th>50%</th>
      <th>75%</th>
      <th>max</th>
    </tr>
    <tr>
      <th>method</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Astrometry</th>
      <td>2.0</td>
      <td>631.180000</td>
      <td>544.217663</td>
      <td>246.360000</td>
      <td>438.770000</td>
      <td>631.180000</td>
      <td>823.590000</td>
      <td>1016.000000</td>
    </tr>
    <tr>
      <th>Eclipse Timing Variations</th>
      <td>9.0</td>
      <td>4751.644444</td>
      <td>2499.130945</td>
      <td>1916.250000</td>
      <td>2900.000000</td>
      <td>4343.500000</td>
      <td>5767.000000</td>
      <td>10220.000000</td>
    </tr>
    <tr>
      <th>Imaging</th>
      <td>12.0</td>
      <td>118247.737500</td>
      <td>213978.177277</td>
      <td>4639.150000</td>
      <td>8343.900000</td>
      <td>27500.000000</td>
      <td>94250.000000</td>
      <td>730000.000000</td>
    </tr>
    <tr>
      <th>Microlensing</th>
      <td>7.0</td>
      <td>3153.571429</td>
      <td>1113.166333</td>
      <td>1825.000000</td>
      <td>2375.000000</td>
      <td>3300.000000</td>
      <td>3550.000000</td>
      <td>5100.000000</td>
    </tr>
    <tr>
      <th>Orbital Brightness Modulation</th>
      <td>3.0</td>
      <td>0.709307</td>
      <td>0.725493</td>
      <td>0.240104</td>
      <td>0.291496</td>
      <td>0.342887</td>
      <td>0.943908</td>
      <td>1.544929</td>
    </tr>
    <tr>
      <th>Pulsar Timing</th>
      <td>5.0</td>
      <td>7343.021201</td>
      <td>16313.265573</td>
      <td>0.090706</td>
      <td>25.262000</td>
      <td>66.541900</td>
      <td>98.211400</td>
      <td>36525.000000</td>
    </tr>
    <tr>
      <th>Pulsation Timing Variations</th>
      <td>1.0</td>
      <td>1170.000000</td>
      <td>NaN</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
      <td>1170.000000</td>
    </tr>
    <tr>
      <th>Radial Velocity</th>
      <td>553.0</td>
      <td>823.354680</td>
      <td>1454.926210</td>
      <td>0.736540</td>
      <td>38.021000</td>
      <td>360.200000</td>
      <td>982.000000</td>
      <td>17337.500000</td>
    </tr>
    <tr>
      <th>Transit</th>
      <td>397.0</td>
      <td>21.102073</td>
      <td>46.185893</td>
      <td>0.355000</td>
      <td>3.160630</td>
      <td>5.714932</td>
      <td>16.145700</td>
      <td>331.600590</td>
    </tr>
    <tr>
      <th>Transit Timing Variations</th>
      <td>3.0</td>
      <td>79.783500</td>
      <td>71.599884</td>
      <td>22.339500</td>
      <td>39.675250</td>
      <td>57.011000</td>
      <td>108.505500</td>
      <td>160.000000</td>
    </tr>
  </tbody>
</table>
</div>



# İleri Toplulaştırma İşlemleri (Aggregate, filter, transform, apply)


```python
import pandas as pd
df = pd.DataFrame({'gruplar': ['A', 'B', 'C', 'A', 'B', 'C'],
                   'degisken1': [10,23,33,22,11,99],
                   'degisken2': [100,253,333,262,111,969]},
                   columns = ['gruplar', 'degisken1', 'degisken2'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gruplar</th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>10</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>23</td>
      <td>253</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>33</td>
      <td>333</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A</td>
      <td>22</td>
      <td>262</td>
    </tr>
    <tr>
      <th>4</th>
      <td>B</td>
      <td>11</td>
      <td>111</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>99</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
#aggregate
```


```python
df.groupby("gruplar").mean()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
    <tr>
      <th>gruplar</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>16</td>
      <td>181</td>
    </tr>
    <tr>
      <th>B</th>
      <td>17</td>
      <td>182</td>
    </tr>
    <tr>
      <th>C</th>
      <td>66</td>
      <td>651</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("gruplar").aggregate([min, np.median, max])
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="3" halign="left">degisken1</th>
      <th colspan="3" halign="left">degisken2</th>
    </tr>
    <tr>
      <th></th>
      <th>min</th>
      <th>median</th>
      <th>max</th>
      <th>min</th>
      <th>median</th>
      <th>max</th>
    </tr>
    <tr>
      <th>gruplar</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>10</td>
      <td>16</td>
      <td>22</td>
      <td>100</td>
      <td>181</td>
      <td>262</td>
    </tr>
    <tr>
      <th>B</th>
      <td>11</td>
      <td>17</td>
      <td>23</td>
      <td>111</td>
      <td>182</td>
      <td>253</td>
    </tr>
    <tr>
      <th>C</th>
      <td>33</td>
      <td>66</td>
      <td>99</td>
      <td>333</td>
      <td>651</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("gruplar").aggregate({"degisken1": "min", "degisken2": "max"})
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
    <tr>
      <th>gruplar</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>10</td>
      <td>262</td>
    </tr>
    <tr>
      <th>B</th>
      <td>11</td>
      <td>253</td>
    </tr>
    <tr>
      <th>C</th>
      <td>33</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
#filter
```


```python
import pandas as pd
df = pd.DataFrame({'gruplar': ['A', 'B', 'C', 'A', 'B', 'C'],
                   'degisken1': [10,23,33,22,11,99],
                   'degisken2': [100,253,333,262,111,969]},
                   columns = ['gruplar', 'degisken1', 'degisken2'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gruplar</th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>10</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>23</td>
      <td>253</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>33</td>
      <td>333</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A</td>
      <td>22</td>
      <td>262</td>
    </tr>
    <tr>
      <th>4</th>
      <td>B</td>
      <td>11</td>
      <td>111</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>99</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
def filter_func(x):
    return x["degisken1"].std() > 9
```


```python
df.groupby("gruplar").std()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
    <tr>
      <th>gruplar</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>8.485281</td>
      <td>114.551299</td>
    </tr>
    <tr>
      <th>B</th>
      <td>8.485281</td>
      <td>100.409163</td>
    </tr>
    <tr>
      <th>C</th>
      <td>46.669048</td>
      <td>449.719913</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("gruplar").filter(filter_func)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gruplar</th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>33</td>
      <td>333</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>99</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
#transform
```


```python
import pandas as pd
df = pd.DataFrame({'gruplar': ['A', 'B', 'C', 'A', 'B', 'C'],
                   'degisken1': [10,23,33,22,11,99],
                   'degisken2': [100,253,333,262,111,969]},
                   columns = ['gruplar', 'degisken1', 'degisken2'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gruplar</th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>10</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>23</td>
      <td>253</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>33</td>
      <td>333</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A</td>
      <td>22</td>
      <td>262</td>
    </tr>
    <tr>
      <th>4</th>
      <td>B</td>
      <td>11</td>
      <td>111</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>99</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
df["degisken1"]*9
```




    0     90
    1    207
    2    297
    3    198
    4     99
    5    891
    Name: degisken1, dtype: int64




```python
df_a = df.iloc[:,1:3]
```


```python
df_a.transform(lambda x: (x-x.mean()) / x.std())
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>-0.687871</td>
      <td>-0.738461</td>
    </tr>
    <tr>
      <th>1</th>
      <td>-0.299074</td>
      <td>-0.263736</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0.000000</td>
      <td>-0.015514</td>
    </tr>
    <tr>
      <th>3</th>
      <td>-0.328982</td>
      <td>-0.235811</td>
    </tr>
    <tr>
      <th>4</th>
      <td>-0.657963</td>
      <td>-0.704331</td>
    </tr>
    <tr>
      <th>5</th>
      <td>1.973890</td>
      <td>1.957853</td>
    </tr>
  </tbody>
</table>
</div>




```python
#apply
```


```python
import pandas as pd
df = pd.DataFrame({'gruplar': ['A', 'B', 'C', 'A', 'B', 'C'],
                   'degisken1': [10,23,33,22,11,99],
                   'degisken2': [100,253,333,262,111,969]},
                   columns = ['gruplar', 'degisken1', 'degisken2'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gruplar</th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>10</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>23</td>
      <td>253</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>33</td>
      <td>333</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A</td>
      <td>22</td>
      <td>262</td>
    </tr>
    <tr>
      <th>4</th>
      <td>B</td>
      <td>11</td>
      <td>111</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>99</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.apply(np.sum)
```




    gruplar      ABCABC
    degisken1       198
    degisken2      2028
    dtype: object




```python
df.drop("gruplar", axis = 1, inplace = True)
```


```python
df.apply(np.mean)
```




    degisken1     33.0
    degisken2    338.0
    dtype: float64




```python
import pandas as pd
df = pd.DataFrame({'gruplar': ['A', 'B', 'C', 'A', 'B', 'C'],
                   'degisken1': [10,23,33,22,11,99],
                   'degisken2': [100,253,333,262,111,969]},
                   columns = ['gruplar', 'degisken1', 'degisken2'])
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gruplar</th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>A</td>
      <td>10</td>
      <td>100</td>
    </tr>
    <tr>
      <th>1</th>
      <td>B</td>
      <td>23</td>
      <td>253</td>
    </tr>
    <tr>
      <th>2</th>
      <td>C</td>
      <td>33</td>
      <td>333</td>
    </tr>
    <tr>
      <th>3</th>
      <td>A</td>
      <td>22</td>
      <td>262</td>
    </tr>
    <tr>
      <th>4</th>
      <td>B</td>
      <td>11</td>
      <td>111</td>
    </tr>
    <tr>
      <th>5</th>
      <td>C</td>
      <td>99</td>
      <td>969</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.groupby("gruplar").apply(np.mean)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>degisken1</th>
      <th>degisken2</th>
    </tr>
    <tr>
      <th>gruplar</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>16.0</td>
      <td>181.0</td>
    </tr>
    <tr>
      <th>B</th>
      <td>17.0</td>
      <td>182.0</td>
    </tr>
    <tr>
      <th>C</th>
      <td>66.0</td>
      <td>651.0</td>
    </tr>
  </tbody>
</table>
</div>



# Pivot Tablolar


```python
import pandas as pd
import seaborn as sns
titanic = sns.load_dataset('titanic')
titanic.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>survived</th>
      <th>pclass</th>
      <th>sex</th>
      <th>age</th>
      <th>sibsp</th>
      <th>parch</th>
      <th>fare</th>
      <th>embarked</th>
      <th>class</th>
      <th>who</th>
      <th>adult_male</th>
      <th>deck</th>
      <th>embark_town</th>
      <th>alive</th>
      <th>alone</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>22.0</td>
      <td>1</td>
      <td>0</td>
      <td>7.2500</td>
      <td>S</td>
      <td>Third</td>
      <td>man</td>
      <td>True</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>no</td>
      <td>False</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>38.0</td>
      <td>1</td>
      <td>0</td>
      <td>71.2833</td>
      <td>C</td>
      <td>First</td>
      <td>woman</td>
      <td>False</td>
      <td>C</td>
      <td>Cherbourg</td>
      <td>yes</td>
      <td>False</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1</td>
      <td>3</td>
      <td>female</td>
      <td>26.0</td>
      <td>0</td>
      <td>0</td>
      <td>7.9250</td>
      <td>S</td>
      <td>Third</td>
      <td>woman</td>
      <td>False</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>yes</td>
      <td>True</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1</td>
      <td>1</td>
      <td>female</td>
      <td>35.0</td>
      <td>1</td>
      <td>0</td>
      <td>53.1000</td>
      <td>S</td>
      <td>First</td>
      <td>woman</td>
      <td>False</td>
      <td>C</td>
      <td>Southampton</td>
      <td>yes</td>
      <td>False</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>3</td>
      <td>male</td>
      <td>35.0</td>
      <td>0</td>
      <td>0</td>
      <td>8.0500</td>
      <td>S</td>
      <td>Third</td>
      <td>man</td>
      <td>True</td>
      <td>NaN</td>
      <td>Southampton</td>
      <td>no</td>
      <td>True</td>
    </tr>
  </tbody>
</table>
</div>




```python
titanic.groupby("sex")[["survived"]].mean()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>survived</th>
    </tr>
    <tr>
      <th>sex</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>female</th>
      <td>0.742038</td>
    </tr>
    <tr>
      <th>male</th>
      <td>0.188908</td>
    </tr>
  </tbody>
</table>
</div>




```python
titanic.groupby(["sex","class"])[["survived"]].aggregate("mean").unstack()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead tr th {
        text-align: left;
    }

    .dataframe thead tr:last-of-type th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr>
      <th></th>
      <th colspan="3" halign="left">survived</th>
    </tr>
    <tr>
      <th>class</th>
      <th>First</th>
      <th>Second</th>
      <th>Third</th>
    </tr>
    <tr>
      <th>sex</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>female</th>
      <td>0.968085</td>
      <td>0.921053</td>
      <td>0.500000</td>
    </tr>
    <tr>
      <th>male</th>
      <td>0.368852</td>
      <td>0.157407</td>
      <td>0.135447</td>
    </tr>
  </tbody>
</table>
</div>




```python
#pivot ile table
```


```python
titanic.pivot_table("survived", index = "sex", columns = "class")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>class</th>
      <th>First</th>
      <th>Second</th>
      <th>Third</th>
    </tr>
    <tr>
      <th>sex</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>female</th>
      <td>0.968085</td>
      <td>0.921053</td>
      <td>0.500000</td>
    </tr>
    <tr>
      <th>male</th>
      <td>0.368852</td>
      <td>0.157407</td>
      <td>0.135447</td>
    </tr>
  </tbody>
</table>
</div>




```python
titanic.age.head()
```




    0    22.0
    1    38.0
    2    26.0
    3    35.0
    4    35.0
    Name: age, dtype: float64




```python
age = pd.cut(titanic["age"], [0, 18, 90])
age.head(10)
```




    0    (18, 90]
    1    (18, 90]
    2    (18, 90]
    3    (18, 90]
    4    (18, 90]
    5         NaN
    6    (18, 90]
    7     (0, 18]
    8    (18, 90]
    9     (0, 18]
    Name: age, dtype: category
    Categories (2, interval[int64]): [(0, 18] < (18, 90]]




```python
titanic.pivot_table("survived", ["sex", age], "class")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>class</th>
      <th>First</th>
      <th>Second</th>
      <th>Third</th>
    </tr>
    <tr>
      <th>sex</th>
      <th>age</th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th rowspan="2" valign="top">female</th>
      <th>(18, 90]</th>
      <td>0.909091</td>
      <td>1.000000</td>
      <td>0.511628</td>
    </tr>
    <tr>
      <th>NaN</th>
      <td>0.972973</td>
      <td>0.900000</td>
      <td>0.423729</td>
    </tr>
    <tr>
      <th rowspan="2" valign="top">male</th>
      <th>(18, 90]</th>
      <td>0.800000</td>
      <td>0.600000</td>
      <td>0.215686</td>
    </tr>
    <tr>
      <th>NaN</th>
      <td>0.375000</td>
      <td>0.071429</td>
      <td>0.133663</td>
    </tr>
  </tbody>
</table>
</div>



# Dış Kaynaklı Veri Okumak


```python
import pandas as pd
```


```python
?pd.read_csv
```


    [1;31mSignature:[0m [0mpd[0m[1;33m.[0m[0mread_csv[0m[1;33m([0m[0mfilepath_or_buffer[0m[1;33m,[0m [0msep[0m[1;33m=[0m[1;34m','[0m[1;33m,[0m [0mdelimiter[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mheader[0m[1;33m=[0m[1;34m'infer'[0m[1;33m,[0m [0mnames[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mindex_col[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0musecols[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0msqueeze[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mprefix[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mmangle_dupe_cols[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mdtype[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mengine[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mconverters[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mtrue_values[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mfalse_values[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mskipinitialspace[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mskiprows[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mnrows[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mna_values[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mkeep_default_na[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mna_filter[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mverbose[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mskip_blank_lines[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mparse_dates[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0minfer_datetime_format[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mkeep_date_col[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mdate_parser[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mdayfirst[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0miterator[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mchunksize[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mcompression[0m[1;33m=[0m[1;34m'infer'[0m[1;33m,[0m [0mthousands[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mdecimal[0m[1;33m=[0m[1;34mb'.'[0m[1;33m,[0m [0mlineterminator[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mquotechar[0m[1;33m=[0m[1;34m'"'[0m[1;33m,[0m [0mquoting[0m[1;33m=[0m[1;36m0[0m[1;33m,[0m [0mescapechar[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mcomment[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mencoding[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mdialect[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0mtupleize_cols[0m[1;33m=[0m[1;32mNone[0m[1;33m,[0m [0merror_bad_lines[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mwarn_bad_lines[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mskipfooter[0m[1;33m=[0m[1;36m0[0m[1;33m,[0m [0mdoublequote[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mdelim_whitespace[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mlow_memory[0m[1;33m=[0m[1;32mTrue[0m[1;33m,[0m [0mmemory_map[0m[1;33m=[0m[1;32mFalse[0m[1;33m,[0m [0mfloat_precision[0m[1;33m=[0m[1;32mNone[0m[1;33m)[0m[1;33m[0m[0m
    [1;31mDocstring:[0m
    Read CSV (comma-separated) file into DataFrame
    
    Also supports optionally iterating or breaking of the file
    into chunks.
    
    Additional help can be found in the `online docs for IO Tools
    <http://pandas.pydata.org/pandas-docs/stable/io.html>`_.
    
    Parameters
    ----------
    filepath_or_buffer : str, pathlib.Path, py._path.local.LocalPath or any \
    object with a read() method (such as a file handle or StringIO)
        The string could be a URL. Valid URL schemes include http, ftp, s3, and
        file. For file URLs, a host is expected. For instance, a local file could
        be file://localhost/path/to/table.csv
    sep : str, default ','
        Delimiter to use. If sep is None, the C engine cannot automatically detect
        the separator, but the Python parsing engine can, meaning the latter will
        be used and automatically detect the separator by Python's builtin sniffer
        tool, ``csv.Sniffer``. In addition, separators longer than 1 character and
        different from ``'\s+'`` will be interpreted as regular expressions and
        will also force the use of the Python parsing engine. Note that regex
        delimiters are prone to ignoring quoted data. Regex example: ``'\r\t'``
    delimiter : str, default ``None``
        Alternative argument name for sep.
    delim_whitespace : boolean, default False
        Specifies whether or not whitespace (e.g. ``' '`` or ``'\t'``) will be
        used as the sep. Equivalent to setting ``sep='\s+'``. If this option
        is set to True, nothing should be passed in for the ``delimiter``
        parameter.
    
        .. versionadded:: 0.18.1 support for the Python parser.
    
    header : int or list of ints, default 'infer'
        Row number(s) to use as the column names, and the start of the
        data.  Default behavior is to infer the column names: if no names
        are passed the behavior is identical to ``header=0`` and column
        names are inferred from the first line of the file, if column
        names are passed explicitly then the behavior is identical to
        ``header=None``. Explicitly pass ``header=0`` to be able to
        replace existing names. The header can be a list of integers that
        specify row locations for a multi-index on the columns
        e.g. [0,1,3]. Intervening rows that are not specified will be
        skipped (e.g. 2 in this example is skipped). Note that this
        parameter ignores commented lines and empty lines if
        ``skip_blank_lines=True``, so header=0 denotes the first line of
        data rather than the first line of the file.
    names : array-like, default None
        List of column names to use. If file contains no header row, then you
        should explicitly pass header=None. Duplicates in this list will cause
        a ``UserWarning`` to be issued.
    index_col : int or sequence or False, default None
        Column to use as the row labels of the DataFrame. If a sequence is given, a
        MultiIndex is used. If you have a malformed file with delimiters at the end
        of each line, you might consider index_col=False to force pandas to _not_
        use the first column as the index (row names)
    usecols : list-like or callable, default None
        Return a subset of the columns. If list-like, all elements must either
        be positional (i.e. integer indices into the document columns) or strings
        that correspond to column names provided either by the user in `names` or
        inferred from the document header row(s). For example, a valid list-like
        `usecols` parameter would be [0, 1, 2] or ['foo', 'bar', 'baz']. Element
        order is ignored, so ``usecols=[0, 1]`` is the same as ``[1, 0]``.
        To instantiate a DataFrame from ``data`` with element order preserved use
        ``pd.read_csv(data, usecols=['foo', 'bar'])[['foo', 'bar']]`` for columns
        in ``['foo', 'bar']`` order or
        ``pd.read_csv(data, usecols=['foo', 'bar'])[['bar', 'foo']]``
        for ``['bar', 'foo']`` order.
    
        If callable, the callable function will be evaluated against the column
        names, returning names where the callable function evaluates to True. An
        example of a valid callable argument would be ``lambda x: x.upper() in
        ['AAA', 'BBB', 'DDD']``. Using this parameter results in much faster
        parsing time and lower memory usage.
    squeeze : boolean, default False
        If the parsed data only contains one column then return a Series
    prefix : str, default None
        Prefix to add to column numbers when no header, e.g. 'X' for X0, X1, ...
    mangle_dupe_cols : boolean, default True
        Duplicate columns will be specified as 'X', 'X.1', ...'X.N', rather than
        'X'...'X'. Passing in False will cause data to be overwritten if there
        are duplicate names in the columns.
    dtype : Type name or dict of column -> type, default None
        Data type for data or columns. E.g. {'a': np.float64, 'b': np.int32}
        Use `str` or `object` together with suitable `na_values` settings
        to preserve and not interpret dtype.
        If converters are specified, they will be applied INSTEAD
        of dtype conversion.
    engine : {'c', 'python'}, optional
        Parser engine to use. The C engine is faster while the python engine is
        currently more feature-complete.
    converters : dict, default None
        Dict of functions for converting values in certain columns. Keys can either
        be integers or column labels
    true_values : list, default None
        Values to consider as True
    false_values : list, default None
        Values to consider as False
    skipinitialspace : boolean, default False
        Skip spaces after delimiter.
    skiprows : list-like or integer or callable, default None
        Line numbers to skip (0-indexed) or number of lines to skip (int)
        at the start of the file.
    
        If callable, the callable function will be evaluated against the row
        indices, returning True if the row should be skipped and False otherwise.
        An example of a valid callable argument would be ``lambda x: x in [0, 2]``.
    skipfooter : int, default 0
        Number of lines at bottom of file to skip (Unsupported with engine='c')
    nrows : int, default None
        Number of rows of file to read. Useful for reading pieces of large files
    na_values : scalar, str, list-like, or dict, default None
        Additional strings to recognize as NA/NaN. If dict passed, specific
        per-column NA values.  By default the following values are interpreted as
        NaN: '', '#N/A', '#N/A N/A', '#NA', '-1.#IND', '-1.#QNAN', '-NaN', '-nan',
        '1.#IND', '1.#QNAN', 'N/A', 'NA', 'NULL', 'NaN', 'n/a', 'nan',
        'null'.
    keep_default_na : bool, default True
        Whether or not to include the default NaN values when parsing the data.
        Depending on whether `na_values` is passed in, the behavior is as follows:
    
        * If `keep_default_na` is True, and `na_values` are specified, `na_values`
          is appended to the default NaN values used for parsing.
        * If `keep_default_na` is True, and `na_values` are not specified, only
          the default NaN values are used for parsing.
        * If `keep_default_na` is False, and `na_values` are specified, only
          the NaN values specified `na_values` are used for parsing.
        * If `keep_default_na` is False, and `na_values` are not specified, no
          strings will be parsed as NaN.
    
        Note that if `na_filter` is passed in as False, the `keep_default_na` and
        `na_values` parameters will be ignored.
    na_filter : boolean, default True
        Detect missing value markers (empty strings and the value of na_values). In
        data without any NAs, passing na_filter=False can improve the performance
        of reading a large file
    verbose : boolean, default False
        Indicate number of NA values placed in non-numeric columns
    skip_blank_lines : boolean, default True
        If True, skip over blank lines rather than interpreting as NaN values
    parse_dates : boolean or list of ints or names or list of lists or dict, default False
    
        * boolean. If True -> try parsing the index.
        * list of ints or names. e.g. If [1, 2, 3] -> try parsing columns 1, 2, 3
          each as a separate date column.
        * list of lists. e.g.  If [[1, 3]] -> combine columns 1 and 3 and parse as
          a single date column.
        * dict, e.g. {'foo' : [1, 3]} -> parse columns 1, 3 as date and call result
          'foo'
    
        If a column or index contains an unparseable date, the entire column or
        index will be returned unaltered as an object data type. For non-standard
        datetime parsing, use ``pd.to_datetime`` after ``pd.read_csv``
    
        Note: A fast-path exists for iso8601-formatted dates.
    infer_datetime_format : boolean, default False
        If True and `parse_dates` is enabled, pandas will attempt to infer the
        format of the datetime strings in the columns, and if it can be inferred,
        switch to a faster method of parsing them. In some cases this can increase
        the parsing speed by 5-10x.
    keep_date_col : boolean, default False
        If True and `parse_dates` specifies combining multiple columns then
        keep the original columns.
    date_parser : function, default None
        Function to use for converting a sequence of string columns to an array of
        datetime instances. The default uses ``dateutil.parser.parser`` to do the
        conversion. Pandas will try to call `date_parser` in three different ways,
        advancing to the next if an exception occurs: 1) Pass one or more arrays
        (as defined by `parse_dates`) as arguments; 2) concatenate (row-wise) the
        string values from the columns defined by `parse_dates` into a single array
        and pass that; and 3) call `date_parser` once for each row using one or
        more strings (corresponding to the columns defined by `parse_dates`) as
        arguments.
    dayfirst : boolean, default False
        DD/MM format dates, international and European format
    iterator : boolean, default False
        Return TextFileReader object for iteration or getting chunks with
        ``get_chunk()``.
    chunksize : int, default None
        Return TextFileReader object for iteration.
        See the `IO Tools docs
        <http://pandas.pydata.org/pandas-docs/stable/io.html#io-chunking>`_
        for more information on ``iterator`` and ``chunksize``.
    compression : {'infer', 'gzip', 'bz2', 'zip', 'xz', None}, default 'infer'
        For on-the-fly decompression of on-disk data. If 'infer' and
        `filepath_or_buffer` is path-like, then detect compression from the
        following extensions: '.gz', '.bz2', '.zip', or '.xz' (otherwise no
        decompression). If using 'zip', the ZIP file must contain only one data
        file to be read in. Set to None for no decompression.
    
        .. versionadded:: 0.18.1 support for 'zip' and 'xz' compression.
    
    thousands : str, default None
        Thousands separator
    decimal : str, default '.'
        Character to recognize as decimal point (e.g. use ',' for European data).
    float_precision : string, default None
        Specifies which converter the C engine should use for floating-point
        values. The options are `None` for the ordinary converter,
        `high` for the high-precision converter, and `round_trip` for the
        round-trip converter.
    lineterminator : str (length 1), default None
        Character to break file into lines. Only valid with C parser.
    quotechar : str (length 1), optional
        The character used to denote the start and end of a quoted item. Quoted
        items can include the delimiter and it will be ignored.
    quoting : int or csv.QUOTE_* instance, default 0
        Control field quoting behavior per ``csv.QUOTE_*`` constants. Use one of
        QUOTE_MINIMAL (0), QUOTE_ALL (1), QUOTE_NONNUMERIC (2) or QUOTE_NONE (3).
    doublequote : boolean, default ``True``
       When quotechar is specified and quoting is not ``QUOTE_NONE``, indicate
       whether or not to interpret two consecutive quotechar elements INSIDE a
       field as a single ``quotechar`` element.
    escapechar : str (length 1), default None
        One-character string used to escape delimiter when quoting is QUOTE_NONE.
    comment : str, default None
        Indicates remainder of line should not be parsed. If found at the beginning
        of a line, the line will be ignored altogether. This parameter must be a
        single character. Like empty lines (as long as ``skip_blank_lines=True``),
        fully commented lines are ignored by the parameter `header` but not by
        `skiprows`. For example, if ``comment='#'``, parsing
        ``#empty\na,b,c\n1,2,3`` with ``header=0`` will result in 'a,b,c' being
        treated as the header.
    encoding : str, default None
        Encoding to use for UTF when reading/writing (ex. 'utf-8'). `List of Python
        standard encodings
        <https://docs.python.org/3/library/codecs.html#standard-encodings>`_
    dialect : str or csv.Dialect instance, default None
        If provided, this parameter will override values (default or not) for the
        following parameters: `delimiter`, `doublequote`, `escapechar`,
        `skipinitialspace`, `quotechar`, and `quoting`. If it is necessary to
        override values, a ParserWarning will be issued. See csv.Dialect
        documentation for more details.
    tupleize_cols : boolean, default False
        .. deprecated:: 0.21.0
           This argument will be removed and will always convert to MultiIndex
    
        Leave a list of tuples on columns as is (default is to convert to
        a MultiIndex on the columns)
    error_bad_lines : boolean, default True
        Lines with too many fields (e.g. a csv line with too many commas) will by
        default cause an exception to be raised, and no DataFrame will be returned.
        If False, then these "bad lines" will dropped from the DataFrame that is
        returned.
    warn_bad_lines : boolean, default True
        If error_bad_lines is False, and warn_bad_lines is True, a warning for each
        "bad line" will be output.
    low_memory : boolean, default True
        Internally process the file in chunks, resulting in lower memory use
        while parsing, but possibly mixed type inference.  To ensure no mixed
        types either set False, or specify the type with the `dtype` parameter.
        Note that the entire file is read into a single DataFrame regardless,
        use the `chunksize` or `iterator` parameter to return the data in chunks.
        (Only valid with C parser)
    memory_map : boolean, default False
        If a filepath is provided for `filepath_or_buffer`, map the file object
        directly onto memory and access the data directly from there. Using this
        option can improve performance because there is no longer any I/O overhead.
    
    Returns
    -------
    result : DataFrame or TextParser
    [1;31mFile:[0m      c:\program files (x86)\microsoft visual studio\shared\anaconda3_64\lib\site-packages\pandas\io\parsers.py
    [1;31mType:[0m      function




```python
#csv okuma
pd.read_csv("reading_data/ornekcsv.csv", sep = ";")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>78</td>
      <td>12</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>78</td>
      <td>12</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>78</td>
      <td>324</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7</td>
      <td>2</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>88</td>
      <td>23</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>56</td>
      <td>11</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>12</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>56</td>
      <td>21</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>346</td>
      <td>2</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>5</td>
      <td>1</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>456</td>
      <td>21</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>3</td>
      <td>12</td>
      <td>88.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#txt okuma
pd.read_csv("reading_data/duz_metin.txt")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>1 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2 2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>3 2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>4 2</td>
    </tr>
    <tr>
      <th>3</th>
      <td>5 2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>6 2</td>
    </tr>
    <tr>
      <th>5</th>
      <td>7 2</td>
    </tr>
    <tr>
      <th>6</th>
      <td>8 2</td>
    </tr>
    <tr>
      <th>7</th>
      <td>9 2</td>
    </tr>
    <tr>
      <th>8</th>
      <td>10 2</td>
    </tr>
  </tbody>
</table>
</div>




```python
#excel
pd.read_excel("reading_data/ornekx.xlsx")
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>78</td>
      <td>12</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>78</td>
      <td>12</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>78</td>
      <td>324</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7</td>
      <td>2</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>88</td>
      <td>23</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>56</td>
      <td>11</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>12</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>56</td>
      <td>21</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>346</td>
      <td>2</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>5</td>
      <td>1</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>456</td>
      <td>21</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>3</td>
      <td>12</td>
      <td>88.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df = pd.read_excel("reading_data/ornekx.xlsx")
```


```python
type(df)
```




    pandas.core.frame.DataFrame




```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>a</th>
      <th>b</th>
      <th>c</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>78</td>
      <td>12</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>78</td>
      <td>12</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>78</td>
      <td>324</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7</td>
      <td>2</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>88</td>
      <td>23</td>
      <td>5.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.columns = ("A","B","C")
```


```python
df
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>A</th>
      <th>B</th>
      <th>C</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>78</td>
      <td>12</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>78</td>
      <td>12</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>78</td>
      <td>324</td>
      <td>3.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>7</td>
      <td>2</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>88</td>
      <td>23</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>5</th>
      <td>6</td>
      <td>2</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>6</th>
      <td>56</td>
      <td>11</td>
      <td>6.0</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>12</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>8</th>
      <td>56</td>
      <td>21</td>
      <td>7.0</td>
    </tr>
    <tr>
      <th>9</th>
      <td>346</td>
      <td>2</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>10</th>
      <td>5</td>
      <td>1</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>11</th>
      <td>456</td>
      <td>21</td>
      <td>8.0</td>
    </tr>
    <tr>
      <th>12</th>
      <td>3</td>
      <td>12</td>
      <td>88.0</td>
    </tr>
  </tbody>
</table>
</div>




```python
#sıfırdan txt okuma
tips = pd.read_csv("reading_data/data.txt")
```


```python
tips.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>total_bill</th>
      <th>tip</th>
      <th>sex</th>
      <th>smoker</th>
      <th>day</th>
      <th>time</th>
      <th>size</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>16.99</td>
      <td>1.01</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1</th>
      <td>10.34</td>
      <td>1.66</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>21.01</td>
      <td>3.50</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>3</td>
    </tr>
    <tr>
      <th>3</th>
      <td>23.68</td>
      <td>3.31</td>
      <td>Male</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>24.59</td>
      <td>3.61</td>
      <td>Female</td>
      <td>No</td>
      <td>Sun</td>
      <td>Dinner</td>
      <td>4</td>
    </tr>
  </tbody>
</table>
</div>



# Bonus: Problem Çözme ve Döküman Okuma Kültürü


```python
9 / 0
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-16-cb7aab57c3ef> in <module>
    ----> 1 9 / 0
    

    ZeroDivisionError: division by zero


# BOLUM SONU DEGERLENDIRMESI


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
