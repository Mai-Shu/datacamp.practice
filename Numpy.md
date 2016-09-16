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
In this chapter, we're going to dive into the world of baseball. Along the way, you'll get comfortable with the basics of Numpy, a powerful package to do data science.

A list baseball has already been defined in the Python script, representing the height of some baseball players in centimeters. Can you add some code here and there to create a Numpy array from it?
###Instructions
Import the numpy package as np, so that you can refer to numpy with np.
Use np.array() to create a Numpy array from baseball. Name this array np_baseball.
Print out the type of np_baseball to check that you got it right.

###Sloution
```
# Create list baseball 
baseball = [180, 215, 210, 210, 188, 176, 209, 200]

# Import the numpy package as np
import numpy as np

# Create a Numpy array from baseball: np_baseball
np_baseball = np.array(baseball)

# Print out type of np_baseball
print(type(np_baseball))

<script.py> output:
    <class 'numpy.ndarray'>

```


##Baseball players' height
You are a huge baseball fan. You decide to call the MLB (Major League Baseball) and ask around for some more statistics on the height of the main players. They pass along data on more than a thousand players, which is stored as a regular Python list: height. The height is expressed in inches. Can you make a Numpy array out of it and convert the units to centimeters?

height is already available and the numpy package is loaded, so you can start straight away (Source: stat.ucla.edu).
###Instructions
Create a Numpy array from height. Name this new array np_height.
Print np_height.
Multiply np_height with 0.0254 to convert all height measurements from inches to meters. Store the new values in a new array, np_height_m.
Print out np_height_m and check if the output makes sense.
###Solution
```
# height is available as a regular list

# Import numpy
import numpy as np

# Create a Numpy array from height: np_height
np_height = np.array(height)

# Print out np_height
print(np_height)

# Convert np_height to m: np_height_m
np_height_m = np_height * 0.0254

# Print np_height_m
print(np_height_m)


<script.py> output:
    [74 74 72 ..., 75 75 73]
    [ 1.8796  1.8796  1.8288 ...,  1.905   1.905   1.8542]
```
##Baseball players' BMI
The MLB also offers to let you analyze their weight data. Again, both are available as regular Python lists: height and weight. height is in inches and weight is in pounds.

It's now possible to calculate the BMI of each baseball player. Python code to convert height to a Numpy array with the correct units is already available in the workspace. Follow the instructions step by step and finish the game!
###Instructions
Create a Numpy array from the weight list with the correct units. Multiply by 0.453592 to go from pounds to kilograms. Store the resulting Numpy array as np_weight_kg.
Use np_height_m and np_weight_kg to calculate the BMI of each player. Use the following equation:
BMI=weight(kg)height(m)2
BMI=weight(kg)height(m)2
Save the resulting numpy array as bmi.
Print out bmi.
###Solution
```
# height and weight are available as a regular lists

# Import numpy
import numpy as np

# Create array from height with correct units: np_height_m
np_height_m = np.array(height) * 0.0254

# Create array from weight with correct units: np_weight_kg 
np_weight_kg = np.array(weight) * 0.453592

# Calculate the BMI: bmi
bmi = np_weight_kg / np_height_m ** 2

# Print out bmi
print(bmi)
<script.py> output:
    [ 23.11037639  27.60406069  28.48080465 ...,  25.62295933  23.74810865
      25.72686361]
```
##Lightweight baseball players
To subset both regular Python lists and Numpy arrays, you can use square brackets:
```
x = [4 , 9 , 6, 3, 1]
x[1]
import numpy as np
y = np.array(x)
y[1]
```
For Numpy specifically, you can also use boolean Numpy arrays:
```
high = y > 5
y[high]
```
The code that calculates the BMI of all baseball players is already included. Follow the instructions and reveal interesting things from the data!
###Instructions
Create a boolean Numpy array: the element of the array should be True if the corresponding baseball player's BMI is below 21. You can use the < operator for this. Name the array light.
Print the array light.
Print out a Numpy array with the BMIs of all baseball players whose BMI is below 21. Use light inside square brackets to do a selection on the bmi array.
###Solution
```
# height and weight are available as a regular lists

# Import numpy
import numpy as np

# Calculate the BMI: bmi
np_height_m = np.array(height) * 0.0254
np_weight_kg = np.array(weight) * 0.453592
bmi = np_weight_kg / np_height_m ** 2

# Create the light array
light = bmi < 21

# Print out light
print(light)

# Print out BMIs of all baseball players whose BMI is below 21
print(bmi[bmi < 21])
<script.py> output:
    [False False False ..., False False False]
    [ 20.54255679  20.54255679  20.69282047  20.69282047  20.34343189
      20.34343189  20.69282047  20.15883472  19.4984471   20.69282047
      20.9205219 ]
```

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
