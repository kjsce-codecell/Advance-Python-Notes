## Beautiful Soup
### Introduction
```
Beautiful Soup is a Python library for pulling data out of HTML and XML files.At the beginning of your Python script, import the library.Now you have to pass something to BeautifulSoup to create a soup object. That could be a document or an URL.BeautifulSoup does not fetch the web page for you, you have to do that yourself. 
```
### Filtering
#### String
```
The simplest filter is a string. 
Pass a string to a search method and Beautiful Soup will perform a match against
that exact string. 
```
```python
This code finds all the 'b' tags in the document (you can replace b with any
tag you want to find)

soup.find_all('b')
```
#### Regular Expression
```python
If you pass in a regular expression object, Beautiful Soup will filter against
that regular expression using its match() method. 

This code finds all the tags whose names start with the letter "b",
in this case, the 'body' tag and the 'b' tag:

import re
for tag in soup.find_all(re.compile("^b")):
    print(tag.name)

This code finds all the tags whose names contain the letter "t":

for tag in soup.find_all(re.compile("t")):
    print(tag.name)
```
#### List
```python
If you pass in a list, Beautiful Soup will allow a string match against any
item in that list. 

This code finds all the 'a' tags and all the 'b' tags

print soup.find_all(["a", "b"])
```
### Example
One common task is extracting all the URLs found within a page’s 'a' tags.Using the find_all method, gives us a whole list of elements with the tag "a". 
```python
for link in soup.find_all('a'):
    print(link.get('href'))
```
Another common task is extracting all the text from a page:
```python
print(soup.get_text())
```


