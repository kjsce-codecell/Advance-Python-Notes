## With As
```python
With the "With" statement, you get better syntax and exceptions handling. 
The with statement simplifies exception handling by encapsulating common preparation and cleanup tasks.
In addition, it will automatically close the file. 
The with statement provides a way for ensuring that a clean-up is always used.
The lines after as can be used as an object to refer that.Without the with statement,
we would write something like this:

file = open("hello.txt")
data = file.read()
print data
file.close()  # It's important to close the file when you're done with it

With Statement Usage
Opening a file using with is as simple as: 

with open(filename) as file:
with open("hello.txt") as inFile: # Use file to refer to the file object
   data = inFile.read()
   print data

Here we did not write separate close statement as it is handled by with.
```
![Output](/images/WA1.png)
```
Above is the file hello.txt
```
![Code](/images/WA2.png)
```python
Thus we can see that when we use “with” statement there is no need of separate close statement.
With more than one item, the context managers are processed as if multiple with statements were nested:
with A() as a, B() as b:
    suite
is equivalent to
with A() as a:
    with B() as b:
        suite
```



