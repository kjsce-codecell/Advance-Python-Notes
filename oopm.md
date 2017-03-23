## Object Oriented Programming Methodology

### Class

```
A class is a user-defined data type. Its a collection of
objects, where objects can represent just about anything
from integers to real world objects like a ball. Structure of Classes
in python are very similar to that of c++ or java. 
```
### For example: ###

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






    
