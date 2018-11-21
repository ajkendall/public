# Python
- [Comments & Print](#Comments-and-Print)
- [Executing Python](#Executing-Python)
- [Variables](#Variables)
- [Casting](#Casting)
- [If Statements](#If-Statements)
- [The While Loop](#The-While-Loop)
- [For Loops](#For-Loops)
- [Range](#Range)
- [Functions](#Functions)
- [Lambda Functions](#Lambda-Functions)
- [Recursion](#Recursion)
- [Arrays](#Arrays)
- [Classes / Objects](#Classes)
- [Iterators](#Iterators)
- [Modules](#Modules)
- [Dates](#Dates)
- [Json](#Json)
- [Other Functions](#Other-Functions)


## Comments and Print
```python
print("Hello World")
# will comment out anything following it
"""this is a multiline
docstring (comment)"""
```



## Executing Python
```python
# by executing a .py file
$ python myfile.py

# or by just writing some python
$ print("Hello World")
```




## Variables
```python
x = 1    # int
y = 2.8  # float
z = 1j   # complex
```



## Casting
```python
a = int(1)   # a will be 1
b = int(2.8) # b will be 2
c = int("3") # c will be 3
d = float("4.2") # d will be 4.2
e = str(2) #e will be '2'
```


## If Statements
- Don't forget indentation - otherwise you will get an error
- If you have only one statement to execute, you can put it on the same line as the if statement.
- You can also have multiple else statements on the same line

**Multi-line if statement**
```python
a = 200
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```
**Single Statement**
```python
print("A") if a > b else print("B")
```
**Multiple Else Statements**
```python
print("A") if a > b else print("=") if a == b else print("B")
```
**Using And**
```python
if a > b and c > a:
  print("Both conditions are True")
```
**Using Or**
```python
if a > b or a > c:
  print("At least one of the conditions are True")
```



## The While Loop
```python
i = 1
while i < 6:
  print(i)
  i += 1
```

**The Break Statement**
- With the break statement we can stop the loop even if the condition is true:

```python
i = 1
while i < 6:
  print(i) # returns 1, 2, 3
  if i == 3:
    break
  i += 1
```

**The Continue Statement**
- With the continue statement we can stop the current iteration, 
- and continue with the next:
```python
i = 0
while i < 6:
  i += 1 
  if i == 3:
    continue
  print(i) # returns 0, 1, 2, 4, 5, 6
```



## For Loops
```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  print(x)

for x in "banana":
  print(x) # loops through the letters in banana
```

**The Break Statement**
- breaking an statement at the item "banana"

```python
fruits = ["apple", "banana", "cherry"]

# with the print preceding the break returns "apple", "banana"
for x in fruits:
  print(x) 
  if x == "banana":
    break
  

# with print following the break returns "apple"
for x in fruits:
  if x == "banana":
    break
  print(x) 
```

**Continue a Statement**
- With the continue statement we can stop the current iteration of the loop, and continue with the next:

```python
fruits = ["apple", "banana", "cherry"]
for x in fruits:
  if x == "banana":
    continue
  print(x) # returns "apple", "cherry"
```



## Range
```range(start?, length, increment?)```
- To loop through a set of code a specified number of times, we can use the range() function
- returns a sequence of numbers, starting from 0 by default, and increments by 1 (by default), and ends at a specified number.
```python
# returns 0, 1, 2, 3, 4, 5
for x in range(6): # means values from 0 to 6 excluding 6
  print(x)

# using a start parameter
# returns 2, 3, 4, 5
for x in range(2, 6): # means values from 2 to 6 excluding 6
  print(x)

# using an increment of 3
# returns 2, 5, 8, 11, 14, 17, 20, 23, 26, 29
for x in range(2, 30, 3):
  print(x)

# execute something once finished using "else"
for x in range(6):
  print(x)
else:
  print("Finally finished!")
```



## Functions
```python
def my_function(country = "Norway"):
  print("I am from " + country)

my_function("Sweden")

def my_function(x):
  return 5 * x
```



## Lambda Functions
- a small anonymous function
- can take any number of arguments
- can only have one expression

**Single Argument**: a > returns a + 10 = 15
```python
x = lambda a: a + 10
print(x(5)) 
```

**Multiple Arguments**: a, b, c > return a + b + c = 13
```python
x = lambda a, b, c : a + b + c
print(x(5, 6, 2))
```

**Lambda Use Cases**
- The power of lambda is better shown when you use them as an anonymous function inside another function.
```python
def myfunc(n):
  return lambda a : a * n

doubler = myfunc(2)
tripler = myfunc(3)

print(doubler(11)) # returns 22
print(tripler(11)) # returns 33
```



## Recursion
- We use the k variable as the data, which decrements (-1) every time we recurse. The recursion ends when the condition is not greater than 0 (i.e. when it is 0).
```python
# returns 1, 3, 6, 10, 15, 21
def tri_recursion(k):
  if(k>0):
    result = k+tri_recursion(k-1)
    print(result)
  else:
    result = 0
  return result

print("\n\nRecursion Example Results")
tri_recursion(6)

# tri_recursion(0) = []
# tri_recursion(1) = [1]    
# tri_recursion(2) = [1, 3]  
# tri_recursion(3) = [1, 3, 6] 
# tri_recursion(4) = [1, 3, 6, 10]
# tri_recursion(5) = [1, 3, 6, 10, 15] 
# tri_recursion(6) = [1, 3, 6, 10, 15, 21] 
  # 1st run: k = 1, result = 1 + 0  = 1
  # 2nd run: k = 2, result = 2 + 1  = 3
  # 3rd run: k = 3, result = 3 + 3  = 6
  # 4th run: k = 4, result = 4 + 6  = 10
  # 5th run: k = 5, result = 5 + 10 = 15
  # 6th run: k = 6, result = 6 + 15 = 21
```



## Arrays
Note: Python does not have built-in support for Arrays, but Python Lists can be used instead.
- To add an item to end of array: ```array.append(newItem)```
- To add another array to the end of the current array: ```array.extend(otherArray)```
- To add an element at a specified position: ```array.insert()```
- To remove an item by its index: ```array.pop(itemIndex) ```
- To remove an item by its value: ```array.remove("Volvo")```
- To remove all items from an array: ```array.clear()```
- To return a copy of a list: ```array.copy()```
- To return the number of elements with the specified value: ```array.count()```
- To return the index of the first element with the specified value: ```array.index()```
- To reverse the order of the list: ```array.reverse()```
- To sorts the list: ```array.sort()```
  



## Classes
- first parameter of init must reference the class itself ("self") - can be named anything you like though
```python
class Person:
  def __init__(self, name, age):
    self.name = name
    self.age = age
  def myfunc(self):
    print("Hello my name is " + self.name)

p1 = Person("John", 36)

print(p1.name)
print(p1.age)
p1.myfunc()
```



## Iterators
- an object that contains a countable number of values.
- an object that can be iterated upon, meaning that you can traverse through all the values.
- an object which implements the iterator protocol, which consist of the methods __iter__() and next().

```python
class MyNumbers:
  def __iter__(self):
    self.a = 1
    return self

  def next(self):
    if self.a <= 3:
      x = self.a
      self.a += 1
      return x
    else:
      raise StopIteration

myclass = MyNumbers()
myiter = iter(myclass)

print(next(myiter)) # returns 1
print(next(myiter)) # returns 2
print(next(myiter)) # returns 3
print(next(myiter)) # returns error: 
# Traceback (most recent call last):
  # File "python.py", line 20, in <module>
    # print(next(myiter))
    # StopIteration
```




### Iterator vs Iterable
- Lists, tuples, dictionaries, and sets are all iterable objects. 
- They are iterable containers which you can get an iterator from.
- All these objects have a iter() method which is used to get an iterator

```python
mytuple = ("apple", "banana", "cherry")
myit = iter(mytuple)

print(next(myit)) # returns "apple"
print(next(myit)) # returns "banana"
print(next(myit)) # returns "cherry"
```

Can also be used on strings
```python
mystr = "banana"
myit = iter(mystr)

print(next(myit)) # returns "b"
print(next(myit)) # returns "a"
print(next(myit)) # returns "n"
print(next(myit)) # returns "a"
print(next(myit)) # returns "n"
print(next(myit)) # returns "a"
```





## Modules

You can save a file as mymodule.py and import it by:
```py
import mymodule

mymodule.greeting("Jonathan")
```

To name a module:
```python
import mymodule as mx

a = mx.person1["age"]
print(a)
```

To import only parts of a module:

```python
from mymodule import person1

print (person1["age"])
```



## Dates
To use dates: import the built-in python module _datetime_
```python
import datetime

x = datetime.datetime.now()
print(x) # returns 2018-11-16 15:06:06.946030
```

**Date Functions**
```python
import datetime

x = datetime.datetime.now()

print(x.year) # returns 2018
print(x.strftime("%A")) # returns "Friday"

# Creating Date Object
y = datetime.datetime(2020, 6, 17)
print(y.strftime("%B")) # returns "June"
```

**Date Parameters**

| Directive |	Description |	Example |
|:--------:|--------------|---------|
| ```%a``` |	Weekday, short version	| Wed |
| ```%A``` |	Weekday, full version	| Wednesday |
| ```%w``` |	Weekday as a number 0-6, 0 is Sunday | 3 |
| ```%d``` |	Day of month 01-31 | 31 |
| ```%b``` |	Month name, short version | Dec	|
| ```%B``` |	Month name, full version | December |
| ```%m``` |	Month as a number 01-12 |	12 |
| ```%y``` |	Year, short version, without century | 18 |
| ```%Y``` |	Year, full version | 2018 |
| ```%H``` |	Hour 00-23 | 17 |
| ```%I``` |	Hour 00-12 | 05 |
| ```%p``` |	AM/PM	| PM |
| ```%M``` |	Minute 00-59 | 41 |	
| ```%S``` |	Second 00-59 | 08 |	
| ```%f``` |	Microsecond 000000-999999 | 548513 |	
| ```%z``` |	UTC offset | +0100 |	
| ```%Z``` |	Timezone | CST |
| ```%j``` |	Day number of year 001-366 | 365 |
| ```%U``` |	Week number of year, Sunday as the first day of week, 00-53 | 52 |	
| ```%W``` |	Week number of year, Monday as the first day of week, 00-53 | 52 |	
| ```%c``` |	Local version of date and time | Mon Dec 31 17:41:00 2018 |
| ```%x``` |	Local version of date | 12/31/18 |
| ```%X``` |	Local version of time | 17:41:00 |
| ```%%``` |	A % character | % |





## Json
To work with JSON data, import the built-in json module

**Parsing Json**
```python
import json

# some JSON:
x =  '{ "name":"John", "age":30, "city":"New York"}'

# parse x:
y = json.loads(x)

# the result is a Python dictionary:
print(y["age"]) # returns 30
```

**Converting Python to Json: json.dumps(object)**
```python
# a Python object (dict):
x = {
  "name": "John",
  "age": 30,
  "city": "New York"
}

# convert into JSON:
y = json.dumps(x)

# the result is a JSON string: '{"name": "John", "age": 30, "city": "New York"}'
print(y)
```
**Formatting Results**
- you can indent using: 
```python
json.dumps(object, indent = 4)
```
- you can change seperators 
  - the default value is: ```(", ", ": ")```
  - for example: change all commas to periods, and change all colons to equal sign
```python
json.dumps(object, indent = 4, separators=(". ", " = ")) 
```
- you can sort the result using the *sort_keys* parameter
```python
json.dumps(x, indent=4, sort_keys=True)
```





## Other Functions
- Length of an Array: ```len(array)```










