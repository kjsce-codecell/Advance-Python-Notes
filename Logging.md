## Logging
```python
When you transfer money, there are transfer records.
If something goes wrong, people can read the log and has a chance to figure out what happened. 
Likewise, logging is important for system developing, debugging and running. 
When a program crashes, if there is no logging record, you have little chance to understand what happened.
You can use the logging functions by just importing logging.
```
### Logging Levels
```
There are many logging levels. 
The numeric values of logging levels are given in the following table. 
These are primarily of interest if you want to define your own levels, and need them to have specific values relative to the predefined levels. 
If you define a level with the same numeric value, it overwrites the predefined value; the predefined name is lost.
```
|Level| Numeric value|
|-----|------|
CRITICAL|50
ERROR|40
WARNING|30
INFO|20
DEBUG|10
NOTSET|0
```python
They are usually used with:
logging.basciConfig(level=logging.DEBUG)  Or
logging.basciConfig(level=logging.INFO)
```
### Steps
```python
Create a file and enter the logging code and then run the code , output will appear on the shell.
If you are using any file name like:
logging.basicConfig(filename='example.log',level=logging.DEBUG)
Then you can see your output in the file named ‘example’ .
However the default level is WARNING
```
#### Case 1
```python
If no level was mentioned:
It does not take the .info information
```
![Code1](/images/LO1.png)
![Code2](/images/LO2.png)
#### Case 2
```python
When level was debug, all the statements were executed.
```
![Code3](/images/LO3.png)
![Code4](/images/LO4.png)
```python
Here we can see that logging is similar to print statements
But..
It works when the program is a simple script, but for complex systems, you better not to use this approach. First of all, you cannot leave only important messages in the log, you may see a lots of garbage messages in the log, but can’t find anything useful.You also cannot control those print statements without modifying code, you may forgot to remove those unused prints.

It can be used with some formatting functions also:
```
![Code5](/images/LO5.png)
![Code6](/images/LO6.png)

