## In-Build Generators:
A generator is a function that generates output whenever you call it and remembers the current state untill the next call is made

A simple example of a generator is ```range()``` function in python

```python 
# this code will freeze you pc if it generates the entire list
# and saves it to memory
#but it doesn't
range(90000000000000000000000000)
```
The reason is this creates a generator which calculates next element every time you call it

### Use of in-build generators
To create a generator we have to write our expression inside parenthesis '()'.
```python
n = 10
# this creates a generator that gives even i upto n
gen = (i for i in range(n) if i%2 == 0)
for i in gen:
    print(i)

# this creates a list that contains even i upto n
# as this creates the entire list at once it's not a generators
# you can call it one line for-loops
# also known as list comprehensions
l = [i for i in range(n) if i%2 == 0]
```

## Custom Generators.

To create more powerfull generators you can use this technique

__Program to calculate fibonacci__
```python
# normal method
def fibo(n):
    f0 = 0
    print(0)
    f1 = 1
    print(1)
    for i in range(n-2):
        temp = f1
        f1 = f1+f0
        f0 = temp
        print(f1)
        
# generator method
def fibo(n):
    f0 = 0
    yield f0
    f1 = 1
    yield f1
    for i in range(n-2):
        temp = f1
        f1 = f1+f0
        f0 = temp
        yield f1

```
### Important points
1. Generators consume more time but are memory efficient and do not blow up your ram by calculating everything before hand. 
2. Normal method is faster but comsumes more ram memory.
