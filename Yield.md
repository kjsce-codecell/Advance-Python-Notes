## Yield
```python
When we call a function in Python, the function will normally start working until it encounters a return, exception, 
or reaches its end – after which it returns control back to the caller. 
Whenever you call that function again, the process will start from scratch!
Whereas in case of the yield statement, it suspends function’s execution and sends a value back to calle,
but retains enough state to enable function to resume where it is left off.
When resumed, the function continues execution immediately after the last yield run. 
This allows its code to produce a series of values over time, rather them computing them at once and sending them back like a list. 
```
![Code1](/images/Y1.png)
```python
Here we can’t return 2 values at a time.Using yield, it is allowed.
```
![Code2](/images/Y2.png)
```python
Yield are used in Python generators. A generator function is defined like a normal function, but whenever it needs to generate a value, it does so with the yield keyword rather than return. If the body of a def contains yield, the function automatically becomes a generator function.
```
![Code3](/images/Y3.png)
```python
Or it could be like this:
```
![Code4](/images/Y4.png)

