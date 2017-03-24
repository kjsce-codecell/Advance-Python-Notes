## Object Oriented Programming Methodology

### Class

A class is a user-defined data type. Its a collection of
objects, where objects can represent just about anything
from integers to real world objects like a ball. Structure of Classes
in python are very similar to that of c++ or java. 

For example: 

```python
class world:
    def hello(self):
        print("Hello World!")

obj=world()
obj.hello()
```

Output:
```
Hello World!
```
As we can see above, we create a class using the keyword class and the name of the class.
This is followed by an indented block of statements which forms the body of the class.
The body can contain methods and variables pertaining to the class. In the above example 
we have created a class "world" which defines a method "hello" to print the 
statement "Hello World!".
We create an object of this class, which can access the data members and methods of the class
and call the methods of the class by using the "." operator just like in c++.

#### Note: 
```
1. The class methods in python need to have an extra parameter called self. This does not
have a value, when a method is called.
2. If we have a method with no parameters, in the class we must have one argument that is 
the self argument. See hello() method in the above example.
3. This is similar to this pointer in c++ or this reference in Java.
4. When we call a method MyClass.method(arg1,arg2) this is automatically converted
by python into MyClass.method(object,arg1,arg2) where object is the self parameter.
```

### The __init__ method

The __init__ method in python is similar to constructors in java or c++.
That means it is run as soon as an object of the class is instantiated.
This method is useful to initialize your objects in the class, before
proceed further method calls.

For example:
```python
class name:
    def __init__(self,str):
        self.str=str

    def greet(self):
        print('Hi, my name is ',self.str)

p=name('Vinitra')
p.greet()
```
Output:
```
Hi, my name is Vinitra
```
### Inheritance

1. Introduction

Inheritance is one of the most powerful concepts of object oriented programming.
It is the mechanism of deriving features of one class from another class facilitating
code reusability.
It constitutes defining a new class which is similar or identical to a class that 
already exists. The new class is hence called derived class or child class and the one 
from which it is inherited is called the base class or the parent class.

For example:
```python
class side:
    def __init__(self,l,b):
        self.l=l
        self.b=b

class area(side):

    def __init__(self,l,b):
        side.__init__(self,l,b)

    def Area(self):
        print('Area of the rectange is ',self.l*self.b)

a=area(4,5)
a.Area()
```
Output:
```
Area of the rectangle is 20
```
2. Super()

```super()``` method is used to access data members and functions of parent class.
The example given in the example for inheritance can also be executed by the
```super()``` method.

For example:
```python
class side:
    def __init__(self,l,b):
        self.l=l
        self.b=b

class area(side):
    
    def __init__(self,l,b):
        super(area,self).__init__(l,b)

    def Area(self):
        print('Area of the rectange is ',self.l*self.b)

a=area(4,5)
a.Area()
```
Output:
```
Area of the rectangle is 20
```
### Operator Overloading

Python operators work for built-in classes. But the same operators can be made to behave
in a user-defined way. For example, the + operator adds the primitive variables of 
primitive data types. But by operator overloading you can make the + operator to 
add two complex numbers!
This feature that allows operators to have to different functions according to context
is called Operator Overloading.
See the example below to see how to overload operators.
Example:
```python
class Point:
    def __init__(self,x,y):
        self.x=x
        self.y=y

    def __str__(self):
        return "({0},{1})",format(self.x,self.y)

    def __add__(self,other):
        x=self.x+other.x
        y=self.y+other.y
        print()

p1=Point(2,4)
p2=Point(-1,5)
print(p1+p2)
```
Output:
```
(1,9)
```
What happens is that, when you write p1+p2, python will call p1.__add__(p2) which in
turn is Point.__add__(p1,p2). Also in the above example, __str__ is special function
like the __init__ method i.e it gets called whenever the class is instantiated.
This method is used to control the output format

### Special Functions

Special functions are those methods which get executed as soon as the class is
instantiated. For example: the __init__ method.
There are many useful special functions in python. Given below are some of them.

1. __iter__: This method returns the iterator object and is implicitly called
at the start of loops.    
2. __next__: This method returns the next value and is implicity called at 
each loop increment.

Example:
```python
class Counter:
def __init__(self, low, high):
    self.current = low
    self.high = high

def __iter__(self):
    return self

def __next__(self): # Python 2: def next(self)
    if self.current > self.high:
        raise StopIteration
    else:
        self.current += 1
        return self.current - 1

for c in Counter(3, 8):
print(c)
```
Output:
```
3
4
5
6
7
8
```

3. __str__ & __repr__: Both the functions are similar, i.e both are used to "represent"
an object in a string. __repr__ gives you an official representation while __str gives
informal  representation.
For example:
```python
x=1
print(repr(x))
print(str(x))
y='string'
print(repr(y))
print(str(y))
```
Output:
```
1
1
'string'
string
```
In the above example, the return of repr() and str() are identical for int x, but not for
string y. Therefore the default implementation of __repr__ for a str object can be called as
an argument to eval and the return value would be a valid str object.

4. dir(): This method takes only 1 object as a parameter and returns a list of 
attributes of the object.
For example:
```python
class num:
    def __init__(self):
        return [1,2,3]

n=num()
print(dir(n))
```
Output:
```
[1,2,3]
```


