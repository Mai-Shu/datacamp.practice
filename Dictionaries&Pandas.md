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
##Dictionariception
##Pandas,Part1
##Dictionary to DataFrame(1)
##Dictionary to DataFrame(2)
##CSV to DataFrame(1)
##CSV to DataFrame(2)
##Pandas,Part2
##Square Brackets(1)
##Square Brackets(2)
##loc and iloc(1)
##loc and iloc(2)
##loc and iloc(3)
