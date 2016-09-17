#Loops
There are several techniques to repeatedly execute Python code. While loops are like repeated if statements; the for loop is there to iterate over all kinds of data structures. Learn all about them in this chapter.
##if-elif-else
```
z = 6
if z % 2 == 0: !!!!True
    print("z is divisible by 2") !!!!Executed
elif z % 3 == 0:
    print("z is divisible by 3")
else:
    print("z is neither divisible by 2 nor by 3")
```
Goes through construct only once!
while loop = repeated if statement
##While
```
while condition:
    expression
```
Numerically calculating model
"repeating action until condition is me"
Example
Error starts at 50
Divide error by 4 on every run
Continue until error no longer > 1
```
error = 50.0
while error > 1:
    error = error / 4 !!!!True
    print(error)

12.5
error = 3.125
while error > 1:
    error = error / 4
    print(error)
3.125

error = 0.78125
while error > 1:
    error = error / 4
    print(error)
0.78125
error = 50.0
while error > 1:  !!!! always True
    print(error)

50
50
...
50

```
##while loop
The while loop is like a repeated if statement. The code is executed over and over again, as long as the condition is True. Have another look at its recipe.
```
while condition :
    expression
```
##while:warming up
Can you tell how many printouts the following while loop will do?
```
x = 1
while x < 4 :
    print(x)
    x = x + 1
```
Possible answers
A 1
B 2
C 3
D 4
Ans: C

##Basic while loop
Below you can find the example from the video where the error variable, initially equal to 50.0, is divided by 4 and printed out on every run:
```
error = 50.0
while error > 1 :
    error = error / 4
    print(error)
```
This example will come in handy, because it's time to build a while loop yourself! We're going to code a while loop that implements a very basic control system for a reverted pendulum. If there's an offset from standing perfectly straight, the while loop will incrementally fix this offset.
###Instructions
Create the variable offset with an initial value of 8.
Code a while loop that keeps running as long as offset is not equal to 0. Inside the while loop:
Print out the sentence "correcting...".
Next, decrease the value of offset by 1. You can do this with offset = offset - 1.
Finally, print out offset so you can see how it changes.

###Solution
```
# Initialize offset
offset = 8


# Code the while loop
while offset != 0:
    print("correcting...")
    offset = offset - 1
    print(offset)
    
<script.py> output:
    correcting...
    7
    correcting...
    6
    correcting...
    5
    correcting...
    4
    correcting...
    3
    correcting...
    2
    correcting...
    1
    correcting...
    0
```
##Add conditionals
The while loop that corrects the offset is a good start, but what if offset is negative? You can try to run the sample code on the right where offset is initialized to -6, but your sessions will be disconnected. The while loop will never stop running, because offset will be further decreased on every run. offset != 0 will never become False and the while loop continues forever.
Fix things by putting an if-else statement inside the while loop.
###Instructions
Inside the while loop, replace offset = offset - 1 by an if-else statement:
If offset > 0, you should decrease offset by 1.
Else, you should increase offset by 1.
If you've coded things correctly, hitting Submit Answer should work this time.
###Solution
```
# Initialize offset
offset = -6

# Code the while loop
while offset != 0 :
    print("correcting...")
    if offset > 0:
        offset = offset - 1
    else:
        offset = offset + 1
    print(offset)
<script.py> output:
    correcting...
    -5
    correcting...
    -4
    correcting...
    -3
    correcting...
    -2
    correcting...
    -1
    correcting...
    0

```
##for loop
```
for var in seq:
    expression
```
"for each var in seq, execute expression"
###fam
```
fam = [1.73, 1.68, 1.71, 1.89]
print(fam)
[1.73, 1.68, 1.71, 1.89]
print(fam[0])
print(fam[1])
print(fam[2])
print(fam[3])
1.73
1.68
1.71
1.89
### for loop
```
fam = [1.73, 1.68, 1.71, 1.89]
for height in fam:
    print(height)
1.73
1.68
1.71
1.89
```
```
fam = [1.73, 1.68, 1.71, 1.89]
???
index 0: 1.73
index 1: 1.68
index 2: 1.71
index 3: 1.89
```
###enumerate
```
fam = [1.73, 1.68, 1.71, 1.89]
for index, height in enumerate(fam):
    print("index" + str(index) + ":" + str(height))
index 0: 1.73
index 1: 1.68
index 2: 1.71
index 3: 1.89
```
###Loop over string
```
for c in "family":
    print(c.capitalize())
F
A
M
I
L
Y
```
###Loop over a list
Have another look at the for loop that Filip showed in the video:Have another look at the for loop that Filip showed in the video:
```
fam = [1.73, 1.68, 1.71, 1.89]
for height in fam : 
    print(height)
```
As usual, you simply have to indent the code with 4 spaces to tell Python which code should be executed in the for loop.

The areas variable, containing the area of different rooms in your house, is already defined.
### Instructions
Write a for loop that iterates over all elements of the areas list and prints out every element separately.
###Solution
```
# areas list
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Code the for loop
for element in areas:
    print(element)
<script.py> output:
    11.25
    18.0
    20.0
    10.75
    9.5

```
##Indexed and values(1)
Using a for loop to iterate over a list only gives you access to every list element in each run, one after the other. If you also want to access the index information, so where the list element you're iterating over is located, you can use enumerate().

As an example, have a look at how the for loop from the video was converted:
```
fam = [1.73, 1.68, 1.71, 1.89]
for index, height in enumerate(fam) :
    print("index " + str(index) + ": " + str(height))
```
###Instructions
Adapt the for loop in the sample code to use enumerate(). On each run, a line of the form "room x: y" should be printed, where x is the index of the list element and y is the actual list element, i.e. the area. Make sure to print out this exact string, with the correct spacing.
###Solution
```
# areas list
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Change for loop to use enumerate()

for index, area in enumerate(areas):
    print("room " + str(index)+": "+ str(area))
    
<script.py> output:
    room 0: 11.25
    room 1: 18.0
    room 2: 20.0
    room 3: 10.75
    room 4: 9.5

```

##Indexed and values(2)
For non-programmer folks, room 0: 11.25 is strange. Wouldn't it be better if the count started at 1?
###Instructions
Adapt the print() function in the for loop on the right so that the first printout becomes "room 1: 11.25", the second one "room 2: 18.0" and so on.
###Solution
```
# areas list
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Code the for loop
for index, area in enumerate(areas) :
    print("room " + str(index + 1) + ": " + str(area))
    

<script.py> output:
    room 1: 11.25
    room 2: 18.0
    room 3: 20.0
    room 4: 10.75
    room 5: 9.5
```
##Loop over list of lists
Remember the house variable from the Intro to Python course? Have a look at its definition on the right. It's basically a list of lists, where each sublist contains the name and area of a room in your house.
It's up to you to build a for loop from scratch this time!
###Instructions
Write a for loop that goes through each sublist of houses and prints out the x is y sqm, where x is the name of the room and y is the area of the room.
###Solution
```
# house list of lists
house = [["hallway", 11.25], 
         ["kitchen", 18.0], 
         ["living room", 20.0], 
         ["bedroom", 10.75], 
         ["bathroom", 9.50]]
         
# Build a for loop from scratch
for name, area in house:
    print("the " + str(name) + " is " + str(area) + " sqm")
<script.py> output:
    the hallway is 11.25 sqm
    the kitchen is 18.0 sqm
    the living room is 20.0 sqm
    the bedroom is 10.75 sqm
    the bathroom is 9.5 sqm
```
##Looping Data Structure, Part1
###Dictionary
```
world = {"afghanistan":30.55,"albania":2.77,"algeria":39.21}
```
for var in seq:
    expression
```
world = {"afghanistan":30.55,"albania":2.77,"algeria":39.21}

for key, value in world:
    print(key + "--" + str(value))
ValueError: too many values to unpack(expected 2)
```
```
world = {"afghanistan":30.55,"albania":2.77,"algeria":39.21}
for key, value in world.items():
    print(key + "--" + str(value))
    
algeria -- 39.21
afhanistan -- 30.55
albania -- 2.77
```
```
world = {"afghanistan":30.55,"albania":2.77,"algeria":39.21}
for k, v in world.items():
    print(k+ "--" + str(v))
    
algeria -- 39.21
afhanistan -- 30.55
albania -- 2.77

###Numpy Arrays
```
import numpy as np
np_height = np.array([1.73, 1.68, 1.71, 1.89, 1.79])
np_weight = np.array([65.4, 59.2, 63.6, 88.4, 68.7])
bmi = np_weight / np_height ** 2

for val in bmi:
    print(val)
    
21.852
20.975
21.750
24.747
21.441
```
###2D Numpy Arrays
```
import numpy as np
np_height = np.array([1.73, 1.68, 1.71, 1.89, 1.79])
np_weight = np.array([65.4, 59.2, 63.6, 88.4, 68.7])
means = np.array([np_height, np_weight])

for val in means:
    print(val)
[1.73, 1.68, 1.71, 1.89, 1.79]
[65.4, 59.2, 63.6, 88.4, 68.7]
```
```
import numpy as np
np_height = np.array([1.73, 1.68, 1.71, 1.89, 1.79])
np_weight = np.array([65.4, 59.2, 63.6, 88.4, 68.7])
means = np.array([np_height, np_weight])

for val in np.nditer(means):
    print(val)
Output:    
1.73
1.68
1.71
1.89
1.79

Output(cont):
65.4
59.2
63.6
88.4
68.7
```
###Recap
Dictionary
for key, val in my_dict.items():
Numpy array
for val in np.nditer(my_array):
##Loop over dictionary
In Python 3, you need the items() method to loop over a dictionary:
```
world = { "afghanistan":30.55, 
          "albania":2.77,
          "algeria":39.21 }

for key, value in world.items() :
    print(key + " -- " + str(value))
```
Remember the europe dictionary that contained the names of some European countries as key and their capitals as corresponding value? Go ahead and write a loop to iterate over it!
###Instructions
Write a for loop that goes through each key:value pair of europe. On each iteration, "the capital of x is y" should be printed out, where x is the key and y is the value of the pair.
###Solution
```
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'bonn', 
          'norway':'oslo', 'italy':'rome', 'poland':'warsaw', 'australia':'vienna' }
          
# Iterate over europe
for key, value in europe.items():
    print("the capital of " + key + " is " + str(value))
    
<script.py> output:
    the capital of norway is oslo
    the capital of poland is warsaw
    the capital of spain is madrid
    the capital of australia is vienna
    the capital of germany is bonn
    the capital of france is paris
    the capital of italy is rome

```
##Loop over Numpy array
If you're dealing with a 1D Numpy array, looping over all elements can be as simple as:
```
for x in my_array :
    ...
```
If you're dealing with a 2D Numpy array, it's more complicated. A 2D array is built up of multiple 1D arrays. To explicitly iterate over all separate elements of a multi-dimensional array, you'll need this syntax:
```
for x in np.nditer(my_array) :
    ...
```
Two Numpy arrays that you might recognize from the intro course are available in your Python session: np_height, a Numpy array containing the heights of Major League Baseball players, and np_baseball, a 2D Numpy array that contains both the heights (first column) and weights (second column) of those players.
###Instructions
Import the numpy package under the local alias np.
Write a for loop that iterates over all elements in np_height and prints out "x inches" for each element, where x is the value in the array.
Write a for loop that visits every element of the np_baseball array and prints it out.
###Solution
```
Import numpy as np
import numpy as np

For loop over np_height
for value in np_height:
    print(str(value) + " inches")

For loop over np_baseball
for element in np.nditer(np_baseball):
    print(element)
    

```
##Looping Data Structure, Part2
###brics
```
import panda as pd
brics = pd.read_csv("brics.csv", index_col = 0)
```
```
for, first try
import pandas as pd
brics = pd.read_csv("brics.csv", index_col = 0)

for val in brics:
    print(val)
country
capital
area
population
```
###iterrows
```
import pandas as pd
brics = pd.read_csv("brics.csv", index_col = 0)
for lab, row  in brics.iterrows()  :
print(lab)
print(row)
```
###Selective print
```
import pandas as pd
brics = pd.read_csv("brics.csv", index_col = 0)

for lab, row in brics.iterrows():
    print(lab + ": " + row["capital"])
```
###Add column
```
import pandas as pd
brics = pd.read_csv("brics.csv", index_col = 0)

for lab, row in brics.iterrows():
    brics.loc[lab, "name_length"] = len(row["country"])
print(brics)

```
len(row["country"])
creating series on every iteration
###apply
```
import pandas as pd
brics = pd.read_csv("brics.csv", index_col = 0)
brics["name_length"] = brics["country"].apply(len)
print(brics)
```
##Loop over DataFrame(2)
Iterating over a Pandas DataFrame is typically done with the iterrows() method. Used in a for loop, every observation is iterated over and on every iteration the row label and actual row contents are available:
```
for lab, row in brics.iterrows() :
    ...
```
In this and the following exercises you will be working on the cars DataFrame. It contains information on the cars per capita and whether people drive right or left for seven countries in the world.
###Instructions
Write a for loop that iterates over the rows of cars and on each iteration perform two print() calls: one to print out the row label and one to print out all of the rows contents.
###Solution
```
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Iterate over rows of cars
for lab, row in cars.iterrows():
   print(lab)
   print(row)

<script.py> output:
    US
    cars_per_cap              809
    country         United States
    drives_right             True
    Name: US, dtype: object
    AUS
    cars_per_cap          731
    country         Australia
    drives_right        False
    Name: AUS, dtype: object
    JAP
    cars_per_cap      588
    country         Japan
    drives_right    False
    Name: JAP, dtype: object
    IN
    cars_per_cap       18
    country         India
    drives_right    False
    Name: IN, dtype: object
    RU
    cars_per_cap       200
    country         Russia
    drives_right      True
    Name: RU, dtype: object
    MOR
    cars_per_cap         70
    country         Morocco
    drives_right       True
    Name: MOR, dtype: object
    EG
    cars_per_cap       45
    country         Egypt
    drives_right     True
    Name: EG, dtype: object
```
##Loop over DataFrame(2)
The row data that's generated by iterrows() on every run is a Pandas Series. This format is not very convenient to print out. Luckily, you can easily select variables from the Pandas Series using square brackets:
```
for lab, row in brics.iterrows() :
    print(row['country'])
```
###Instructions
Adapt the code in the for loop such that the first iteration prints out "US: 809", the second iteration "AUS: 731", and so on. Make sure to print out this exact string, with the correct spacing.
###Solution
```
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Adapt for loop
for lab, row in cars.iterrows() :
    print(lab+ ": " + str(row['cars_per_cap']))

<script.py> output:
    US: 809
    AUS: 731
    JAP: 588
    IN: 18
    RU: 200
    MOR: 70
    EG: 45
```
##Add column(1)
In the video, Filip showed you how to add the length of the country names of the brics DataFrame in a new column:
```
for lab, row in brics.iterrows() :
    brics.loc[lab, "name_length"] = len(row["country"])
```
You can do similar things on the cars DataFrame.
###Instructions
Use a for loop to add a new column, named COUNTRY, that contains a uppercase version of the country names in the "country" column. You can use the string method upper() for this.
To see if your code worked, print out cars. Don't indent this code, so that it's not part of the for loop.

###Solution
```
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Code for loop that adds COUNTRY column
for lab, row in cars.iterrows():
    cars.loc[lab, "COUNTRY"] = row["country"].upper()


# Print cars
print(cars)
```
<script.py> output:
         cars_per_cap        country drives_right        COUNTRY
    US            809  United States         True  UNITED STATES
    AUS           731      Australia        False      AUSTRALIA
    JAP           588          Japan        False          JAPAN
    IN             18          India        False          INDIA
    RU            200         Russia         True         RUSSIA
    MOR            70        Morocco         True        MOROCCO
    EG             45          Egypt         True          EGYPT

##Add column(2)
Using iterrows() to iterate over every observation of a Pandas DataFrame is easy to understand, but not very efficient. On every iteration, you're creating a new Pandas Series.

If you want to add a column to a DataFrame by calling a function on another column, the iterrows() method in combination with a for loop is not the preferred way to go. Instead, you'll want to use apply().

Compare the iterrows() version with the apply() version to get the same result in the brics DataFrame:

for lab, row in brics.iterrows() :
    brics.loc[lab, "name_length"] = len(row["country"])

brics["name_length"] = presidents["country"].apply(len)

We can do a similar thing to call the upper() method on every name in the country column. However, upper() is a method, so we'll need a slightly different approach:

###Instructions
Replace the for loop with a one-liner that uses .apply(str.upper). The call should give the same result: a column COUNTRY should be added to cars, containing an uppercase version of the country names.
As usual, print out cars to see the fruits of your hard labor

###Solution
```
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Use .apply(str.upper)

cars["COUNTRY"] = cars["country"].apply(str.upper)
print(cars)

<script.py> output:
         cars_per_cap        country drives_right        COUNTRY
    US            809  United States         True  UNITED STATES
    AUS           731      Australia        False      AUSTRALIA
    JAP           588          Japan        False          JAPAN
    IN             18          India        False          INDIA
    RU            200         Russia         True         RUSSIA
    MOR            70        Morocco         True        MOROCCO
    EG             45          Egypt         True          EGYPT
```

