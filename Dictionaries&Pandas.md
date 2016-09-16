#Dictionaries&Pandas
Learn about the dictionary, an alternative to the Python list, and the Pandas DataFrame, the de facto standard to work with tabular data in Python. 
You will get hands-on practice with creating, manipulating and accessing the information you need from these data structures.
##Dictionaries,Part1
###List
```
pop = [30.55, 2.77, 39.21]
countries = ["afghanistan", "albania", "algeria"]
ind_alb = countries.index("albania")
ind_alb
1
pop[ind_alb]
2.77
```
Not convenient
Not intuitive
```
world = {"afghanistan":30.55, "albania":2.77,"algeria":39.21}
world["albania"]
2.77
```
dict_name[key]
result: value
##Motivation for dictionaries
To see why dictionaries are useful, have a look at the two lists defined on the right. countries contains the names of some European countries. capitals lists the corresponding names of their capital.
###Instructions
Use the index() method on countries to find the index of 'germany'. Store this index as ind_ger.
Use ind_ger to access the capital of Germany from the capitals list. Print it out.
###Solution
```
# Definition of countries and capital
countries = ['spain', 'france', 'germany', 'norway']
capitals = ['madrid', 'paris', 'berlin', 'oslo']

# Get index of 'germany': ind_ger
ind_ger = countries.index("germany")
# Use ind_ger to print out capital of Germany
print(capitals[ind_ger])
```
<script.py> output:
    berlin
##Create dictionary
The countries and capitals lists are again available in the script. It's your job to convert this data to a dictionary where the country names are the keys and the capitals are the corresponding values. As a refresher, here is a recipe for creating a dictionary:
```
my_dict = {
   "key1":"value1",
   "key2":"value2",
}
```
In this recipe, both the keys and the values are strings. This will also be the case for this exercise.
###Instructions
With the strings in countries and capitals, create a dictionary called europe with 4 key:value pairs. Beware of capitalization! Make sure you use lowercase characters everywhere.
Print out europe to see if the result is what you expected.
###Solution
```
# Definition of countries and capital
countries = ['spain', 'france', 'germany', 'norway']
capitals = ['madrid', 'paris', 'berlin', 'oslo']

# From string in countries and capitals, create dictionary europe
europe = {"spain": "madrid", "france":"paris", "germany":"berlin", "norway":"oslo"}

# Print europe
print(europe)
```
##Access dictionary
If the keys of a dictionary are chosen wisely, accessing the values in a dictionary is easy and intuitive. For example, to get the capital for France from europe you can use:
```
europe['france']
```
Here, 'france' is the key and 'paris' the value is returned.
###Instructions
Check out which keys are in europe by calling the keys() method on europe. Print out the result.
Print out the value that belongs to the key 'norway'.
###Solution
```
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'berlin', 'norway':'oslo' }

# Print out the keys in europe
print(europe.keys())

# Print out value that belongs to key 'norway'
print(europe['norway'])
<script.py> output:
    dict_keys(['france', 'germany', 'spain', 'norway'])
    oslo
```
##Dictionaries,Part2
###Recap
```
world = {"afghanistan":30.55, "albania":2.77, "algeria":39.21}
world["albania"]
2.77
world = {"afghanistan":30.55, "albania":2.77, "algeria":39.21, "albania":2.81}
world
{'afghanistan':30.55, 'albania':2.81, 'algeria':39.21}
#keys have to be "immutable" objects
{0:"hello", True:"dear", "two":"world"}
{0:'hello', True:'dear', 'two':'world'}
{["just","to","test"]:"value"}
TypeError: unhashable type: 'list'
```
###Prinicipality of Sealand
###Dictionary
```
world["sealand"] = 0.000027
world
{'afghanistan': 30.55, 'albania': 2.81, 'algeria': 39.21, 'sealand': 2.7e-05}

"sealand" in world
True
world["sealand"] = 0.000028
world
{'afghanistan': 30.55, 'albania': 2.81, 'algeria': 39.21, 'sealand': 2.8e-05}
del(world["sealand"])
{'afghanistan': 30.55, 'albania': 2.81, 'algeria': 39.21}
```
###List vs Dictionary
List: Select, update and remove:[]
Indexed by range of numbers
Collection of values order matters select entire subsets
Dictionary:Select, update and remove:[]
Indexed by unique keys
Lookup table with unique keys
##Dictionary Manipulation(1)
If you know how to access a dictionary, you can also assign a new value to it. To add a new key-value pair to europe you can use something like this:
```
europe['iceland'] = 'reykjavik'
```
###Instructions
Add the key 'italy' with the value 'rome' to europe.
To assert that 'italy' is now a key in europe, print out 'italy' in europe.
Add another key:value pair to europe: 'poland' is the key, 'warsaw' is the corresponding value.
Print out europe.
###Solution
```
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'berlin', 'norway':'oslo' }

# Add italy to europe
europe["italy"] = 'rome'

# Print out italy in europe
print("italy" in europe)


# Add poland to europe
europe["poland"] = 'warsaw'

# Print europe
print(europe)
```
##Dictionary Manipulation(2)
Somebody thought it would be funny to mess with your accurately generated dictionary. An adapted version of the europe dictionary is available in the script on the right.

Can you clean up? Do not do this by adapting the definition of europe, but by adding Python commands to the script to update and remove key:value pairs.
###Instructions
The capital of Germany is not 'bonn'; it's 'berlin'. Update its value.
Australia is not in Europe, Austria is! Remove they key 'australia' from europe.
Print out europe to see if your cleaning work paid off.
###Solution
```
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'bonn', 
          'norway':'oslo', 'italy':'rome', 'poland':'warsaw', 
          'australia':'vienna' }

# Update capital of germany
europe["germany"] = 'berlin'

# Remove australia
del(europe["australia"])

# Print europe
print(europe)

<script.py> output:
    {'france': 'paris', 'italy': 'rome', 'poland': 'warsaw', 'norway': 'oslo', 'spain': 'madrid', 'germany': 'berlin'}
```
##Dictionariception
Remember lists? They could contain anything, even other lists. Well, for dictionaries the same holds. Dictionaries can contain key:value pairs where the values are again dictionaries.

As an example, have a look at the script where another version of europe - the dictionary you've been working with all along - is coded. The keys are still the country names, but the values are dictionaries that contain more information than just the capital.

It's perfectly possible to chain square brackets to select elements. To fetch the population for spain from europe, for example, you need:
```
europe['spain']['population']
```
###Instructions
Use chained square brackets to select and print out the capital of France.
Create a dictionary, named data, with the keys capital and population. Set them to 'rome' and 59.83, respectively.
Add a new key-value pair to europe: the key is 'italy' and the value is data, the dictionary you just built.
###Solution
```
# Dictionary of dictionaries
europe = { 'spain': { 'capital':'madrid', 'population':46.77 },
           'france': { 'capital':'paris', 'population':66.03 },
           'germany': { 'capital':'berlin', 'population':80.62 },
           'norway': { 'capital':'oslo', 'population':5.084 } }
           
           
# Print out the capital of France
print(europe['france']['capital'])

# Create sub-dictionary data
data = {'capital': 'rome', 'population': 59.83}


# Add data to europe under key 'italy'
europe["italy"] = data

# Print europe
print(europe)

<script.py> output:
    paris
    {'italy': {'population': 59.83, 'capital': 'rome'}, 'france': {'population': 66.03, 'capital': 'paris'}, 'germany': {'population': 80.62, 'capital': 'berlin'}, 'spain': {'population': 46.77, 'capital': 'madrid'}, 'norway': {'population': 5.084, 'capital': 'oslo'}}
```
##Pandas,Part1
###Tabular dataset examples
file:///Users/Hsia/Desktop/Screen%20Shot%202016-09-16%20at%2013.39.46.png
row = observations
column = variable
file:///Users/Hsia/Desktop/Screen%20Shot%202016-09-16%20at%2013.41.22.png
###Datasets in Python
2D Numpy array
one data type
country --> str
capital --> str
area --> float
population --> float
Pandas!
High level data manipulation tool
Wes McKinney
Built on Numpy
DataFrame
###DataFrame
columns with different types
###DataFrame form Dictionary
```
dict = {"country":["Brazil", "Russia",...]}
key(column labels)
values(data, column by column)
import pandas as pd
brics = pd.DataFrame(dict)
```
###DataFrame from Dictionary(2)
```
##change name of items
brics.index = ["BR", "RU",...,"SA"]
brics
```
###DataFrame from CSV file
```
CSV = comma-separated values
brics = pd.read_csv("path/to/brics.csv")
##change first column to item names
brics = pd.read_csv("path/to/brics.csv", index_col = 0)
```
##Dictionary to DataFrame(1)
Pandas is an open source library, providing high-performance, easy-to-use data structures and data analysis tools for Python. Sounds promising!

The DataFrame is one of Pandas' most important data structures. It's basically a way to store tabular data, where you can label the rows and the columns. One way to build a DataFrame is from a dictionary.

In the exercises that follow you will be working with vehicle data in different countries. Each observation corresponds to a country and the columns give information about the number of vehicles per capita, whether people drive left or right, and so on.

Three lists are defined in the script: - names, containing the country names for which data is available. - dr, a list with booleans that tells whether people drive left or right in the corresponding country. - cpc, the number of motor vehicles per 1000 people in the corresponding country.

Each dictionary key is a column label and each value is a list which contains the column elements.
###Instructions
Import pandas as pd.
Use the pre-defined lists to create dictionary, called my_dict. There should be three key value pairs:
key 'country' and value names.
key 'drives_right' and value dr.
key 'cars_per_cap' and value cpc.
Use pd.DataFrame() to turn your dict into a DataFrame called cars.
Print out cars and see how beautiful it is.
###Solution
```
# Pre-defined lists
names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
dr =  [True, False, False, False, True, True, True]
cpc = [809, 731, 588, 18, 200, 70, 45]

# Import pandas as pd
import pandas as pd


# Create dictionary my_dict with three key:value pairs: my_dict
my_dict = {'country': names, 'drives_right': dr, 'cars_per_cap': cpc}



# Build a DataFrame cars from my_dict: cars
cars = pd.DataFrame(my_dict)

# Print cars
print(cars)
<script.py> output:
       cars_per_cap        country drives_right
    0           809  United States         True
    1           731      Australia        False
    2           588          Japan        False
    3            18          India        False
    4           200         Russia         True
    5            70        Morocco         True
    6            45          Egypt         True
```
##Dictionary to DataFrame(2)
The Python code that solves the previous exercise is included on the right. Have you noticed that the row labels (so the labels for the different observations) where automatically set to integers from 0 up to 6?

To solve this a list row_labels has been created. You can use it to specify the row labels of the cars DataFrame. You do this by setting the index attribute of cars, that you can access as cars.index.
###Instructions
Hit Submit Answer to see that, indeed, the row labels are not correctly set.
Specify the row labels by setting cars.index equal to row_labels.
Print out cars again and check if the row labels are correct this time.
###Solution
```
import pandas as pd

# Build cars DataFrame
names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
dr =  [True, False, False, False, True, True, True]
cpc = [809, 731, 588, 18, 200, 70, 45]
dict = { 'country':names, 'drives_right':dr, 'cars_per_cap':cpc }
cars = pd.DataFrame(dict)
print(cars)

# Definition of row_labels
row_labels = ['US', 'AUS', 'JAP', 'IN', 'RU', 'MOR', 'EG']

# Specify row labels of cars
cars.index = row_labels


# Print cars again
print(cars)

<script.py> output:
       cars_per_cap        country drives_right
    0           809  United States         True
    1           731      Australia        False
    2           588          Japan        False
    3            18          India        False
    4           200         Russia         True
    5            70        Morocco         True
    6            45          Egypt         True
         cars_per_cap        country drives_right
    US            809  United States         True
    AUS           731      Australia        False
    JAP           588          Japan        False
    IN             18          India        False
    RU            200         Russia         True
    MOR            70        Morocco         True
    EG             45          Egypt         True

```



##CSV to DataFrame(1)
##CSV to DataFrame(2)
##Pandas,Part2
##Square Brackets(1)
##Square Brackets(2)
##loc and iloc(1)
##loc and iloc(2)
##loc and iloc(3)
