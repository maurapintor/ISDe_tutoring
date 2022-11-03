# Industrial Software Development

## Tutoring sessions

<center>Tutor: Maura Pintor (maura.pintor@unica.it)</center>

---

## Organization

**Thursday h 15:00 - 18:00 Room AB** <br> **and Teams channel**

Topics:
1. Setup and Python basics
2. Python advanced
3. Design patterns (required for exam)
4. Projects in teams

---

## Organization

All lessons will be held in hybrid mode.
The first three topics will be also recorded and available on Teams.
The group activity will not be recorded (and in-presence mode is recommended!).

Ask questions!
Use the Teams channel, send me a PM on Teams (associated to this email: maura.pintor@unica.it), or directly send an email to [maura.pintor@unica.it](mailto:maura.pintor@unica.it)


---

# Today: Setup and Python basics

---

What to know about Python:

- it is an **interpreted language**
- indentation matters
- extremely flexible (not always a good thing)

---

## Setting up the interpreter

1. Install [Miniconda](https://docs.conda.io/en/latest/miniconda.html)
2. Create an interpreter ```bash conda create --name isde```
3. Activate the interpreter ```bash conda activate isde```
4. Use the interpreter
5. (optional) Deactivate the interpreter ```bash conda deactivate```

The last step is optional as it will be done automatically when the shell session terminates.

---

## Setting up the interpreter

If you have an IDE, check out the dedicated instructions for setting the interpreter in your project.
It will make life easier!

---

## Python variables and types

```python
# examples of types
number = 100  # integer
another_number = 10.6  # floating point
letter= "a"  # char

# gets the type of a variable
type(number)

str(number)  # type conversion

```

---

## Exercise

Print the results of the following expressions:

```python
a = 15 b = -20
c = a-b
c = not a
c = (a==b) or ((a+b)==-5)
```

---

## Exercise

Try to predict what will be the result of these expressions

```python
print ((4>6) and (3>8))
print ((4>6) or (3>8))
print (1 == 1 and 2 == 1)
print (False and 0 != 0)
print (not (True and False))
```

---

## Aggregations of variables

```python
l = [0, 1, 2]  # list
s = "some text"  # string

print(type(l))
print(type(s))

l = [[0, 1], [2, 3]]  # nesting
```

---

## Indexing lists and strings

```python
   l = [0, 1, 2]
```

```python
# take first element (or element at position X)
fist_element = l[0]  # numbering starts from zero!
first_letter = s[0]

# take last element (or element at position -X)
last_letter = s[-1]

```

---

## Indexing lists and strings
```python


# take portion of elements (from A to B -> B not included)
group_of_letters = s[1:5]  # elements from 1 to 4

# if one end is not specified, uses a default
first_letters = s[:2]  # default: start from 0
last_letters = s[2:]  # default: end with -1

# take one element each N
reverse_string = s[::2]  # one each 2

# take elements in reverse
reverse_string = s[::-1]

```

---

## Indexing lists and strings
```python
l = [[1, 2], [3, 4, 5]]

# access nested lists
sublist = l[0]
element_of_sublist = l[0][1]
```

---

## Edit elements

```python
l = ['a', 1, 2]
l[0] = 0  # changes first element to 0
```

REMEMBER: elements of strings cannot be edited!
```python
s = "text"
s[0] = "n"  # DOES NOT WORK
s = "next"  # re-defining the string works
```

---

## Operations with strings and lists

```python
l = [0, 1, 2]
l = l + [3, 4, 5]  # concatenates the lists
s = "abc" + "def"  # works also with strings

s = '!' * 30  # creates a string with 30 '!'

number_of_chars = len(s)  # length of the string
```

---

## Operations with strings only

```python
s = "abCdef"
lowercase = s.lower()
uppercase = s.upper()

# checks if sequence "de" is contained in the string
de_in_s = "de" in s  # case sensitive!

```

---

## Fancy strings

Since Python 3.6, strings can access directly python variables.

```python
number = 222
s = f"The lucky number is {number}"
print(s)
```

This converts the variable automatically into a string type and concatenates it inside of the string.

---

## Dictionaries

```python
d = {'age': 22, 'name': 'joe'}
age = d['age']  # takes element by key
keys = d.keys()  # all keys
values = d.values()  # all values
d['surname'] = 'doe'  # adds one key
d['name'] = 'john'  # edits element
```

Remember: each key is unique!

---

## Control structures

How to change the control flow of a program?

* ```if```
* ```if-else```
* ```if-elif-else```
* ```while```
* ```for```

Remember: Python uses intentation to define control flow structures

---

## Normal control flow 

```python
a = 2  # instr1
b = a + 3  # instr2
c = b/2  # instr3
```

~~~mermaid
flowchart LR;
    instr1-->instr2;
    instr2-->instr3;
~~~

---

## If-only control flow 

```python
a = 2  # instr1
if a >= 1:  # condition
    print("greater than or equal to 1")  # instrA
print(a)  # instr2
```

~~~mermaid
flowchart LR;
    instr1-->if{condition};
    if{condition}-->|True|instrA;
    if{condition}-->|False|instr2;
    instrA --> instr2;
~~~

---

ATTENTION: anything different than ```0``` or ```False``` is considered ```True```!

---

## If-else control flow 

```python
a = 2  # instr1
if a >= 1:  # condition
    print("greater than or equal to 1")  # instrA
else:
    print("smaller than 1")  # instrB
```

~~~mermaid
flowchart LR;
    instr1-->if{condition};
    if{condition}-->|True|instrA;
    if{condition}-->|False|instrB;
~~~

---

## If-elif-else control flow 

```python
a = 2  # instr1
if a >= 1:  # condition1
    print("greater than 1")  # instrA
elif a == 1:
    print("equal to 1")  # instrB
else:
    print("smaller than 1")  # instrC
```

~~~mermaid
flowchart LR;
    instr1-->if{condition1};
    if{condition1}-->|True|instrA;
    if{condition1}-->|False|if2{condition2};
    if2{condition2}-->|True|instrB;
    if2{condition2}-->|False|instrC;
~~~

---

## Loops

What if we have to repeat the same instruction multiple times?
We can use loops. They repeat the instruction until the stop condition is met.

---


## While loops

Used to repeat actions until condition is met. <br>
```CTRL + c``` if you get stuck in a while loop :D

```python
a = 0  # instr1
while a < 10:  # condition
    a += 1  # instrA
print(a)  #inst2

```

~~~mermaid
flowchart LR;
    instr1-->if{condition};
    if{condition}-->|True|instrA;
    instrA --> if;
    if{condition}-->|False|instr2;
~~~

---

## For loops

Used for index-based structures or variables or to repeat actions (exactly) N times.

```python
#get only items
for item in [0, 1, 2]:
    print(item)
```

```python
# get index and item
for index, item in enumerate([0, 1, 2]):
    print(index,item)
```

```python
# do action exactly N times
for i in range(10):
    print("string")
```

---

## For loops

Can be used to iterate through dictionaries.

```python
d = {'A': [0, 1, 2], 'B': [3, 4, 5]}

for key, value in d.items():
    print(key, value)

```

---

## Exercise

Print the sum of a list of integers. <br>
Implement it with a ```for``` loop and a ```while``` loop.

---

## Functions

Useful for dividing complex problems into more simple and solvable sub-problems.
They are blocks of code that solve a sub-problem, returning directly the result.

---

```python

students = {
    'A': [20, 23, 22, 19], 
    'B': [18, 22, 19, 28],
    'C': [30, 18, 22, 30]
    }

```

* Main problem: Take away one point for each score of each student.
* Sub-problem: Subtract one to all elements of a list (solved for each student).
* Sub-sub-problem: Subtract one to one element.

---

## Functions

* Input parameter(s): information required to find the result (```x```)
* Output(s): result of the function (```return x - 1```)

```python
def subtract_one(x):
    """Subtracts one point from the score x"""
    return x - 1

def subtract_one_list(x):
    """Returns a new list with the scores lowered by 1"""
    new_list = []  # empty list
    for item in x:
        lower_score = subtract_one(item)
        new_list.append(lower_score)  # appends element
    return new_list

def subtract_one_to_all(x):
    ...  # have fun :D
```

---

## Functions

Functions can take no input or return no output.

```python

def no_input():
    return 10

def no_return(x):
    print(x)

def no_input_and_return():
    print("I will return nothing.")

result = no_input_and_return()  # returns None

```

---

## Functions

Functions can take multiple parameters as input and return multiple results.

```python

# two input parameters
def concatenate_strings(s1, s2):
    return s1 + s2

# return two results
def sum_and_subtract_10(x):
    return 10+10, 10-10

```

---

## Scope

The variables inside the function are only accessible within the function. This is referred as **scope**.

```python

# two input parameters
def concatenate_strings(s1, s2):
    print(s1)  # works

a = "aa"
b = "bb"
concatenate_stings(a, b)
print(s1)  # gives error

```

---

## Exercise

Write four functions that perform the mathematical operations sum, product, division, subtraction. They have to take as input two numbers and return the result (don't call them the same as built-in functions!).

---

## Built-in functions

Python has many built-in functions. 

```python
x = [0, -1, 2, -10]
m = min(x)  # finds the minimum
l = len(x)  # finds length
```

RECOMMENDED: DO NOT CALL VARIABLES OR FUNCTIONS WITH BUILT-IN FUNCTION NAMES!!!

---

## Libraries

```python
import math
x = 0
s = math.sin(x)

import math.sin
s = math.sin(x)  # imports only the module 'sin'

from math import sin
s = sin(x)  # can be used without specifying the library name

import math as m
s = m.sin(x)  # uses an alias for the library
```

---

## Exercise

Write a snippet that computes the area of a circle, given the radius: 

```python
import math.pi

...
```

---

## Install libraries

External libraries can be installed through the python packet managers.
The most used ones are conda and pip. 

```bash
conda install pip
pip install numpy
```

---

# Advanced Python

---

## Python Classes / Objects

**Objects** are complex Python structures, with their properties and methods.
* property: variables stored in the object
* method: functions that are accessible from the object

**Classes** are object creators, they define the blueprint of the object.

---


## Python Classes / Objects

```python
class Student:  # class
    name = "John"
    age = 20

student = Student()  # object = instance of the class
name = student.name
```


---


## The ```__init__``` function

All classes have a function called ```__init__()```, which is always executed when the class is being initiated.

We can use the ```__init__()``` function to assign values to object properties, or other operations that are necessary to do when the object is being created.

---

## The ```__init__``` function

Within the class, we can refer to ```self``` to get (or assign) attributes and methods stored in the class.


---


## The ```__init__``` function

```python
class Student:  # class
    def __init__(self, name, age):  # self is passed as input
        self.name = name  # store attributes in self
        self.age = age

student = Student('John', 20)  # now we can pass values here
name = student.name
```

---

## The ```__init__``` function


Now we can define methods and access attributes stored in self.

```python
class Student:  # class
    def __init__(self, name, age):  # self is passed as input
        self.name = name  # store attributes in self
        self.age = age

    def print_info(self):
        # access the attributes of the object
        print(f"Student {self.name} is {self.age} years old.")

student = Student('John', 20)  # now we can pass values here
student.print_info()

```

---

## Inheritance

Inheritance allows us to define a class that inherits all the methods and properties from another class.

~~~mermaid
classDiagram
    class Person {
        +name
        +surname
        +walk(target)
        }
    class Student {
        +student_id
    }
    Person <|-- Student
~~~

---

## Inheritance

```python
class Person:
    def __init__(self, name, surname):
        self.name = name
        self.surname = surname
    
    def walk(self, target):
        print(f"{self.name} {self.surname} is walking to {target}")
```

---

## Inheritance

```python
class Student(Person):
    def __init__(self, name, surname, student_id):
        self.student_id = student_id
        super().__init__(name, surname)  # calls method from parent
    
    def print_info(self):
        print(f"Student: {self.name} {self.surname} ID: {self.student_id}")

st = Student("John", "Doe", "12345")

st.walk("the store")  # inherits parent method
st.print_info()
```

---

## Abstract objects and methods

We can define a class that is not supposed to be ever instantiated, but defines a blueprint for creating other classes.

The other classes cannot be instantiated if they don't implement *at least* this method.

---

```python
class Animal:
    def talk(self):
        # this method is not implemented yet
        pass
 
class Human(Animal):
    def talk(self):
        print("I can say words")
 
class Dog(Animal):
    def talk(self):
        print("I can bark")
```

---

## Abstract objects and methods

Sometimes you will find also the ```...``` instead of ```pass```.

```python
class Animal:
    def talk(self):
        # this method is not implemented yet
        ...
 ```



