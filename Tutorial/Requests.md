# Requests

This tutorial is for beginner in python.
</br>You will see how to collect information on web page with the library requests.
## Installation :
```sh
pip install requests
```
You can follow installation on official website : [Requests http for humans](http://docs.python-requests.org/en/latest/user/install/)

## Importing the Requests module
To work with the Requests library in Python, you must import the appropriate module. You can do this simply by adding the following code at the beginning of your script:

```python
import requests
```

## Making a Request and Working with

```python
#!/usr/bin/env python
import requests

# Define your target webpage
target_webpage = ""

# To get a webpage you would do something like the following :
# Here, we use the GET method but you can use POST method too
r = request.get(target_webpage)

# If we print r we can see the status (eg. "<Response [200]>" if it's ok, if it's "<Response [404]>" or error something like that it doesn't work)
print (r)

# If you want print your content of your webpage use r.text
print (r.text)
# You can use r.text to work with your data (eg. use condition to see if you have a word in your text to continue or not)

```
## Working with Headers
By utilizing a Python dictionary, you can access and view a server’s response headers. Thanks to how Requests works, you can access the headers using any capitalization you’d like.

If you perform this function but a header doesn’t exist in the response, the value will default to None.
```python
r.headers
{
    'status': '200 OK',
    'content-encoding': 'gzip',
    'transfer-encoding': 'chunked',
    'connection': 'close',
    'server': 'nginx/1.0.4',
    'x-runtime': '148ms',
    'etag': '"e1ca502697e5c9317743dc078f67693f"',
    'content-type': 'application/json; charset=utf-8'
}
```
You can change everything as you want.
</br> And if you want get a headers of a URL :
```python
resp = requests.head("http://wwww.target.com")
print (resp.headers)
```
### Make an HTTP Post Request
We will see now how to perform a Post request.
```python
#!/usr/bin/env python
import requests

# Define your target webpage
target_webpage = ""

# Define your data eg. for a username and password :
payload = (("username","myusername"),("password","mytopsecretpassword"))

# Send your data on post form
r = request.post(target_webpage, data=payload)

# And you can print your response in text
print (r.text)
```
You can also rely on other HTTP requests too, like PUT, DELETE, HEAD, and OPTIONS.
```python
r = requests.put("http://target.com/put")
r = requests.delete("http://target.com/delete")
r = requests.head("http://target.com/get")
r = requests.options("http://target.com/get")
```
