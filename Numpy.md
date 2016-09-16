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
As Filip explained before, Numpy is great to do vector arithmetic. If you compare its functionality with regular Python lists, however, some things have changed.

First of all, Numpy arrays cannot contain elements with different types. If you try to build such a list, some of the elments' types are changed to end up with a homogenous list. This is known as type coercion.

Second, the typical arithmetic operators, such as +, -, * and / have a different meaning for regular Python lists and Numpy arrays.

Have a look at this line of code:
```
np.array([True, 1, 2]) + np.array([3, 4, False])
```
Can you tell which code chunk builds the exact same Python object? The Numpy package is already imported as np, so you can start experimenting in the IPython Shell straight away!
###Solution
A np.array([True, 1, 2, 3, 4, False]) 

B np.array([4, 3, 0]) + np.array([0, 2, 2]) 

C np.array([1, 1, 2]) + np.array([3, 4, -1]) 

D np.array([0, 1, 2, 3, 4, 5])

Ans:B
##Subsetting Numpy Arrays
You've seen it with your own eyes: Python lists and Numpy arrays sometimes behave differently. Luckily, there are still certainties in this world. For example, subsetting (using the square bracket notation on lists or arrays) works exactly the same. To see this for yourself, try the following lines of code in the IPython Shell:
```
x = ["a", "b", "c"]
x[1]

np_x = np.array(x)
np_x[1]
```
The script on the right already contains code that imports numpy as np, and stores both the height and weight of the MLB players as Numpy arrays.
###Instructions
Subset np_weight: print out the element at index 50.
Print out a sub-array of np_height: It contains the elements at index 100 up to and including index 110
###Solution
```
# height and weight are available as a regular lists

# Import numpy
import numpy as np

# Store weight and height lists as numpy arrays
np_weight = np.array(weight)
np_height = np.array(height)

# Print out the weight at index 50
print(np_weight[50])

# Print out sub-array of np_height: index 100 up to and including index 110
print(np_height[100:111])


<script.py> output:
    200
    [73 74 72 73 69 72 73 75 75 73 72]
```
##2D Numpy Arrays
###Type of Numpy Arrays
```
import numpy as np
np_height = np.array([1.73, 1.68, 1.71, 1.89, 1.79])
np_weight = np.array([65.4, 59.2, 63.6, 88.4, 68.7])
type(np_height)
numpy.ndarray
type(np_weight)
numpy.ndarray
```
ndarray = N-dimensional array
###2D Numpy Arrays
```
np_2d = np.array([[1.73, 1.68, 1.71, 1.89, 1.79],
[65.4, 59.2, 63.6, 88.4, 68.7])
np_2d
array([[1.73, 1.68, 1.71, 1.89, 1.79],
[65.4, 59.2, 63.6, 88.4, 68.7]])
np_2d.shape
(2,5)
#2 rows, 5 coulmns
np.array([[1.73, 1.68, 1.71, 1.89, 1.79],
[65.4, 59.2, 63.6, 88.4, "68.7"]])

array([['1.73', '1.68', '1.71', '1.89', '1.79'],
['65.4', '59.2', '63.6', '88.4', '68.7']], dtype='<U32')
#Single type!
```
###Subsetting
```
np_2d[0]
array([1.73, 1.68, 1.71, 1.89, 1.79])

np_d2[0][2]
1.71

np_2d[0,2]
1.71

np_2d[:,1:3]
array([[1.68, 1.71], [59.2, 63.6]])
np_2d[1,:]
array([65.4, 59.2, 63.6, 88.4, 68.7])
```

##Your first 2D Numpy Arrays
Before working on the actual MLB data, let's try to create a 2D Numpy array from a small list of lists.

In this exercise, baseball is a list of lists. The main list contains 4 elements. Each of these elements is a list containing the height and the weight of 4 baseball players, in this order. baseball is already coded for you in the script.

###Instructions
Use np.array() to create a 2D Numpy array from baseball. Name it np_baseball.
Print out the type of np_baseball.
Print out the shape attribute of np_baseball. Use np_baseball.shape.
###Solution
```
# Create baseball, a list of lists
baseball = [[180, 78.4],
            [215, 102.7],
            [210, 98.5],
            [188, 75.2]]

# Import numpy
import numpy as np

# Create a 2D Numpy array from baseball: np_baseball
np_baseball = np.array(baseball)

# Print out the type of np_baseball
print(type(np_baseball))



# Print out the shape of np_baseball
print(np_baseball.shape)
<script.py> output:
    <class 'numpy.ndarray'>
    (4, 2)

```
##Baseball data in 2D form
You have another look at the MLB data and realize that it makes more sense to restructure all this information in a 2D Numpy array. This array should have 1015 rows, corresponding to the 1015 baseball players you have information on, and 2 columns (for height and weight).

The MLB was, again, very helpful and passed you the data in a different structure, a Python list of lists. In this list of lists, each sublist represents the height and weight of a single baseball player. The name of this embedded list is baseball.

Can you store the data as a 2D array to unlock Numpy's extra functionality?

###Instructions
Use np.array() to create a 2D Numpy array from baseball. Name it np_baseball.
Print out the shape attribute of np_baseball.
###Solution
```
# baseball is available as a regular list of lists

# Import numpy package
import numpy as np

# Create a 2D Numpy array from baseball: np_baseball
np_baseball = np.array(baseball)


# Print out the shape of np_baseball
print(np_baseball.shape)

<script.py> output:
    (1015, 2)
```
##Subsetting 2D Numpy Arrays
If your 2D Numpy array has a regular structure, i.e. each row and column has a fixed number of values, complicated ways of subsetting become very easy. Have a look at the code below where the elements "a" and "c" are extracted from a list of lists.
```
# regular list of lists
x = [["a", "b"], ["c", "d"]]
[x[0][0], x[1][0]]

# numpy
import numpy as np
np_x = np.array(x)
np_x[:,0]
```
For regular Python lists, this is a real pain. For 2D Numpy arrays, however, it's pretty intuitive! The indexes before the comma refer to the rows, while those after the comma refer to the columns. The : is for slicing; in this example, it tells Python to include all rows.

The code that converts the pre-loaded baseball list to a 2D Numpy array is already in the script. Add some lines to make the correct selections. Remember that in Python, the first element is at index 0!
###Instructions
Print out the 50th row of np_baseball.
Make a new variable, np_weight, containing the entire second column of np_baseball.
Select the height (first column) of the 124th baseball player in np_baseball and print it out.
###Solution
```
# baseball is available as a regular list of lists

# Import numpy package
import numpy as np

# Create np_baseball (2 cols)
np_baseball = np.array(baseball)

# Print out the 50th row of np_baseball
print(np_baseball[49,:])


# Select the entire second column of np_baseball: np_weight
np_weight = np_baseball[:,1]

# Print out height of 124th player
print(np_baseball[123,0])
<script.py> output:
    [ 70 195]
    210

<script.py> output:
    [ 70 195]
    75
```



##2D Arithmetic
Remember how you calculated the Body Mass Index for all baseball players? Numpy was able to perform all calculations element-wise. For 2D Numpy arrays this isn't any different! You can combine matrices with single numbers, with vectors, and with other matrices.

Execute the code below in the IPython shell and see if you understand:
```
import numpy as np
np_mat = np.array([[1, 2],
                   [3, 4],
                   [5, 6]])
np_mat * 2
np_mat + np.array([10, 10])
np_mat + np_mat
```
np_baseball is coded for you; it's again a 2D Numpy array with 3 columns representing height, weight and age.
###Instructions
You managed to get hold on the changes in weight, height and age of all baseball players. It is available as a 2D Numpy array, update. Add np_baseball and update and print out the result.
You want to convert the units of height and weight. As a first step, create a Numpy array with three values: 0.0254, 0.453592 and 1. Name this array conversion.
Multiply np_baseball with conversion and print out the result.
###Solution
```
# baseball is available as a regular list of lists
# update is available as 2D Numpy array

# Import numpy package
import numpy as np

# Create np_baseball (3 cols)
np_baseball = np.array(baseball)

# Print out addition of np_baseball and update
print(np_baseball + update)


# Create Numpy array: conversion
conversion = ([0.0254, 0.453592, 1])


# Print out product of np_baseball and conversion
print(np_baseball * conversion)

 
<script.py> output:
    [[  75.2303559   168.83775102   23.99      ]
     [  75.02614252  231.09732309   35.69      ]
     [  73.1544228   215.08167641   31.78      ]
     ..., 
     [  76.09349925  209.23890778   26.19      ]
     [  75.82285669  172.21799965   32.01      ]
     [  73.99484223  203.14402711   28.92      ]]
    [[  1.8796   81.64656  22.99   ]
     [  1.8796   97.52228  34.69   ]
     [  1.8288   95.25432  30.78   ]
     ..., 
     [  1.905    92.98636  25.19   ]
     [  1.905    86.18248  31.01   ]
     [  1.8542   88.45044  27.92   ]]
```

##Numpy:Basic statistics
###Data analysis
Get to know your data
Little data --> simply look at it
Big data -->
###City-wide survey
```
import numpy as np
np_city = ... # implementation left out
np_city
array([[1.64, 71.78],
       [1.37, 63.35],
       [1.6, 55.09],
       ....,
       [2.04, 74.85],
       [2.04, 68.72],
       [2.01, 73.57]])
```
###Numpy
```
np.mean(np_city[:,0])
1.7472
np.medidan(np_city[:,0])
1.75
np.corrcoef(np_city[:,0], np_city[:,1])
array([[1. , -0.01802],
       [-0.01801, 1. ]])
np.std(np_city[:,0])
0.1992
```
sum()
sort()
Enforce single data type:speed!
###Generate data
``` 
height = np.round(np.random.normal(1.75, 0.20, 5000), 2)
weight = np.round(np.random.normal(60.32, 15, 5000), 2)
(1.75, 0.20, 5000) ---> (distribution mean, distribution standard dev., number of samples)
np_city = np.column_stack((height, weight))
```
##Average versus median
You now know how to use Numpy functions to a get a better feeling for your data. It basically comes down to importing Numpy and then calling several simple functions on the Numpy arrays:
```
import numpy as np
x = [1, 4, 8, 10, 12]
np.mean(x)
np.median(x)
```
The baseball data is available as a 2D Numpy array with 3 columns (height, weight, age) and 1015 rows. The name of this Numpy array is np_baseball. After restructuring the data, however, you notice that some height values are abnormally high. Follow the instructions and discover which summary statistic is best suited if you're dealing with so-called outliers.
###Instructions
Create Numpy array np_height, that is equal to first column of np_baseball.
Print out the mean of np_height.
Print out the median of np_height.
###Solution
```
# np_baseball is available

# Import numpy
import numpy as np

# Create np_height from np_baseball
np_height = np_baseball[:,0]


# Print out the mean of np_height
print(np.mean(np_height))

# Print out the median of np_height
print(np.median(np_height))

<script.py> output:
    1586.46108374
    74.0

```


##Explore the baseball datas
Because the mean and median are so far apart, you decide to complain to the MLB. They find the error and send the corrected data over to you. It's again available as a 2D Numpy array np_baseball, with three columns.

The Python script on the right already includes code to print out informative messages with the different summary statistics. Can you finish the job?
###Instructions
The code to print out the mean height is already included. Complete the code for the median height. Replace None with the correct code.
Use np.std() on the first column of np_baseball to calculate stddev. Replace None with the correct code.
Do big players tend to be heavier? Use np.corrcoef() to store the correlation between the first and second column of np_baseball in corr. Replace None with the correct code.
###Solution
```
# np_baseball is available

# Import numpy
import numpy as np

# Print mean height (first column)
avg = np.mean(np_baseball[:,0])

print("Average: " + str(avg))

# Print median height. Replace 'None'
med = np.median(np_baseball[:,0])
print("Median: " + str(med))

# Print out the standard deviation on height. Replace 'None'
stddev = np.std(np_baseball[:,0])
print("Standard Deviation: " + str(stddev))

# Print out correlation between first and second column. Replace 'None'
corr = np.corrcoef([np_baseball[:,0], np_baseball[:,1]])
print("Correlation: " + str(corr))

<script.py> output:
    Average: 73.6896551724
    Median: 74.0
    Standard Deviation: 2.31279188105
    Correlation: [[ 1.          0.53153932]
     [ 0.53153932  1.        ]]
     
```
##Blend it all together
In the last few exercises you've learned everything there is to know about heights and weights of baseball players. Now it's time to dive into another sport: soccer.

You've contacted the FIFA for some data and they handed you two lists. The lists are the following: positions = ['GK', 'M', 'A', 'D', ...] heights = [191, 184, 185, 180, ...] Each element in the lists corresponds to a player. The first list, positions, contains strings representing each player's position. The possible positions are: 'GK' (goalkeeper), 'M' (midfield), 'A' (attack) and 'D' (defense). The second list, heights, contains integers representing the height of the player in cm. The first player in the lists is a goalkeeper and is pretty tall (191 cm).

You're fairly confident that the median height of goalkeepers is higher than that of other players on the soccer field. Some of your friends don't believe you, so you are determined to show them using the data you received from FIFA and your newly acquired Python skills.
###Instructions
Convert heights and positions, which are regular lists, to numpy arrays. Call them np_heights and np_positions.
Extract all the heights of the goalkeepers. You can use a little trick here: use np_positions == 'GK' as an index for np_heights. Assign the result to gk_heights.
Extract all the heights of the all the other players. This time use np_positions != 'GK' as an index for np_heights. Assign the result to other_heights.
Print out the median height of the goalkeepers using np.median(). Replace None with the correct code.
Do the same for the other players. Print out their median height. Replace None with the correct code.
###Solution
```
# heights and positions are available as lists

# Import numpy
import numpy as np

# Convert positions and heights to numpy arrays: np_positions, np_heights
np_heights = np.array(heights)
np_positions = np.array(positions)


# Heights of the goalkeepers: gk_heights
gk_heights = np_heights[np_positions == 'GK']


# Heights of the other players: other_heights
other_heights = np_heights[np_positions != 'GK']

# Print out the median height of goalkeepers. Replace 'None'
print("Median height of goalkeepers: " + str(np.median(gk_heights)))

# Print out the median height of other players. Replace 'None'
print("Median height of other players: " + str(np.median(other_heights)))

<script.py> output:
    Median height of goalkeepers: 188.0
    Median height of other players: 181.0

```


