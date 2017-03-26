## Request Module
### Introduction
```
Requests will allow you to send HTTP/1.1 requests using Python. With it, you can add content like headers, form data, multipart files, and parameters via simple Python libraries. It also allows you to access the response data of Python in the same way.
```
### Make a GET  request
```python
import requests
URL = "http://maps.googleapis.com/maps/api/geocode/json"
location = "delhi technological university"
PARAMS = {'address':location}
r = requests.get(url = URL, params = PARAMS)
data = r.json()
 latitude = data['results'][0]['geometry']['location']['lat']
longitude = data['results'][0]['geometry']['location']['lng']
formatted_address = data['results'][0]['formatted_address']
print("Latitude:%s\nLongitude:%s\nFormatted Address:%s"
      %(latitude, longitude,formatted_address))
```
Output:
```
Latitude:28.7499867
Longitude:77.1183137
Formatted Address:Delhi Technological University, Shahbad Daulatpur Village, Rohini, Delhi, 110042, India
```
### Make a POST request
```python
import requests
 API_ENDPOINT = "http://pastebin.com/api/api_post.php"
API_KEY = "XXXXXXXXXXXXXXXXX"
source_code = '''
print("Hello, world!")
a = 1
b = 2
print(a + b)
'''
data = {'api_dev_key':API_KEY,
        'api_option':'paste',
        'api_paste_code':source_code,
        'api_paste_format':'python'}
 
r = requests.post(url = API_ENDPOINT, data = data)
pastebin_url = r.text
print("The pastebin URL is:%s"%pastebin_url)
```
Output:
```python
This example explains how to paste your source_code to pastebin.com by sending POST request to the PASTEBIN API.You will need to generate an API key here http://pastebin.com/signup
    data = {'api_dev_key':API_KEY,
            'api_option':'paste',
            'api_paste_code':source_code,
            'api_paste_format':'python'}
Here again, we will need to pass some data to API server. We store this data as a dictionary.
    r = requests.post(url = API_ENDPOINT, data = data)
Here we create a response object ‘r’ which will store the request-response. We use requests.post() method since we are sending a POST request. The two arguments we pass are url and the data dictionary.
    pastebin_url = r.text
In response, the server processes the data sent to it and sends the pastebin URL of your source_code which can be simply accessed by r.text .
```

