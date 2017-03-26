## JSON Module
### What is it?
```
The json library can parse JSON from strings or files. The library parses JSON into a Python dictionary or list. It can also convert Python dictionaries or lists into JSON strings.
```
### How to use?
Take the following string containing JSON data:
```python
json_string = '{"first_name": "Guido", "last_name":"Rossum"}'
```
It can be parsed like this:
```python
import json
parsed_json = json.loads(json_string)
```
and can now be used as a normal dictionary:
```python
print(parsed_json['first_name'])
"Guido"
```
You can also convert the following to JSON:
```python
d = {
    'first_name': 'Guido',
    'second_name': 'Rossum',
    'titles': ['BDFL', 'Developer'],
}

print(json.dumps(d))
'{"first_name": "Guido", "last_name": "Rossum", "titles": ["BDFL", "Developer"]}'
```



### Example
#### Python Dictionaries to JSON Strings
Code:
```python
import json 
student = {"101":{"class":'V', "Name":'Rohit',  "Roll_no":7}, 
         "102":{"class":'V', "Name":'David',  "Roll_no":8},  
         "103":{"class":'V', "Name":'Samiya', "Roll_no":12}}  
print(json.dumps(student)); 
```
Output
```
{"103": {"class": "V", "Name": "Samiya", "Roll_no": 12}, 
"102": {"class": "V", "Name": "David", "Roll_no": 8}, 
"101": {"class": "V", "Name": "Rohit", "Roll_no": 7}}
```
#### JSON Strings to Python Dictionaries
Code:
```python
import json 
json_data = '{"103": {"class": "V", "Name": "Samiya", "Roll_n": 12}, "102": {"class": "V", "Name": "David", "Roll_no": 8}, "101": {"class": "V", "Name": "Rohit", "Roll_no": 7}}'; 
print(json.loads(json_data)); 
```
Output:
```
{"103": {"class": "V", "Name": "Samiya", "Roll_no": 12}, 
"102": {"class": "V", "Name": "David", "Roll_no": 8}, 
"101": {"class": "V", "Name": "Rohit", "Roll_no": 7}}
```

