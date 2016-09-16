#Numpy
Numpy is a Python package to efficiently do data science. Learn to work with the Numpy array, a faster and more powerful alternative to the list, and take your first steps in data exploration.

##Numpy
###Lists Recap
Powerful
Collection of values
Hold different types
Change,add,remove
Need for Data Science
--Mathematical operations over collections
--Speed
```
height = [1.73, 1.68, 1.71, 1.89, 1.79]
height
[1.73, 1.68, 1.71, 1.89, 1.79]
weight = [65.4,59.2,63.6,88.4,68.7]
weight
[65.4,59.2,63.6,88.4,68.7]
weight / height ** 2
TypeError: unsupported operand type(s) for **: 'list' and 'int'
```
###Solution:Numppy
Numeric Python
Alternative to Python list: Numpy Array
Calculation over entire arrays
Easy and Fast
Installation
In the terminal: pip3 install numpy
###Numpy
```
import numpy as np
np_height = np.array(height)
np_height
array([1.73, 1.68, 1.71, 1.89, 1.79])

np_weight
array([65.4, 59.2, 63.6, 88.4, 68.7])

bmi = np_weight / np_height ** 2
bmi
array([21.852, 20.975, 21.75, 24.747, 21.441])

```
###Comparison
```
height = [1.73, 1.68, 1.71, 1.89, 1.79]
weight = [65.4, 59.2, 63.6, 88.4, 68.7]
weight / height ** 2
TypeError: unsupported operand type(s) for **: 'list' and 'int'

np_height = np.array(height)
np_weight = np.array(weight)
np_weight / np_height ** 2
array([21.852, 20.957, 21.75, 24.747, 21.441])
```
###Numpy:remarks
```
np.array([1.0,"is",True])
array(['1.0','is','True'],dtype='<U32')
```
Numpy arrays:contain only one type
```
python_list = [1, 2, 3]
numpy_array = np.array([1, 2, 3])
python_list + python_list
[1, 2, 3, 1, 2, 3]
numpy_array + numpy_array
array([2, 4, 6])
```
### Numpy subsetting
```
bmi
array([21.852, 20.975, 21.75, 24.747, 21.441])
bmi[1]
20.975
bmi > 23
array([False,False,False,True,False],dtype=bool)
bmi[bmi > 23]
array([24.747])
```

##Your first Numpy array
##Baseball players' height
##Baseball players' BMI
##Lightweight baseball players
##Numpy side effects
##Subsetting Numpy Arrays
##2D Numpy Arrays
##Your first 2D Numpy Arrays
##Baseball data in 2D form
##Subsetting 2D Numpy Arrays
##2D Arithmetic
##Numpy:Basic statistics
##Average versus median
##Explore the baseball datas
##Blend it all together
