# Python

## Introduction
* Python is a high-level, interpreted programming language.
* Interpreted language has an interpreter processing the scripts at runtimes line by line, no compiling needed before execution. Cpython is the official interpreter.
* Python 3 is the current version.
* IDLE is the integrated development environment for Python. It is available for all platform. Python code can be executed in IDLE line by line using Python Shell(immediate mode) or written and run in source code files.
* Source files have an extension of .py. The code is executed all at once, from top to bottom. Interpreted language doesn’t have machine code file which is created by the compiler.
* It is a case sensitive language.


## Basic Syntax
It is generally consisted of comments, statements, methods, functions and modules.

### Comments

* Single line comment is followed by ``#``, everything after # in one line will be ignored.
```python
# Single line comment goes here.
```

* Three sets of double quotation marks is called doctrings. Doctrings contains multi-lines comments and explains the following code after the first line. It is retained through runtime.
```python
"""
Summary or Description of the Function
Parameters:
argument1 (int): Description of arg1
Returns:
int:Returning value
"""
```

### Statements
* It is recognized by one keyword in the entire line, or sometimes followed by a variables after a singe space.

```python
del x
break
```

### Methods
* It is used to access and manipulate objects.
* It is recognized by a dot and a method name immediately after a variable name.

```py
x.count(y)
x.upper()
```

### Functions
* There are many built-in functions or it can be defined in codes.
* It is recognized by brackets after function names.


>#### Basic Useful Functions
```py
print(x)              #It prints variable x with a new line, x can be any data type.
print(x, y)           #It prints any two data types with a space in between.
input("Prompt: ")     #It prompts, get and returns user input as a string. The string that input() returns is automatically escaped.
```

### Modules
* Modules provide additional methods or functions for the programming. They are imported at the very beginning.
* It is recognized by the keyword import.

```py
import math
```



## Variables
They are customized name for storing data.

### Naming Conventions
* Variable name is usually oneTwoThree or one_two_three
* Variable name can use only letter number and underscore
* Variable name can not begin with number
* Variable name can not use reserved words in python
* Variable name abbreviation often needs comments as explanation.

### Variable Scope
* Variables introduced inside functions are local(only available) to that function.


## Basic Data Types

#### Boolean:
* True
* False

#### Integer:
* Whole number

#### Float:
* It can be any number with a decimal point. It is produced after any division or implicitly transfer after an operation between float and integer.
* Computer has limited memory space for floats. Also, any zero at the end will be ignored.

>#### Useful Math Functions
```py
round(value, toHowManyDigitAfterDecimal) #Rounding to specific decimal place
abs(value) #Get the absolute value of a number.
```

#### Character:
* It can be any single character.

>#### Character Conversion
```py
ord(character)  #Transforming a character to its ASCII code number. Character can be Unicode like u’\u1234’
chr(number)   # transform ASCII (a number from 0 to 255) to character.
unichr(number)   # transform UCS2 (a number from 0 to 65535) to character.
```


#### String:
* String is like list type for character, but can not change(immutable).
* \ is used to escape special characters, the characters are then called escape characters. E.g. ``"abc\"def\\g"``, Output: ``abc"def\g``
* ``\n`` represents a newline.
* ``\t`` represents a new tab.

##### String operators
* Concatenation uses ``+``.
* Integer repetition uses ``*``.



##### Membership Operator
It returns membership relationship between two objects as boolean.
```py
a in b                         
a not in b                     
not a in b                    
```

##### Relational operators
It can be used on strings for lexicographical(alphabetical order) comparison.

##### String Methods
```py
stringX[n]  #Get the character of stringX at nth index.

stringX[m:n]  #Get the character of stringX at index from m to n-1, max or min if m or n is missing.   
"""
There could be a third parameter that represents the step.
-1 means backward from its left or right end.
"""
str.upper()
str.lower()
str.isalpha()         #Return boolean
str.isdecimal()
str.islower()
str.isspace()
str.isupper()
str.find(substring) #Find the lowest index of the substring.
str.strip(string)   #Strip all the characters in the argument of the str from the beginning and the end.
```
##### String Function
```py
len(string)    #Return the number of characters of this string.
```
### Type Casting
Explicitly convert types.
```py
str(x)    #To  string
int(x)    #To  integer  
float(x) #To   float
list(x)   #To   list
```

### String Formatting
"formatedStringUsing{}".format(x,y,z)  
* String is formatted in a set of double quotation marks.
* The location, order, and content of data is indicated by {}.
* The argument of .format is the value of data in the {}.

```py
"{x},{y}".format(x=5,y=12)         
#Output:5,12
"{} {}".format(100,50)                
#Output:100 50
"{1}abc{0}".format(100,50)         
#Output:50abc100
"{:04d}".format(1)                      
#Output:0001
"{:06.2f}".format(1.2)                 
#Output:001.20     #decimal point counts
"{:_<10}".format("left")               
#Output:left______
"{:>10}".format("right")               
#Output:     right

"""
Other Methods
"""
",".join(["a","b","c"])    		           
#Output:’a,b,c’
"Hello ME".replace("ME","world")          
#Output:’Hello world’
"This is a sentence".startswith("This")   
#Output:True
"Hello World!".endswith("world!")         
#Output:False        
"x,y,z".split(",")                                   
#Output:[‘x’,’y’,’z’]
```

## Operators
Operators are special symbols that placed in between objects.

### Operators and Precedence
When operator are chained together, The operation order is determined from top to bottom in the following order.

* String Operators:
  * Slicing ``x[n]``
  * concatenation ``+``

* Arithmetic Operators:
  * exponent ``**``
  * Bitwise not ``~``
  * negation ``-``
  * multiply ``*``
  * divide ``/``
  * integer division ``//``
  * remainder ``%``
  * string repetition ``*``
  * addition ``+``
  * subtraction ``-``
  * Bitwise and ``&``
  * Bitwise xor ``^``
  * Bitwise or ``|``


* Relational Operators
  * greater ``>``
  * greater or equal ``>=``
  * great ``<``
  * smaller or equal ``<=``
  * equal ``==``
  * not equal ``!=``
  * string membership ``in``   

* Binary Boolean Operators
  * ``not``
  * ``and``
  * ``or``

* Assignment
  * It is used to assign value to a variable name. ``=``


### Bitwise operators
It is performed bit by bit.

* and ``&``
* or ``|``
* not ``~``
* XOR,  it is an "or" operations that doesn’t include "and", ``^``

```py
a=1101101
~a=0010010
```

>##### Hint:
* ``del x``, this statement remove one reference count from the name to the value in memory.
* ``a+=b`` is treated as  ``a=a+b``
* ``a**b**c`` is same as ``a**(b**c)``. This is called right associative.

## Basic Structures

#### If Condition

The execution of a certain code block is determined by conditions. Conditions are a boolean expression. When the condition is true the codes after will be executed.

```py
if condition:   
	#…
elif condition:
	#…
else:
	#…
```

#### All and Any
It can be used to test the condition among multiple values in an object.

```py
x = [1,2,3,4,5]
if all([i<6 for i in x]):
	print("all smaller than 6")
if any([i==5 for i in x]):
	print("At least one 5 in the array")
```

#### While Condition
This block of code is executed when the condition is true.

```py
while condition:
	#….
```

#### For Loop
Every elements of an object is assigned to the variable x.
```py
for x in objects:
	print(x)

for x in enumerate([1,3,5,7]):
	print(x)
"""
Output:
(0,1)
(1,3)
(2,5)
(3,7)
"""
# Enumerate(x) casts other types into enumerate.
```
>**Notes:**
* Flag is a condition for the loops which can be tested and modified in the loop.
* Sentinel value is a value in the loop condition, it is used to determine the exit of a loop.
* break statement in the loop can stop looping immediately.
* continue statement restart the loop from the top.

## List
* It is a mutable object. Its content can be changed. This index starts at 0.
```py
list=[‘a’,’b’,’c’,’d’]
print(list[0])
#Output:’a’
```
* 2-D List
```py
list=[[1,2],[3,4],[5,6]]
print(list[1][0])
#Output:3
```

#### List Methods
```py
list.append(value)#This will append a value at its end.
list.sort()#This will sort the object
list.remove(value)#It will remove certain value in the list regardless of its location.
list.reverse()  #It will reverse the order, print(list.sort()) will not work
list.insert(index, element)#It will insert an element at certain index location.
list.count(object)#It returns how many times an item occurs in the list
list.index(object)#It returns the first index of the item, ValueError if not find.
```

#### List Operators
* join ``+``
* repeat ``*``
* existence(return Boolean) ``in``
* slicing(from index n to m-1) ``n:m``

#### List Function
```py
len(list)
min(list)
max(list)
sum(list)
```

#### List Comprehension
It is the shortcut for creating lists.
```py
squareList = [i**2 for i in range(5)]
evenSquareList = [i**2 for i in range(10) if i**2%2 ==0]
```

## Dictionary
It is mutable.

```py
x = {key1:value1, key2:value2, key3:value3, …}
print(x[key1])
x[key1] = newValue
```

#### Operators
* Membership Operator - in
```py
keyName in dictionaryName      
keyName not in dictionaryName
```

#### Methods
```py
dictionary.get(key, notification)  #It returns the key’s value and None if key is not found. or display specific notification.
```

## Tuples
* It is an immutable list with or without parentheses(use comma for separation).
* It is faster than list, because it can not be changed or there will be a typeError.

```py
#Creates an empty tuples.
x = ()
#tuples declaration 1
x = (8,’a’,"sdfs",(2,4))
#tuples declaration 2
x = 8,’a’,"sdfs",(2,4)
#access tuples
print(x[0])
#Output: 8
```

## Set

* It is an unordered list.
* It is surrounded by curly bracket{}.
* Empty set is set(). {} is reserved for dictionary.

#### Operators

* union ``|``
* intersection ``&``
* difference ``-``
* symmetric difference: items in either set, but not both. ``^``

#### Methods
```py
set.add(x)  #It adds new element
set.remove(x)  #It removes x from set
set.pop()  #It removes a random element from the list
```
#### Functions
```py
len(set) # get length
```

## Other Basic Objects

### Range Object
* A sequential list of numbers.
* Created by range function.
```py
range(2,5) #It represents number from 2 to 4.
list(range(5))=[0,1,2,3,4]
range(5,20,x) #It creates a range from 5 to 19 with certain interval x.
```

### None object
* It is a False when converted to boolean type.
* It is the default output for user defined function.
* It is used to represent the absence of a value.

### Map Object
```py
map(function,oldlist)
```
* It returns a map object that manipulate the old list(or other iterables) according to the function.
* The map object needs to be transferred  into a list(or other iterables).

### Filter Object
```py
filter(function,iterables)
```
* It returns a filter object that has elements removed according to the function as the first argument.

## Module

#### Ways of Importing Modules
```py
import module_name
from math import pi, sort
from math import *
from math import sqrt as square_root
```

#### Sources of Modules
1. Some of them are preinstalled in the standard Library

2. Third-party Python modules.
  They can be stored on the Python Package Index (PyPI).
  Command line: ``pip install library_name``

3. Your own module.
  Most modules are available on all platforms, but some of them are Windows or Unix specific. Some are using exe file.

### itertools modules

#### Import module
```py
from itertools import *
```

#### Methods
```py
count(x) #counts up from x
for i in count(3):
	print(i)
cycle(x) #infinitely iterates through an iterable (for instance a list or string).
repeat(x) #repeats an object, either infinitely or a specific number of times(x).
product(iterable1,iterable2) #return an object contains all possible combination product of these two iterables. (all possible iterable 1 , all possible iterable 2 )
permutation(iterable)   #return an object contains all possible comb for the single iterable.
```

#### Functions
```py
takewhile(predicateFunc, iterables) # return object with items that only satisfy the predicate function.
chain(x,y) #combine iterables
accumulate(iterables)  #return a object contains a list of sum up to its position.
list(accumulate(range(8)))
```


## Lambda
* It is used to create anonymous function with has no variable name.
* It can be assigned to a variable to become a normal function.
```py
print(lambda  x: 2*x*x(10))  ->  200
```

## User Defined Functions

```py
def functionName(variable):
	…..
	…..
functionName(variable)
```
* parameters are variables that a function accepts.
* arguments are specific values that are substituted into the parameters.
* the scope of a variable is the sections of codes where the variable is accessible.
* variables within a function, has an independent scope within the function.
* functions can be assigned to a variable names.
* The variable can be called.
* function can be argument of other function.

#### return statement
Once a value is returned from a function, it immediately stops being executed.



## Generator
```py
def count():
	i=5
	while i>0:
		yield i
		i-=1
for i in count():
	print(i)  -> 5 4 3 2 1
```

* It is a type of iterable, it doesn’t contain indices.
* It is a user defined function with loop that contain yield statement to iterate multiple output by using for loop.
* It can be infinite.

#### Convert to List
```py
def number(x):
	for i in range(x):
		if i%2 ==0:
			yield i
print(list(number(11)))
```
finite generator can be transfer to list using ``list()``.


## Decorators
It is a user defined function that take old function as argument, declare a new function. manipulate old function by putting it inside and then return the new defined function.

```py
def decor(func):
	def wrap():
		print("===================")
		func()
		print("==================")
	return wrap  
#Then, newly defined function could be decorated by adding @decorfunction before def statement.
@decor
def rawfunction():
	print("Hello world!")
```

## Recursion
* Function that repeatedly calls themselves is called recursion.
* The last step is called the base case, it’s an exit point of recursion.
* Multiple functions can get involved in on recursion.

```py
def factorial(x):
	if x == 1:
		return 1
	else:
		return x * factorial(x-1)
```

## Class
* the name should be Capital letters for each word like OneTwoThree.
* It is the blueprint for creating objects.
* Instance is an object which is being called.

#### Object methods
* They are functions defined within the class block.
* It must have self as its first parameter. When calling functions, self parameter can be ignored.

#### ``__init__`` method
* It is called to create object, using class name as a function
* It is used to set the initial environment of an object.
* It is also called the class constructor.
* ``__new__`` method is executed before ``__init__`` for special cases.


#### Instance’s attributes
They are placed in the ``__init__`` method
#### Class attributes
They are placed in the first line of the class block. and shared by all instance of the class.

```py
class Dog:
	legs = 4
	def __init__(self,name,color):
		self.name = name
		self.color = color
	def bark(self):
		print("Woof!")
fido = Dog("Fido","brown")
fido.bark() -> Woof!
fido.legs -> Dog.legs -> 4
```

## Superclass
* It is used to share common attributes among classes called subclasses.
* A class can inherit a class from the superclass by putting superclass name at the end of the class statement for the subclass.
* Attributes for subclass can override attributes for superclass if they have the same name.
* Superclass(subclass) can have superclass(subclass).
* super function super() refers to the parent class


```py
class Animal:
  def __init__(self, name, color):
    self.name = name
    self.color = color

class Cat(Animal):
  def purr(self):
    print("Purr...")

class Dog(Animal):
  def bark(self):
    print("Woof!")

fido = Dog("Fido", "brown")
print(fido.color)
fido.bark()
```

## Magic methods
* Magic methods has double underscores at two ends as dunders.
* It is a special method for operator overloading(defines ``+``,``*``,``\``, and``-``between objects) or others.

#### Operators

* ``__sub__`` for -
* ``__mul__`` for *
* ``__truediv__`` for /
* ``__floordiv__`` for //
* ``__mod__`` for %
* ``__pow__`` for **
* ``__and__`` for &
* ``__xor__`` for ^
* ``__or__`` for |

```py
class Vector2D:
  def __init__(self, x, y):
    self.x = x
    self.y = y
  def __add__(self, other):
    return Vector2D(self.x + other.x, self.y + other.y)

first = Vector2D(5, 7)
second = Vector2D(3, 9)
result = first + second
print(result.x)
print(result.y)
```
* It simply translate x+y into ``x.__add__(y)``
* If x hasn't implemented ``__add__``, and x and y are of different types, ``x.__radd__(y)`` is called.

#### Comparison
* ``__lt__`` for <
* ``__le__`` for <=
* ``__eq__`` for ==
* ``__ne__`` for !=
* ``__gt__`` for >
* ``__ge__`` for >=
* ``__ne__`` could be translate to ``__eq__`` if it has not been implemented.

```py
class SpecialString:
  def __init__(self, cont):
    self.cont = cont

  def __gt__(self, other):
    for index in range(len(other.cont)+1):
      result = other.cont[:index] + ">" + self.cont
      result += ">" + other.cont[index:]
      print(result)

spam = SpecialString("spam")
eggs = SpecialString("eggs")
spam > eggs
```

#### Container
* ``__len__`` for len()
* ``__repr__`` for print() with format
* ``__getitem__`` for indexing
* ``__setitem__`` for assigning to indexed values
* ``__delitem__`` for deleting indexed values
* ``__iter__`` for iteration over objects (e.g., in for loops)
* ``__contains__`` for in
* ``__call__`` for calling objects as functions
* ``__int__`` or  ``__str__`` for converting objects to built-in types.

```py
import random

class VagueList:
  def __init__(self, cont):
    self.cont = cont

  def __getitem__(self, index):
    return self.cont[index + random.randint(-1, 1)]

  def __len__(self):
    return random.randint(0, len(self.cont)*2)

vague_list = VagueList(["A", "B", "C", "D", "E"])
print(len(vague_list))
print(len(vague_list))
print(vague_list[2])
print(vague_list[2])
```
* ``__del__`` is used for del statement and it is called garbage collection(automatic deletion process).

## Class Methods
* They all have cls as the first parameter
* They return new object of the newly defined class.
* add ``@classmethod`` before def statement

```py
class Rectangle:
  def __init__(self, width, height):
    self.width = width
    self.height = height

  def calculate_area(self):
    return self.width * self.height

  @classmethod
  def new_square(cls, side_length):
    return cls(side_length, side_length)

square = Rectangle.new_square(5)
print(square.calculate_area())
```

## Static Methods
* It starts with ``@staticmethod``.
* They don’t take new arguments.
* They are identical.
* They don't have self parameter.

```py
class Pizza:
  def __init__(self, toppings):
    self.toppings = toppings

  @staticmethod
  def validate_topping(topping):
    if topping == "pineapple":
      raise ValueError("No pineapples!")
    else:
      return True

ingredients = ["cheese", "onions", "spam"]
if all(Pizza.validate_topping(i) for i in ingredients):
  pizza = Pizza(ingredients)
```

## Property
``@property`` is placed above the def statement to make the code below read-only

```py
class Pizza:
  def __init__(self, toppings):
    self.toppings = toppings

  @property
  def pineapple_allowed(self):
    return False

pizza = Pizza(["cheese", "tomato"])
print(pizza.pineapple_allowed)
pizza.pineapple_allowed = True
```

## Setter or Getter
* It set or get the property’s value.
* property name followed by . and setter or getter.

```py
class Pizza:
  def __init__(self, toppings):
    self.toppings = toppings
    self._pineapple_allowed = False

  @property
  def pineapple_allowed(self):
    return self._pineapple_allowed

  @pineapple_allowed.setter
  def pineapple_allowed(self, value):
    if value:
      password = input("Enter the password: ")
      if password == "Sw0rdf1sh!":
        self._pineapple_allowed = value
      else:
        raise ValueError("Alert! Intruder!")

pizza = Pizza(["cheese", "tomato"])
print(pizza.pineapple_allowed)
pizza.pineapple_allowed = True
print(pizza.pineapple_allowed)
```

## Error Handling
When an exception occurs, the program immediately stops.

#### Error Types
* ImportError: an import fails;
* IndexError: a list is indexed with an out-of-range number;
* NameError: an unknown variable is used;
* SyntaxError: the code can't be parsed properly;
* TypeError: a function is called on a value of an inappropriate type;
* ValueError: a function is called on a value of the correct type, but with an inappropriate value.
* KeyError: trying to index a key that isn’t part of the dictionary.
* MemoryError: trying to create a list in a very extensive range.
* AttributeError: Trying to access an attribute of an instance that isn't defined or call an undefined method.

#### Handling Error
```py
try: #try some code
except ZeroDivisionError: #run if there is a ZeroDivisionError
except (ValueError, TypeError): #or two different error#
except:#and all other errors#
finally: #it will run no matter what
```

#### Raise an Error
* Raise statement is used to raise an error
```py
raise ValueError("display some other details")
```
* It can be used in except block alone to reraise errors.
```py
except:
   print("An error occurred")
   raise
```

#### Assert
* Assert statement is used to assume a condition then raise an error accordingly.
```py
assert 1==2
# Result: AssertionError
```
* It can has an argument to display details
```py
temp = -10
assert (temp >= 0), "Colder than absolute zero!"
# Result: AssertionError: Colder than absolute zero!
```

## File

#### Open a File
```py
newfile = open("localfile.txt", r+)
```

#### File Mode
* r: read mode It is the default mode
* w: write mode that can create new files and will overwrite old content  
* b: binary mode for non-text files
* a: append mode for adding new content to the end of the file.    
* r+ read and write mode

#### File Method
```py
newfile.close()   # close file after done manipulation.
x = newfile.read()    # read all file
newfile,read(x)    # read x byte
newfile.read(y)    # read next y byte
newfile.read() #read rest all.
newfile.read(negativeValue) #read rest all.
newfile.readlines()    #return a list of lines
newfile.write(stringS)     #write content into the file and return the byte written.
```

#### Read File Line by Line
```py
for line in file:
	print(line)      #print one line at a time
```

# Apply Error Handling
```py
try:
	newfile = open("localfile.txt")
	print(newfile.read())
finally:
	f.close()
```
```py
with open("localfile.txt") as newfile:
	print(newfile.read())    #This create a temperate variable newfile within the block. It will also make sure the file closure.
```