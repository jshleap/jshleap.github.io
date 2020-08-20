

# Python Fundamentals: First Interactions with Python 

Welcome to the first module of Python Programming of the SHARCNET Summer School!! 
This lesson deals with the first interaction of Python starting at the built-in data-structures such as variables, lists, and dictionaries. We will build up the knowledge you need, even if is your first time doing serious programming.

### Learning Objectives
* Interact with the python interpreter.
* Understand what is a variable, how to set it up, and manipulate it.
* Use lists, tuples, and dictionaries in Python programs.
* Read and manipulate data in the interpreter and in files.
* Write loops and decision statements in Python.
* Understand and write pure python functions.

<center>
<img src="quiz.png"  width="820" height="700" align="center"/>
</center>

### What are the names of your instructors? (Answer on instructors cue)

<img src="yes.png" width="30" height="30" align="left"/> Ivan

<img src="no.png" width="30" height="30" align="left"/> Sergio

<img src="slow.png" width="40" height="40" align="left"/> Tyler

<img src="fast.png" width="40" height="40" align="left"/> Tyson


## Why Python? 

* Easy for humans to read
* Fast to code with it
* Reasonably efficient
* Growing community and community support


Python is a general purpose scripting language, and therefore you can do most tasks with it, from GUI development to HPC applications. Python is a high level programming language, which means that has strong abstraction from the computer code (a.k.a humans can easily read it). Python syntax is even more akin to regular English than other programming languages such as C or Java, allowing the programmer to focus more on functionality. This is also why is said to be extremely readable, and readability is encourage among the "Pythonistas". One particularly useful property of Python is that is fully cross platform, meaning that, done correctly, the same program can be run in Windows, Mac, or Linux operating systems.


## Getting Started with Python

There are many ways to interact with python:

* Python console: Just type `python` in the terminal
* Ipython and variations: Provides a rich toolkit to help you make the most of using Python interactively (used here). After install, just type `ipython` or check Jupyter
* Others

## Variables in Python
Let's imagine that you want to store some numbers. In Python:


```python
x = y = 10
x = 5
print(x)
print(y)

```

    5
    10


```python
x = 10
y = 5.5
print(y)
```

### Types of Variables
In Python you can query the type a variable belongs to using the `type` functions.

Native functions in python are invoked with the parenthesis sintax:


```python
string = '10'
print(string)
type(string)
```

    10





    str



```python
type(x)
```

Basic types in python include:
* Integers: The integer part of a number
* Floats or Floating-Point Numbers: Decimal numbers
* Complex Numbers: Numbers including imaginary ones
* Strings: A sequence of characters
* Logical or Boolean: Has only two states `True` or `False`

```python
i = 10 # Integers
print(type(i))
f = 5.5 # floats
print(type(f))
c = 3j # complex
print(type(c))
s = 'ABC' # String
print(type(s))
b = True # Boolean
print(type(b))
```

### Integers
As the name classifies this data type is reserved for integer numbers. As you possibly know, integers cannot not have decimal places, as this type of data is discrete. The distinction that Python (and most other programming languages) do between integers and decimals (called floats in python, see below) is that they occupy different amount of memory, and therefore they are different class of objects. However, you can do any mathematical operation using floats and integers.

### Floats
As you probably already know, float is a data type designated for numbers with decimal places. `1.5` is considered a float, but also `1.0`. Both integers and floats have to be designated **without quotation marks**, otherwise Python will interpret them as strings. To understand this better let's do another exercise.


<center>
<img src="quiz.png"  width="820" height="700" align="center"/>
</center>

### What is the value of `a` after: `a = b = 10`
<img src="yes.png" width="30" height="30" align="left"/> 0

<img src="no.png" width="30" height="30" align="left"/> 10

<img src="slow.png" width="40" height="40" align="left"/> error

<img src="fast.png" width="40" height="40" align="left"/> None

### Modifying the Type: Casting
Some transformations of variables are allowed:


```python
z = '15'
b = "z is number "
c = b + z
type(b)
print(c)
```

    z is number 15


```python
a = False
int(a)
```

So to transform variables to one another, they need to be of the same kind. A string with numbers can be transformed into floats or integers, but any other character can't.

Another example, let's transform the float in variable `y` into a string and an integer using the functions `str()` and `int()`:
```python
y1 = str(y) # Transform float into string
y2 = int(y) # Transform float into integer
```

To recap, using the `print` function and the `type` function we learned before, print the type and values of `y`, `y1` and `y2`:


```python
print('y is of type', type(y), 'with value', y)
print('y1 is of type', type(y1), 'with value', y1)
print('y2 is of type', type(y2), 'with value', y2)

```

### Operations with variables
Within type operations are allowed, but cross-type operations will depend:


```python
# string with string
a = 'a string '
b = 'another string'
a + b
```




    'a string another string'




```python
# string with number
c = 10
d = '5'
int(d) /c
```




    0.5



```python
a = 'Hello'
b = ' world'
print(a + b)
```

```python
x = 10
y = 'string'
print( y +x )
```

Likewise, operations (such as concatenation/addition, subtraction, etc) can only been done in same types. For example, mathematical operations can only been done between numeric types (complex, floats and integers), and not with strings.

To recap and a few points to note:
1. A float will be rounded down to the lowest integer when transformed to integer
2. An integer would be given a zero decimal when transformed to float
3. **Only** strings that contain numerical values can be transformed to either integer or float
4. _bonus_: `#` can be used in python to write comments in the code. I strongly recommend you thoroughly comment your code.
5. _bonus2_: When Python code fails, it output different kinds of error. We saw in points 8 and 9 that when the value is not correct we get a `ValueError`. Check the Python documentation for more errors!

<center>
<img src="quiz.png"  width="820" height="700" align="center"/>
</center>

### Which code will correctlly print: "hello 1234"
<img src="yes.png" width="30" height="30" align="left"/> print("hello " + 1234)

<img src="no.png" width="30" height="30" align="left"/> print("hello " + string(1234))

<img src="slow.png" width="30" height="40" align="left"/> print("hello " + str(1234))

## Containers and Basic Data Structures
Variables are fine - but what if we want to "bundle" some of those variables?

How can I store them? For this, python has 3 basic containers: lists, dictionaries, and tuples.

### Lists
A list is an ordered sequence of elements, and those elements are normally variables.

This data structure is mutable or changeable. Also you can iterate over it to retrieve your data or access one item at a time. 


```python
alist = [10, 5.5, 'ABC', [1,2,3], a]
print(alist)
```

    [10, 5.5, 'ABC', [1, 2, 3], 'a string ']


So, lists are represented as comma separated variables between square brackets (`[var1, var2, var3]`). The variables can be of any type, including other containers, and objects.

#### Indexing: Retrieving elements from the list
To _index_ the first element in the list we call the name of the list and the number of the element between square brackets


```python
print(alist)
alist[1:4]
```

    [10, 5.5, 'ABC', [1, 2, 3], 'a string ']





    [5.5, 'ABC', [1, 2, 3]]



To recap:
1. We can construct a list by typing variables or data between square brackets separated by comma:
```python
# create a lits
alist = ['a', 'b', 3]
```
2. You can retrieve the items in the list by indexing the list:
```python
# Retrieve the first element of the list
item1 = alist[0]
```
**NOTE: Python indexing starts at 0**

3. Now we can print the first element:
```python
print('The first item is', item1)
```

4. What if I want say the first two? we can use a special kind of indexing called slicing:
```python
print(alist[:2])
```
**Note that you could write 0 or blank and in both cases it will retrieve the slice. Also note that the last index is not included on the result.**
5. What if we want the last two? We can also have a slice if we use a negative number:
```python
print(alist[:-2])
```

#### Iterating over a list
Oftentimes you will find yourself with very long lists. In these cases indexing and slicing the list one at a time is not very efficient. 


```python
for index, item in enumerate(alist):
    line = "Item number " + str(index) + " is " + str(item) 
    print("Item number ", str(index),  " is ", str(item) )
print(alist)
```

    Item number  0  is  10
    Item number  1  is  5.5
    Item number  2  is  ABC
    Item number  3  is  [1, 2, 3]
    Item number  4  is  a string 
    [10, 5.5, 'ABC', [1, 2, 3], 'a string ']


```python
for item in alist:
    print(item)
```

Imagine you want to go over a list, and apply and print a modification to each item. If you do it one by one, it will take a lot of code an a lot of time. Let's say that you have a list of numbers and you want to know what is the result of each item after elevating each number to the power of two and then subtracting two:
1. Let's create a list of numbers from 0 to 20. Python have a very convenient function called `range` to do this:
```python
numbers = range(10)
```
However, the function `range` returns a special type of container also called so if we print this container we get:
```python
print(numbers)
```
2. Transform the range into a list. Luckily for you there is the function `list` which will give us the list of number in the range:
```python
numberlist = list(numbers)
print(numberlist)
```
3. Now that we have the list we can go over it with a for loop. Let's first enumerate all the items using the `enumerate()` function and print each enumeration:
```python
# Iterate over the list enumerating the items
for index, item in enumerate(numberlist):
    print('Item', index, 'is', item)
```

4. Now we can iterate over the list, compute the square of the number minus 2:
```python
# Iterate over the items and compute the squared minus 2
for index, item in enumerate(numberlist):
    print('(item%d^2) - 2 =' % (index), (item**2)-2)
```

Recap
we cover many new tricks!!:
* We can go over a list with a for loop
* Two new function: `range()` which creates a range of numbers, and `enumerate()` that enumerates every item in a container
* One subtle trick was displayed in step 4, did you see it? when we wanted to print the value of `index `inside of the string `(item%d^2) - 2 =`, we use a trick called string formatting, that allows you to include things in a string. You can use it to include strings by using `%s`, integers by using `%d`, and floats by using `%f`. The replacing variable have to be put outside of the string after a percentage sign (`%`). There are more advance usages and I will encourage you to check the Python documentation on string formatting, it is very useful!!

Now it is important to introduce mutability of containers. Containers such as _lists_ and _dictionaries_ are mutable, meaning that can be modified without re-writing them. _Tuples_ on the other hand, cannot be modified. We will see more of _dictionaries_ and _tuples_ in their corresponding sections. For now, let's understand mutable lists through an exercise.

#### Mutating lists
Suppose that you have a list of three colors `Red`, `Blue`, and `Green`. Let's imagine that you actually want the primary colors. In this case you have to replace `Green` by `Yellow`.


```python
colors = ['Red', 'Blue', 'Green']
colors[2] = 'Yellow'
print(colors)
```

    ['Red', 'Blue', 'Yellow']


```python
colorlist = ["Red", "Blue", "Green"]
for index, color in enumerate(colorlist):
    print('Color {} is in index {}'.format(color, index))
    # after python 3.5 you can use formatted strings!!!!
    print(f'Color {color} is in index {index}'.format(index, color))
colorlist[2] = 'Yellow'
print(colorlist)
colorlist[colorlist.index('red')]
```

Let's also imagine that you want to add `Purple` and `Grey` at the end of the list:


```python
colors = colors[:2]
colors 
```




    ['Red', 'Blue']



Now you get how to get items from a list through indexing. For completion sake, let's say we want to spell the last color in the list. Of course we can just write it down in a print statement if we know what it is, but in cases where you don't know you can do something like this:
```python
# Get the last element with negative indexing
last = colorlist[-1]
# convert the string Gray into a list of characters using the function list
chars = list(last)
# print the spelling of the last item in colorlist
print('The color %s is spelled:' % last)
for character in chars:
    print(character)
```
So far we have seen that:
1. Any element in a list can be mutated (replaced) by something else without redefining the rest of the elements
2. Lists have a method called `append` to append elements at the end of the list
3. The function `list()` can be used to turn string into a list of characters

I encourage you to check the python documentation on lists and other methods that are very useful such as `extend()`, `pop()`, `index()`, etc.

Lists are very useful data structures, however, it can become cumbersome when you don't know the exact index and you want to access a given value. Looping over a very big list can also be very slow, if you want just a given set of values. For this, we can use another very useful data structure called dictionaries.

### Dictionaries
A dictionary is basically a map between pairs of objects. It is also a mutable object, meaning that you can change its values at any time. Dictionaries work in a key-and-lock fashion, where with a particular key you point to a value:


```python
d = {'Sp1':[1023,5,68,654,654], 'Sp2':[500]}
d['Sp1']
```




    [1023, 5, 68, 654, 654]



```python
adict = {"Red":3, "Blue":4, "Green":5, "Yellow":6, "Purple":6, "Grey":4}
adict2 = dict(Red=3, Blue=4, Green=5)
alist
```

**NOTE: Dictionaries are not sorted**

To recap, different than lists, dictionaries are built either by having variables in between curly brackets (`{key1:var1, key2:var2, key3:var3}`), or by using the built in function `dict` (`dict(key1=var1, key2=var2, key3=var3`). As you can see, you need to provide a key and a value. You can access the value with that particular key. Dictionaries, like lists, also have useful methods that allow you to access the keys, the values, or both. This methods are called `keys()`, `values()`, `items()`. So if your dictionary is called `d`, and you want only the keys, you will call the method `d.keys()`. Likewise if you only want the values you can use `d.values()` to access them. If you want to get pairs, you can use `d.items()`. 

#### Creating and looping over dictionaries
Let's assume that you are creating a phone book and want to retrieve and modify its contents:


```python
phonebook = {('Bob','Andres'): 5146012356, 'Stacy': 9024896778, 'John': 9099788563}
# Retrieve Stacy's number, and modify it from 9024896778 to 9024896779
phonebook['Stacy'] = 9024896779
phonebook
```




    {('Bob', 'Andres'): 5146012356, 'Stacy': 9024896779, 'John': 9099788563}



```python
phonebook = {'Bob': 5146012356, 'Stacy': 9024896778, 'John': 9099788563}
# Retrieve Stacy's number, and modify it from 9024896778 to 9024896779
phonebook['Stacy'] = 9024896779
phonebook['Kelly'] = 9024396779
#print(phonebook['Kelly'])
for value in phonebook.keys():
    print(value)
```

For completion, let's imagine you would like to include other friend after the phone book is created without having to re-type all the entries. 

```python
# Add Kelly's number
phonebook['Kelly'] = 901526956
# Print Kelly's number
print("The added Kelly's number is", phonebook['Kelly'])
# Iterate over the key-value pair
for name, number in phonebook.items():
    print("%s's number is %d" % (name, number))
```
In this example we can see that:
1. We can access a dictionary's value with a key
2. Dictionaries have the attribute items, which returns the key-value pair
3. Dictionaries have the attribute keys which returns an iterable with the keys
4. Dictionaries can be modified by calling the key and assigning a new value
5. You can add a new key value pair by calling the dictionary with the new key pointing to a value
6. _Bonus_: Did you see that the last print have a string formatting with two variables? did you see that you can pass a tuple of arguments to that string formatting? We will get to tuples later, but keep an eye on it.

It is important to notice that dictionaries, unlike lists, do not keep any particular order in their keys.

### Tuples
Tuples are a container just like lists, but are immutable.

This means that once it is created you cannot modify its contents without re-writing the object. To define `tuples` you can enclose a set of variables between parenthesis (`()`)


```python
# Define red fruits
red = ('Apple', 'Strawberry')
# Define green fruits
green = ('Avocado', 'Watermelon')

# Print them
print(red, green)
```

    ('Apple', 'Strawberry') ('Avocado', 'Watermelon')


```python
# Define red fruits
red = ('Apple', 'Strawberry', 'Raspberry')
# Define green fruits
green = ('Pear', 'Avocado')
# Print them
print(red)
print(green)
```

Tuples are very useful when you need to guarantee that a given grouping will not be modified by the code. Tuples are also used in string formatting, and to pack and unpack variables (this is to advanced for this lesson, but you can go ahead and look it up!). Items stored in tuples can be accessed just like we did with lists, but unlike lists we cannot assign new content in the place of another.



```python
# print the second element in red
print(red[:2])
# Enumerate all fruits in red
for idx, fruit in enumerate(red):
    print('fruit number ', idx, ' is ', red[idx])
# Enumerate all fruits in green
for idx, fruit in enumerate(green):
    print('fruit number ', idx, ' is ', green[idx])
```

    ('Apple', 'Strawberry')
    fruit number  0  is  Apple
    fruit number  1  is  Strawberry
    fruit number  0  is  Avocado
    fruit number  1  is  Watermelon


We can access the items by index, just like lists. Let's access the second element on the red fruits (Strawberry), and then let just enumerate both tuples:
```python
# print the second element in red
print(red[1])
# Enumerate all fruits in red
print('Fruits in container red are:')
for index, fruit in enumerate(red):
 print('Fruit %d in red is %s' % (index, fruit))
# Enumerate all fruits in green
print('Fruits in container green are:')
for index, fruit in enumerate(green):
 print('Fruit %d in green is %s' % (index, fruit))
```

But tuples cannot be modified, but is it true? let's try to replace Apple with cherry:


```python
red2 = list(red)
print(type(red2))
red2[0] = 'Cherry'
print(red, red2)
red2 = tuple(red2)
print(red2, type(red2))
```

    <class 'list'>
    ('Apple', 'Strawberry') ['Cherry', 'Strawberry']
    ('Cherry', 'Strawberry') <class 'tuple'>


```python
aredlist = list(red)
aredlist[0] = 'Cherry'
red = tuple(aredlist)
red
```

### Booleans
A boolean expression (or logical expression) evaluates to one of two states true or false


```python
a = {}
if a:
    print(True)
else:
    print(False)
```

    False


```python
a=''
if a:
    print(a)
```    

Every object has a boolean value. The following elements are false:
* None
* False
* 0 (whatever type from integer, float to complex)
* Empty collections: “”, (), [], {}
* Objects from classes that have the special method __nonzero__
* Objects from classes that implements __len__ to return False or zero

#### Evaluating booleans: Conditional statements
The importance of booleans is that you can evaluate variables and execute conditional code:


```python
a = ['string 1', 'a line', 'string 2']
b = None
for item in a:
    if 'string' in item:
        print(item)
    elif item is None:
        print('Item is none')
    elif b is None:
        b = item
    else:
        print('This was empty')
print(b)
```

    string 1
    string 2
    a line


Several operations also evaluate logically: Comparison, membership, and identity.


```python
x = 3
y = 1
z = 3
y <= x <= z
```




    True



**Comparison operators**
The <, <=, >, >=, ==, != operators compare the values of 2 objects and returns True or False. Comparison depends on the type of the objects. See the Classes to see how to refedine the comparison operator of a type.
```python
10 == 10
10 <= 10
```

**Chaining comparison operators**
Comparison operators can be chained. Consider the following examples:
```python
>>> x = 2
>>> 1 < x < 3
True
>>> 10 < x < 20
False
>>> 3 > x <= 2
True
>>> 2 == x < 4
True
```
The comparison is performed between each pair of terms to be evaluated. For instance in the first example, 1<x is evaluated to True AND x<2 is evaluated. It is not as if 1<x is evaluated to True and then True<3 is evaluated to True !!! Each term is evaluated once.

**Evaluation of logical and comparison operators and membership operators**
The evaluation using the and and or operators follow these rules:

and and or evaluates expression from left to right.
with and, if all values are True, returns the last evaluated value. If any value is false, returns the first one.
or returns the first True value. If all are False, returns the last value

**Membership operators**
in evaluates to True if it finds a variable in a specified sequence and false otherwise.
not in evaluates to False if it finds a variable in a sequence, True otherwise.
```python
>>> 'good' in 'this is a great example'
False
>>> 'good' not in 'this is a great example'
True
```
**Identity operators**
is evaluates to True if the variables on either side of the operator point to the same object and False otherwise
is not evaluates to False if the variables on either side of the operator point to the same object and True otherwise
```python
>>> p = 'hello'
>>> ps = p
>>> ps is p
True
```

<center>
<img src="quiz.png"  width="820" height="700" align="center"/>
</center>

### What is printed in the following code snippet?


```python
a = 10
b = 'hello'
c = 'hello world'
if a > 20:
    print("YES")
else:
    if "cat" in c:
        print("NO")
    elif b in c:
        print("Go slower")
    else:
        print("Go faster")
```

    Go slower


### Converting Between Data Structures
You can convert a tuple to a list, a list to a tuple, and you can convert a list of tuples into a dictionary. You can also convert a dictionary to a list, but only the keys will be displayed.


```python
fruits = ('Apple', 'Banana', 'Pear')
fruits = dict(fruits)
fruits
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-150-d2b876c7f034> in <module>
          1 fruits = ('Apple', 'Banana', 'Pear')
    ----> 2 fruits = dict(fruits)
          3 fruits


    ValueError: dictionary update sequence element #0 has length 5; 2 is required


```python
fruits = ('Apple', 'Banana', 'Pear')
fruits = list(fruits)
fruits = tuple(fruits)
fruits
```


```python
subset = ('Apple', 'Strawberry')
colored_tuples = [('Apple', 'red'), ('Banana', 'yellow'), ('Pear', 'green')] 
colored_dict = dict(colored_tuples)

for fruit in subset:
    if fruit in colored_dict:
        print(colored_dict[fruit])
    else:
        print(f'{fruit} is not classified')


# Tuple in boolean
```

    red
    Strawberry is not classified


You can also create a list of tuples and transform it into a dictionary using the `dict()` function. Also, let's use the `list()` function to make a list of the keys in the newly created dictionary:
```python
# Create a list of tuple pairs and convert it to dictionary
fruitsncolor = [('Apple', 'Red'), ('Banana', 'Yellow'), ('Pear', 'Green')]
print(fruitsncolor)
# Convert the list of tuples into a dictionary and print it
d = dict(fruitsncolor)
print(d)
# Print the list of keys
print('Fruits in dictionary', list(d))
```
Here we just showed you that if you provide the key-value pair in a list, you can generate a dictionary with the `dict` function. I also showed you that you can go back and forth from tuples to lists with the functions `list` and `tuple`.

#### Recap
In this section we also saw that lists are represented with square brackets (`[]`), dictionaries with curly brackets (`{}`) and tuples with parenthesis (`()`). All these data structures (including strings) have very useful functions that we will not cover here, but I encourage you to explore before continuing. You can visit the [Python documentation](https://docs.python.org/3/tutorial/datastructures.html) for more information.

### Loops
When you have to repeat an action a number of times, you need to *loop* over the task. We inderectly have seen one kind of looping before called *_for loop_*


```python

```




    (0,
     1,
     2,
     3,
     4,
     5,
     6,
     7,
     8,
     9,
     10,
     11,
     12,
     13,
     14,
     15,
     16,
     17,
     18,
     19,
     20,
     21,
     22,
     23,
     24,
     25,
     26,
     27,
     28,
     29,
     30,
     31,
     32,
     33,
     34,
     35,
     36,
     37,
     38,
     39,
     40,
     41,
     42,
     43,
     44,
     45,
     46,
     47,
     48,
     49,
     50,
     51,
     52,
     53,
     54,
     55,
     56,
     57,
     58,
     59,
     60,
     61,
     62,
     63,
     64,
     65,
     66,
     67,
     68,
     69,
     70,
     71,
     72,
     73,
     74,
     75,
     76,
     77,
     78,
     79,
     80,
     81,
     82,
     83,
     84,
     85,
     86,
     87,
     88,
     89,
     90,
     91,
     92,
     93,
     94,
     95,
     96,
     97,
     98,
     99,
     100,
     101,
     102,
     103,
     104,
     105,
     106,
     107,
     108,
     109,
     110,
     111,
     112,
     113,
     114,
     115,
     116,
     117,
     118,
     119,
     120,
     121,
     122,
     123,
     124,
     125,
     126,
     127,
     128,
     129,
     130,
     131,
     132,
     133,
     134,
     135,
     136,
     137,
     138,
     139,
     140,
     141,
     142,
     143,
     144,
     145,
     146,
     147,
     148,
     149,
     150,
     151,
     152,
     153,
     154,
     155,
     156,
     157,
     158,
     159,
     160,
     161,
     162,
     163,
     164,
     165,
     166,
     167,
     168,
     169,
     170,
     171,
     172,
     173,
     174,
     175,
     176,
     177,
     178,
     179,
     180,
     181,
     182,
     183,
     184,
     185,
     186,
     187,
     188,
     189,
     190,
     191,
     192,
     193,
     194,
     195,
     196,
     197,
     198,
     199,
     200,
     201,
     202,
     203,
     204,
     205,
     206,
     207,
     208,
     209,
     210,
     211,
     212,
     213,
     214,
     215,
     216,
     217,
     218,
     219,
     220,
     221,
     222,
     223,
     224,
     225,
     226,
     227,
     228,
     229,
     230,
     231,
     232,
     233,
     234,
     235,
     236,
     237,
     238,
     239,
     240,
     241,
     242,
     243,
     244,
     245,
     246,
     247,
     248,
     249,
     250,
     251,
     252,
     253,
     254,
     255,
     256,
     257,
     258,
     259,
     260,
     261,
     262,
     263,
     264,
     265,
     266,
     267,
     268,
     269,
     270,
     271,
     272,
     273,
     274,
     275,
     276,
     277,
     278,
     279,
     280,
     281,
     282,
     283,
     284,
     285,
     286,
     287,
     288,
     289,
     290,
     291,
     292,
     293,
     294,
     295,
     296,
     297,
     298,
     299,
     300,
     301,
     302,
     303,
     304,
     305,
     306,
     307,
     308,
     309,
     310,
     311,
     312,
     313,
     314,
     315,
     316,
     317,
     318,
     319,
     320,
     321,
     322,
     323,
     324,
     325,
     326,
     327,
     328,
     329,
     330,
     331,
     332,
     333,
     334,
     335,
     336,
     337,
     338,
     339,
     340,
     341,
     342,
     343,
     344,
     345,
     346,
     347,
     348,
     349,
     350,
     351,
     352,
     353,
     354,
     355,
     356,
     357,
     358,
     359,
     360,
     361,
     362,
     363,
     364,
     365,
     366,
     367,
     368,
     369,
     370,
     371,
     372,
     373,
     374,
     375,
     376,
     377,
     378,
     379,
     380,
     381,
     382,
     383,
     384,
     385,
     386,
     387,
     388,
     389,
     390,
     391,
     392,
     393,
     394,
     395,
     396,
     397,
     398,
     399,
     400,
     401,
     402,
     403,
     404,
     405,
     406,
     407,
     408,
     409,
     410,
     411,
     412,
     413,
     414,
     415,
     416,
     417,
     418,
     419,
     420,
     421,
     422,
     423,
     424,
     425,
     426,
     427,
     428,
     429,
     430,
     431,
     432,
     433,
     434,
     435,
     436,
     437,
     438,
     439,
     440,
     441,
     442,
     443,
     444,
     445,
     446,
     447,
     448,
     449,
     450,
     451,
     452,
     453,
     454,
     455,
     456,
     457,
     458,
     459,
     460,
     461,
     462,
     463,
     464,
     465,
     466,
     467,
     468,
     469,
     470,
     471,
     472,
     473,
     474,
     475,
     476,
     477,
     478,
     479,
     480,
     481,
     482,
     483,
     484,
     485,
     486,
     487,
     488,
     489,
     490,
     491,
     492,
     493,
     494,
     495,
     496,
     497,
     498,
     499,
     500,
     501,
     502,
     503,
     504,
     505,
     506,
     507,
     508,
     509,
     510,
     511,
     512,
     513,
     514,
     515,
     516,
     517,
     518,
     519,
     520,
     521,
     522,
     523,
     524,
     525,
     526,
     527,
     528,
     529,
     530,
     531,
     532,
     533,
     534,
     535,
     536,
     537,
     538,
     539,
     540,
     541,
     542,
     543,
     544,
     545,
     546,
     547,
     548,
     549,
     550,
     551,
     552,
     553,
     554,
     555,
     556,
     557,
     558,
     559,
     560,
     561,
     562,
     563,
     564,
     565,
     566,
     567,
     568,
     569,
     570,
     571,
     572,
     573,
     574,
     575,
     576,
     577,
     578,
     579,
     580,
     581,
     582,
     583,
     584,
     585,
     586,
     587,
     588,
     589,
     590,
     591,
     592,
     593,
     594,
     595,
     596,
     597,
     598,
     599,
     600,
     601,
     602,
     603,
     604,
     605,
     606,
     607,
     608,
     609,
     610,
     611,
     612,
     613,
     614,
     615,
     616,
     617,
     618,
     619,
     620,
     621,
     622,
     623,
     624,
     625,
     626,
     627,
     628,
     629,
     630,
     631,
     632,
     633,
     634,
     635,
     636,
     637,
     638,
     639,
     640,
     641,
     642,
     643,
     644,
     645,
     646,
     647,
     648,
     649,
     650,
     651,
     652,
     653,
     654,
     655,
     656,
     657,
     658,
     659,
     660,
     661,
     662,
     663,
     664,
     665,
     666,
     667,
     668,
     669,
     670,
     671,
     672,
     673,
     674,
     675,
     676,
     677,
     678,
     679,
     680,
     681,
     682,
     683,
     684,
     685,
     686,
     687,
     688,
     689,
     690,
     691,
     692,
     693,
     694,
     695,
     696,
     697,
     698,
     699,
     700,
     701,
     702,
     703,
     704,
     705,
     706,
     707,
     708,
     709,
     710,
     711,
     712,
     713,
     714,
     715,
     716,
     717,
     718,
     719,
     720,
     721,
     722,
     723,
     724,
     725,
     726,
     727,
     728,
     729,
     730,
     731,
     732,
     733,
     734,
     735,
     736,
     737,
     738,
     739,
     740,
     741,
     742,
     743,
     744,
     745,
     746,
     747,
     748,
     749,
     750,
     751,
     752,
     753,
     754,
     755,
     756,
     757,
     758,
     759,
     760,
     761,
     762,
     763,
     764,
     765,
     766,
     767,
     768,
     769,
     770,
     771,
     772,
     773,
     774,
     775,
     776,
     777,
     778,
     779,
     780,
     781,
     782,
     783,
     784,
     785,
     786,
     787,
     788,
     789,
     790,
     791,
     792,
     793,
     794,
     795,
     796,
     797,
     798,
     799,
     800,
     801,
     802,
     803,
     804,
     805,
     806,
     807,
     808,
     809,
     810,
     811,
     812,
     813,
     814,
     815,
     816,
     817,
     818,
     819,
     820,
     821,
     822,
     823,
     824,
     825,
     826,
     827,
     828,
     829,
     830,
     831,
     832,
     833,
     834,
     835,
     836,
     837,
     838,
     839,
     840,
     841,
     842,
     843,
     844,
     845,
     846,
     847,
     848,
     849,
     850,
     851,
     852,
     853,
     854,
     855,
     856,
     857,
     858,
     859,
     860,
     861,
     862,
     863,
     864,
     865,
     866,
     867,
     868,
     869,
     870,
     871,
     872,
     873,
     874,
     875,
     876,
     877,
     878,
     879,
     880,
     881,
     882,
     883,
     884,
     885,
     886,
     887,
     888,
     889,
     890,
     891,
     892,
     893,
     894,
     895,
     896,
     897,
     898,
     899,
     900,
     901,
     902,
     903,
     904,
     905,
     906,
     907,
     908,
     909,
     910,
     911,
     912,
     913,
     914,
     915,
     916,
     917,
     918,
     919,
     920,
     921,
     922,
     923,
     924,
     925,
     926,
     927,
     928,
     929,
     930,
     931,
     932,
     933,
     934,
     935,
     936,
     937,
     938,
     939,
     940,
     941,
     942,
     943,
     944,
     945,
     946,
     947,
     948,
     949,
     950,
     951,
     952,
     953,
     954,
     955,
     956,
     957,
     958,
     959,
     960,
     961,
     962,
     963,
     964,
     965,
     966,
     967,
     968,
     969,
     970,
     971,
     972,
     973,
     974,
     975,
     976,
     977,
     978,
     979,
     980,
     981,
     982,
     983,
     984,
     985,
     986,
     987,
     988,
     989,
     990,
     991,
     992,
     993,
     994,
     995,
     996,
     997,
     998,
     999)



```python
n_simulations = 10
for simulation in range(n_simulations):
    print('Performing simulation', simulation)
```

What about if you do not have a set number of items you want to loop? what if you want to execute lines of code until some condition becomes False?
#### while loop


```python
current_number = 0
while True:
    print(f'Current number is {current_number}')
    current_number += 1
    if current_number >= 10:
        print('This is going to be the last iteration')
        break
    
    
```

    Current number is 0
    Current number is 1
    Current number is 2
    Current number is 3
    Current number is 4
    Current number is 5
    Current number is 6
    Current number is 7
    Current number is 8
    Current number is 9
    This is going to be the last iteration


```python
current_number = 0
while True:
    print("Current number is", current_number)
    current_number += 1
    if current_number > 10:
        print(f'This will be the last iteration at {current_number}')
        break
```

#### Flow control
<center>
<img src="https://automatetheboringstuff.com/images/000105.jpg" width="600" height="700" align="center"/>
</center>


```python
a = 'a string'
print(a + ' another string')
a
```

    a string another string





    'a string'



```python
look = 0
rain=True
while rain:
    print('It is raining, staying inside')
    if look > 10:
        break
    look +=1
print('It is not raining, going outside')
```

BEWARE of while true or while number, it will create infinite loops, unless you break it.

<center>
<img src="quiz.png"  width="820" height="700" align="center"/>
</center>

### What does the final_list look like after the following code snippet?


```python
some_list = []
for i in range(10):
    if i < 4:
        some_list.append(i*2)
final_list = []
for i, ele in enumerate(some_list):
    if i < 4:
        final_list.append(ele)
    
print(final_list)
```

    [0, 2, 4, 6]


<img src="yes.png" width="30" height="30" align="left"/> [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]

<img src="no.png" width="30" height="30" align="left"/>  [0, 2, 4, 6]

<img src="slow.png" width="40" height="40" align="left"/> []

<img src="fast.png" width="40" height="40" align="left"/> Error

### Functions
We have seen so far how to store data into variables and containers. We also have seen how to go over lots of data using loops, and how to control the flow of the code. But what if we want to use the same code multiple times?

<center>
<img src="python-function.png" width="400" height="300" align="center"/>
</center>


```python
RESUMING AT 3:25
```

    100 fahrenheit is 37.77777777777778 celsius
    37.77777777777778


```python
def fahr_to_celsius(temp):
    celsius = ((temp - 32) * (5/9))
    return celsius

temp = 100
t = fahr_to_celsius(temp)
print(t)
```

#### Scope and Lifetime of variables
Scope is where the variable is recognized and the lifetime of a variable is how long you can access it. We can have local and global scopes and lifetimes:


```python
bar = 100 # this is global
def my_func(x, y=10):
    """
    This is a function that shows scope
    x is a positional argument and y have a default value, and therefore is optional
    """
    bar = x + y # This will be local
    return bar
foo = my_func(5, y=bar)
print(foo)
print(bar)
```

    105
    105


```python
bar = 100 # this will be global
def my_func(x, y=10):
    """
    X is a positional argument with no default, while y
    is a keyword argument with default
    """
    bar = 50 # this will be local
    print(bar)
my_func(5, y=10)
print(bar)
```

So, if you define a variable within a function (Local variable), it will be only recognized within that function and will destroyed once you exit the function.

<center>
<img src="quiz.png"  width="820" height="700" align="center"/>
</center>

### Which inputs in the following function header have default values?
```python
def my_func(some, thing, goes=100, right=200, here=300)
```
<img src="yes.png" width="30" height="30" align="left"/> All

<img src="no.png" width="30" height="30" align="left"/> goes, right, here

<img src="slow.png" width="40" height="40" align="left"/> It's complicated...

<img src="fast.png" width="40" height="40" align="left"/> Why is Python like this...?


### Base problem
#### Scenario:
You have a list of 10 genes names, a second list with the number of copies of each gene in species *x*, and a new gene and copy count. You want to create a container that would allow you to access the number of gene copies by calling the gene name. You also received a third list matching the same gene names but with counts for species *y*.

#### Aim:
1. Create a container that would allow you to access the number of gene copies by calling the gene name by species name.

2. Filter for genes that have more than 100 counts on species x.


**HINT: You will be creating a dictionary of dictionaries**

#### Steps
1. Create a variable called `genes` containing the following gene names: `COI`, `Cytb`, `12S`, `18S`, `IgA`, `A1BG`, `ZZZ3`, `GDF6`, `CNN1`, `MKNK1`.


```python
genes = ['COI', 'Cytb', '12S', '18S', 'IgA', 'A1BG', 'ZZZ3', 'GDF6', 'CNN1', 'MKNK1']
```

```python 
genes = ['COI', 'Cytb', '12S', '18S', 'IgA', 'A1BG', 'ZZZ3', 'GDF6', 'CNN1', 'MKNK1']
```

2. Create a second list called `spx_counts` with the following counts (**NOTE: counts are made up**): `1000`, `1000`, `5000`, `500`, `54`, `35`, `564`, `6`, `45`, `68`.


```python
spx_counts = [1000, 1000, 5000, 500, 54, 35, 564, 6, 45, 68]
```

```python
spx_counts = [1000, 1000, 5000, 500, 54, 35, 564, 6, 45, 68]
```

3. Create a third list called `spy_counts` with the counts of gene copies for species _y_: `1050`, `1050`, `3452`, `315`, `45`, `45`, `345`, `5`, `78`, `15`.


```python
spy_counts = [1050, 1050, 3452, 315, 45, 45, 345, 5, 78, 15]
```

```python
spy_counts = [1050, 1050, 3452, 315, 45, 45, 345, 5, 78, 15]
```

4. Create a tuple with a new pair of gene name and its count for species _x_ called `new_entry`: `('ALPI', 789)`


```python
new_entry = ('ALPI', 789)
```

```python
new_entry = ('ALPI', 789)
```

5. The new entry has a mistake, it was not the `ALPI` gene but instead it was the `ALPG` name. Correct it.



```python
new_entry = list(new_entry)
new_entry[0] = 'ALPG'
new_entry = tuple(new_entry)
print(new_entry)
```

    ('ALPG', 789)


```python
new_entry = list(new_entry)
new_entry[0] = 'ALPG'
new_entry = tuple(new_entry)
```

6. Create a dictionary for each species


```python
print(genes, len(genes))
print(spx_counts, len(spx_counts))
print(spy_counts, len(spy_counts))
dx = dict((zip(genes, spx_counts)))
dy = dict((zip(genes, spy_counts)))
print(dx)
print(dy)
```

    ['COI', 'Cytb', '12S', '18S', 'IgA', 'A1BG', 'ZZZ3', 'GDF6', 'CNN1', 'MKNK1'] 10
    [1000, 1000, 5000, 500, 54, 35, 564, 6, 45, 68] 10
    [1050, 1050, 3452, 315, 45, 45, 345, 5, 78, 15] 10
    {'COI': 1000, 'Cytb': 1000, '12S': 5000, '18S': 500, 'IgA': 54, 'A1BG': 35, 'ZZZ3': 564, 'GDF6': 6, 'CNN1': 45, 'MKNK1': 68}
    {'COI': 1050, 'Cytb': 1050, '12S': 3452, '18S': 315, 'IgA': 45, 'A1BG': 45, 'ZZZ3': 345, 'GDF6': 5, 'CNN1': 78, 'MKNK1': 15}


```python
dx = {} # Empty dictionaries to start
dy = dict() # This is also a empty dictionary but with the constructor

for index, gene in enumerate(genes):
    # we could filter here ...
    dx[gene] = spx_counts[index]
    dy[genes[index]] = spy_counts[index]
```

7. Add the new entry of species _x_ in the appropriate dictionary


```python
dx[new_entry[0]] = new_entry[1]
dx
```




    {'COI': 1000,
     'Cytb': 1000,
     '12S': 5000,
     '18S': 500,
     'IgA': 54,
     'A1BG': 35,
     'ZZZ3': 564,
     'GDF6': 6,
     'CNN1': 45,
     'MKNK1': 68,
     'ALPG': 789}



```python
dx[new_entry[0]] = new_entry[1]
```

8. Create a dictionary where the keys are the species names and the values are the dictionaries with the counts



```python
big_dict = {'x': dx, 'y': dy}
big_dict
```




    {'x': {'COI': 1000,
      'Cytb': 1000,
      '12S': 5000,
      '18S': 500,
      'IgA': 54,
      'A1BG': 35,
      'ZZZ3': 564,
      'GDF6': 6,
      'CNN1': 45,
      'MKNK1': 68,
      'ALPG': 789},
     'y': {'COI': 1050,
      'Cytb': 1050,
      '12S': 3452,
      '18S': 315,
      'IgA': 45,
      'A1BG': 45,
      'ZZZ3': 345,
      'GDF6': 5,
      'CNN1': 78,
      'MKNK1': 15}}



```python
big_dict = dict(x=dx, y=dy)
big_dict
```

9. Print the counts in both species for the gene `CNN1`


```python
for sp_name, counts in big_dict.items():
    print(f'Species {sp_name} has {big_dict[sp_name]["CNN1"]} CNN1 copies')
```

    Species x has 45 CNN1 copies
    Species y has 78 CNN1 copies



```python
for sp, dictionary in big_dict.items():
    print('The count of CNN1 in species {} is {}'.format('CNN1', dictionary['CNN1']))
```

10. If you did not filter in step 6, let's try filtering the big dictionary:


```python
filtered = dict(x={},y={})
for sp, counts_dict in big_dict.items():
    for gene, count in counts_dict.items():
        if count >= 100:
            filtered[sp].update({gene:count}) 

print('filtered', filtered)
print('Full', big_dict)
```

    filtered {'x': {'COI': 1000, 'Cytb': 1000, '12S': 5000, '18S': 500, 'ZZZ3': 564, 'ALPG': 789}, 'y': {'COI': 1050, 'Cytb': 1050, '12S': 3452, '18S': 315, 'ZZZ3': 345}}
    Full {'x': {'COI': 1000, 'Cytb': 1000, '12S': 5000, '18S': 500, 'IgA': 54, 'A1BG': 35, 'ZZZ3': 564, 'GDF6': 6, 'CNN1': 45, 'MKNK1': 68, 'ALPG': 789}, 'y': {'COI': 1050, 'Cytb': 1050, '12S': 3452, '18S': 315, 'IgA': 45, 'A1BG': 45, 'ZZZ3': 345, 'GDF6': 5, 'CNN1': 78, 'MKNK1': 15}}


```python
filtered = dict(x={}, y=dy)
for gene, count in big_dict['x'].items():
    if count >= 100:
        filtered['x'].update({gene:count})
#         filtered['x'][gene] = count
print('filtered', filtered)
print('Full', big_dict)
# ...
```

# Extended problem
<center>
<img src="https://files.realpython.com/media/building_with_python_watermark.2ebe5beb5b1e.jpg"  width="820" height="700" align="center"/>
</center>


Now, based on the big dictionary we have created, print only genes that start with a `C` **AND** that have more than 500 counts in species x and more than 500 counts on species y.

If you have fallen behind, or need to start fresh, the moodle page will explain how to begin the extended problem.