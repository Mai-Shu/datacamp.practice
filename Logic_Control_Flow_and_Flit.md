#Logic,Control Flow and Filt
Boolean logic is the foundation of decision-making in your Python programs. Learn about different comparison operators, how you can combine them with boolean operators and how to use the boolean outcomes in control structures. You'll also learn to filter data from Pandas DataFrames using logic.
##Comparison Operators
###Numpy Recap
```
import numpy as np
np_height = np.array([1.73, 1.68, 1.71, 1.89, 1.79])
np_weight = np.array([65.4, 59.2, 63.6, 88.4, 68.7])
bmi = np_weight / np_height ** 2
bmi
array([21.852, 20.975, 21.75, 24.747, 21.441])
bmi > 23
array([False, False, False, True, False], dtype=bool)
bmi[bmi > 23]
array([24.747])
```
Comparison operators: how Python values relate
###Numeric Comparisons
```
2 < 3
True

2==3
False

2 <= 3
True

3 <= 3
True

x = 2
y = 3
x < y
True
```
###Other Comparisons
```
"carl" < "chris"
True

3 < "chris"
TypeError: unorderable type: int() < str()

3 < 4.1
True

bmi
array([21.852, 20.975, 21.75, 24.747, 21.441])

bmi > 23
array([False, False, False, True, False], dtype=bool)
```
###Comparators
< strictly less than
<= less than or equal
> strictly greater than
>= greater than or equal
== equal
!= not equal

##Equality
To check if two Python values, or variables, are equal you can use ==. To check for inequality, you need !=. As a refresher, have a look at the following examples that all result in True. Feel free to try them out in the IPython Shell.
```
2 == (1 + 1)
"intermediate" != "python"
True != False
"Python" != "python"
```
When you write these comparisons in a script, you will need to wrap a print() function around them to see the output.
###Instructions
In the editor on the right write code to see if True equals False.
Write Python code to check if -5 * 15 is not equal to 75.
Ask Python whether the strings "pyscript" and "PyScript" are equal.
What happens if you compare booleans and integers? Write code to see if True and 1 are equal.
###Solution
```
# Comparison of booleans
print(True == False)

# Comparison of integers
print(-5 * 15 != 75)

# Comparison of strings
print("pyscript" == "PyScript")

# Compare a boolean with an integer
print(True == 1)

<script.py> output:
    False
    True
    False
    True

```
##Greater and less than
In the video, Filip also talked about the less than and greater than signs, < and > in Python. You can combine them with an equals sign: <= and >=. Pay attention: <= is valid syntax, but =< is not.

All Python expressions in the following code chunk evaluate to True:
```
3 < 4
3 <= 4
"alpha" <= "beta"
```
Remember that for string comparison, Python determines the relationship based on alphabetical order.
###Instructions
Write Python expressions, wrapped in a print() function, to check whether: - x is greater than or equal to -10. x has already been defined for you. - "test" is less than or equal to y. y has already been defined for you. - True is greater than False.
###Solution
```
# Comparison of integers
x = -3 * 6
print(x >= -10)


# Comparison of strings
y = "test"
print("test" <= y)


# Comparison of booleans
print(True > False)

<script.py> output:
    False
    True
    True
```
##Compare arrays
Out of the box, you can also use comparison operators with Numpy arrays.

Remember areas, the list of area measurements for different rooms in your house from the previous course? This time there's two Numpy arrays: my_house and your_house. They both contain the areas for the kitchen, living room, bedroom and bathroom in the same order, so you can compare them.
###Instructions
Using comparison operators, generate boolean arrays that answer the following questions: - Which areas in my_house are greater than or equal to 18? - You can also compare two Numpy arrays element-wise. Which areas in my_house are smaller than the ones in your_house?
Make sure to wrap both commands in print() statement, so that you can inspect the output.
###Solution
```
# Create arrays
import numpy as np
my_house = np.array([18.0, 20.0, 10.75, 9.50])
your_house = np.array([14.0, 24.0, 14.25, 9.0])

# my_house greater than or equal to 18
print(my_house >= 18)

# my_house less than your_house
print(my_house < your_house)


<script.py> output:
    [ True  True False False]
    [False  True  True False]

```
##Boolean Operators
and
or
not
###and
True and True
True

False and True
False

True and False
False

False and False
False

x = 12
True       True
x > 5 and x < 15
True

###or
True or True
True

False or True
True

True or False
True

False or False
False

y = 5
y < 7 or y > 13
True

###not
not True
False

not False
True
###Numpy
```
bmi # calculation of bmi left out
array([21.852, 20.975, ,21.75, 24.747, 21.441])
bmi > 21 
array([True, False, True, True, True], dtype=bool)
bmi < 22 
array([True, True, True, False, True], dtype=bool)

bmi > 21 and bmi < 22
ValueError: The truth value of an array with more than one element is ambiguous. Use a.any() or a.all()
#logical_and()
#logical_or()
#logical_not()

np.logical_and(bmi > 21, bmi < 22)
array([True, False, True, False, True], dtype=bool)

bmi[np.logica_and(bmi > 21, bmi <22)]
array([21.852, 21.75, 21.441])
```
##and, or, not(1)
A boolean is either 1 or 0, True or False. With boolean operators such as and, or and not, you can combine these booleans to perform more advanced queries on your data.
In the sample code on the right, two variables are defined: my_kitchen and your_kitchen, representing areas.
###Instructions
Write Python expressions, wrapped in a print() function, to check whether: - my_kitchen is bigger than 10 and smaller than 18. - my_kitchen is smaller than 14 or bigger than 17. - double the area of my_kitchen is smaller than triple the area of your_kitchen.
###Solution
```
# Define variables
my_kitchen = 18.0
your_kitchen = 14.0

# my_kitchen bigger than 10 and smaller than 18?
print(my_kitchen > 10 and my_kitchen < 18)

# my_kitchen smaller than 14 or bigger than 17?
print(my_kitchen < 14 or my_kitchen > 17)

# Double my_kitchen smaller than triple your_kitchen?
print(2 * my_kitchen < 3 *  your_kitchen)


<script.py> output:
    False
    True
    True
```
##and, or, not(2)
To see if you completely understood the boolean operators, have a look at the following piece of Python code:
```
x = 8
y = 9
not(not(x < 3) and not(y > 14 or y > 10))
```
What will the result be if you execute these three commands in the IPython Shell?

NB: Notice that not has a higher priority than and and or, it is executed first.
possible:
A True 

B False 

C Running these commands will result in an error.

Ans: B
##Boolean operators with Numpy
Before, the operational operators like < and >= worked with Numpy arrays out of the box. Unfortunately, this is not true for the boolean operators and, or, and not.

To use these operators with Numpy, you will need np.logical_and(), np.logical_or() and np.logical_not(). Here's an example on the my_house and your_house arrays from before to give you an idea:
```
logical_and(your_house > 13, 
            your_house < 15)
```
###Instructions
Generate boolean arrays that answer the following questions: - Which areas in my_house are greater than 18.5 or smaller than 10? - Which areas are smaller than 11 in both my_house and your_house? Make sure to wrap both commands in print() statement, so that you can inspect the output.
###Solution
```
# Create arrays
import numpy as np
my_house = np.array([18.0, 20.0, 10.75, 9.50])
your_house = np.array([14.0, 24.0, 14.25, 9.0])

# my_house greater than 18.5 or smaller than 10
print(np.logical_or(my_house > 18.5, my_house < 10))


# Both my_house and your_house smaller than 11
print(np.logical_and(my_house < 11, your_house < 11))


<script.py> output:
    [False  True False  True]
    [False False False  True]

```

##if, elif, else
###Overview
Comparison operators
<, >, >=, <=, ==, !=
Boolean operators
and, or, not
Conditional statements
if, else, elif
###if
```
z = 4
if z % 2 == 0:
    print("z is even")

z is even
    
```
###if condition: 
       expression
expression # not part of if

```
z = 4
if z % 2 == 0:
    print("checking" + str(z))
    print("z is even")
    
checking 4
z is even
```
```
##False, not executed
z = 5
if z % 2 == 0:
    print("checking" + str(z))
    print("z is even")
```
```
z = 5
if z % 2 == 0 : 
    print("z is even")
else:
    print("z is odd")

z is odd
```
###elif
if condition:
    expression
elif condition:
    expression
else:
    expression
```
z = 3
if z % 2 == 0: ##False
    print("z is divisible by 2")
elif z % 3 == 0: ##True
    print("z is divisible by 3")
else:
    print("z is neither divisible by 2 nor by 3")
    
z is divisible by 3
```
```
z = 6
if z % 2 == 0: ##True
    print("z is divisible by 2")
elif z % 3 == 0: ##Never reached
    print("z is divisible by 3")
else:
    print("z is neither divisible by 2 nor by 3")
    
z is divisible by 2

```
##Warmup
To experiment with if and else a bit, have a look at this code sample:
```
area = 10.0
if(area < 9) :
    print("small")
elif(area < 12) :
    print("medium")
else :
    print("large")
```
What will the output be if you run this piece of code in the IPython Shell?
###possible answers
A small 
B medium 
C large 
D The syntax is incorrect; this code will produce an error.
Ans: B
##if
It's time to take a closer look around in your house.
Two variables are defined in the sample code: room, a string that tells you which room of the house we're looking at, and area, the area of that room.
###Instructions
Examine the if statement that prints out "Looking around in the kitchen." if room equals "kit".
Write another if statement that prints out "big place!" if area is greater than 15.
###Solution
```
# Define variables
room = "kit"
area = 14.0

# if statement for room
if room == "kit" :
    print("looking around in the kitchen.")

# if statement for area
if area > 15:
    print("big place!")
    
<script.py> output:
    looking around in the kitchen.
```
##Add else
On the right, the if construct for room has been extended with an else statement so that "looking around elsewhere." is printed if the condition room = "kit" evaluates to False.
Can you do a similar thing to add more functionality to the if construct for area?
###Instructions
Add an else statement to the second control structure so that "pretty small." is printed out if area > 15 evaluates to False.
###Solution
```
# Define variables
room = "kit"
area = 14.0

# if-else construct for room
if room == "kit" :
    print("looking around in the kitchen.")
else :
    print("looking around elsewhere.")

# if-else construct for area
if area > 15 :
    print("big place!")
else : 
    print("pretty small.")
    
<script.py> output:
    looking around in the kitchen.
    pretty small.

```
##Customize further:elif
It's also possible to have a look around in the bedroom. The sample code contains an elif part that checks if room equals "bed". In that case, "looking around in the bedroom." is printed out.
It's up to you now! Make a similar addition to the second control structure to further customize the messages for different values of area.
###Instructions
Add an elif to the second control structure such that "medium size, nice!" is printed out if area is greater than 10.
###Solution
```
# Define variables
room = "bed"
area = 14.0

# if-elif-else construct for room
if room == "kit" :
    print("looking around in the kitchen.")
elif room == "bed":
    print("looking around in the bedroom.")
else :
    print("looking around elsewhere.")

# if-elif-else construct for area
if area > 15 :
    print("big place!")
elif area > 10:
    print("medium size, nice!")
else :
    print("pretty small.")

<script.py> output:
    looking around in the bedroom.
    medium size, nice!
```
##Filtering Pandas DataFrame
brics
###Goal
Select countries with area over 8 milliosn km**2
3 steps
select the area column
do comparison on area column
use result to select countries
Step1. Get column
!! Need Pandas Series, not DataFrame
ex. brics["area"]
Name: area, dtype: float64
Step2. Compare
ex. brics["area"]
Name: area, dtype: bool
Step3. Subset DF
is_huge = brics["area"] > 8
Name: area, dtype: bool
brics[is_huge]
!!!list content
###Summary
```
is_huge = brics["area"] > 8
brics[is_huge]
brics[brics["area"] > 8]
```
###Boolean operators
```
import numpy as np
np.logical_and(brics["area"] > 8, brics["area"] < 10)
Name: area, dtype: bool
bricks[np.logical_and(brics["area"] > 8, brics["area"] < 10)]
!!list items
```

##Driving right(1)
##Driving right(2)
##Cars per capita(1)
##Cars per capita(2)
