## Lambda
```python
Lambda functions are called as anonymous functions i.e a function that is defined without a name.
The general syntax of a lambda function is quite simple:
lambda argument_list: expression
Lambda is a tool for building functions, or more precisely, for building function objects. 
That means that Python has two tools for building functions: 
def and lambda.
Def:
```
![Code1](/images/L1.png)
```python
Lambda:
```
![Code2](/images/L2.png)
```python
Generally, functions are created for  to reduce code duplication, or to modularize code.
But suppose you need to create a function that is going to be used only once.
Well, first of all, you don’t need to give the function a name. 
It can be “anonymous”. And you can just define it right in the place where you want to use it. 
That’s where lambda is useful.
Lambda functions are mainly used in combination with the functions filter(), map() and reduce().
```
### With Map
```python
r = map(func, seq)
The first argument func is the name of a function and the second a sequence (e.g. a list) seq. map() applies the function func to all the elements of the sequence seq. 
It returns a new list with the elements changed by func.
Here is an example where using lambda with map reduces the size of  code which was earlier written by normal functions.
```
![Code3](/images/L3.png)
![Code4](/images/L4.png)
### With FILTER()
```pyhton
The function filter(function, list) offers an elegant way to filter out all the elements of a list, for which the function function returns True.
```
![Code5](/images/L5.png)
