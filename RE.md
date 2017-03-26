## Regular Expresion 
### What is it?
```
A regular expression is a special sequence of characters that helps you match or find other strings or sets of strings, using a specialized syntax held in a pattern.

There are various characters, which would have special meaning when they are used in regular expression. To avoid any confusion while dealing with regular expressions, we would use Raw Strings as r'expression'.
```
### Match Function
```
This function attempts to match RE pattern to string with optional flags.
Here is the syntax for this function −
```
```python
re.match(pattern, string, flags=0)
```
```
Here is the description of the parameters:
```
|Parameter | Description |
| ------ | ------ |
|pattern|	This is the regular expression to be matched.|
|string|	This is the string, which would be searched to match the pattern at the beginning of string.|
|flags|	You can specify different flags using bitwise OR. These are modifiers, which are listed in the table below.|
#### Example
```python
#!/usr/bin/python
import re

line = "Cats are smarter than dogs"

matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I)

if matchObj:
   print "matchObj.group() : ", matchObj.group()
   print "matchObj.group(1) : ", matchObj.group(1)
   print "matchObj.group(2) : ", matchObj.group(2)
else:
   print "No match!!"
```
The result obtained will be:-
``` python
matchObj.group() :  Cats are smarter than dogs
matchObj.group(1) :  Cats
matchObj.group(2) :  smarter
```
### Match Function
```
This function searches for first occurrence of RE pattern within string with optional flags.
Here is the syntax for this function:
```
```python
re.search(pattern, string, flags=0)
```
The re.search function returns a match object on success, none on failure. We use group(num) or groups() function of match object to get matched expression.
|Match Object Methods | Description |
| ------ | ------ |
group(num=0)|	This method returns entire match (or specific subgroup num)
groups()|	This method returns all matching subgroups in a tuple (empty if there weren't any)

#### Example
```python
#!/usr/bin/python
import re

line = "Cats are smarter than dogs";

searchObj = re.search( r'(.*) are (.*?) .*', line, re.M|re.I)

if searchObj:
   print "searchObj.group() : ", searchObj.group()
   print "searchObj.group(1) : ", searchObj.group(1)
   print "searchObj.group(2) : ", searchObj.group(2)
else:
   print "Nothing found!!"
```
Output:
```python
searchObj.group() :  Cats are smarter than dogs
searchObj.group(1) :  Cats
searchObj.group(2) :  smarter
```
### Match vs Search
```
match checks for a match only at the beginning of the string, while search checks for a match anywhere in the string.
```
#### Example
```python
#!/usr/bin/python
import re

line = "Cats are smarter than dogs";

matchObj = re.match( r'dogs', line, re.M|re.I)
if matchObj:
   print "match --> matchObj.group() : ", matchObj.group()
else:
   print "No match!!"

searchObj = re.search( r'dogs', line, re.M|re.I)
if searchObj:
   print "search --> searchObj.group() : ", searchObj.group()
else:
   print "Nothing found!!"
```
Output:
```python
No match!!
search --> matchObj.group() :  dogs
```
### Search and Replace
```python
re.sub(pattern, repl, string, max=0)
This method replaces all occurrences of the RE pattern in string with repl, substituting all occurrences unless max provided. This method returns modified string.
```
#### Example
```python
#!/usr/bin/python
import re

phone = "2004-959-559 # This is Phone Number"

# Delete Python-style comments
num = re.sub(r'#.*$', "", phone)
print "Phone Num : ", num

# Remove anything other than digits
num = re.sub(r'\D', "", phone)    
print "Phone Num : ", num
```
Output:
```python
Phone Num :  2004-959-559
Phone Num :  2004959559
```







