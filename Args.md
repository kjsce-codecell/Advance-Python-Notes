## Args and Kwargs
```python
The purpose of *args is that, *args are used to help the developer passing a variable number 
of arguments to a function.
The symbol * makes args iterable which means that you can run a for loop and process 
every argument inside the args list.
```
### Example
![Code1](/images/A1.png)
```
Now what if you want to pass a list and print every number in the list
```
![Code2](/images/A2.png)
```python
The list is getting printed in one line as the whole list is taken as 1 parameter.
Suppose if you want to print each element of the list then while passing parameters in call add * before list name.
```
![Code3](/images/A3.png)
```
**kwargs help the developer to give arbitrary keyworded arguments to a
function and access them later in a dictionary.
We will see an example where we are passing 2 parameters to a
function with 2 parameters and to a function with kargs parameter.
```
![Code4](/images/A4.png)
```
We can see that in the former case it is printing 1 1 so we cannot identify which is x and which is y, But in the latter case it is easily recognizable.

What if we only want to print the value of x then:
```
![Code5](/images/A5.png)
```
Now if we want to use *args and **kwargs together:
First we should see to it that *args should always be before 
**kwargs or else it will throw an error message.
```
![Code6](/images/A6.png)
![Code7](/images/A7.png)
