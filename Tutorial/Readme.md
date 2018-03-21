# Python

This tutorial is for beginner in python.
</br>You will see how to use socket and how to collect information on web page with the librairy requests.

## Socket
</br> Definition:
```
Socket :
A socket is an internal endpoint for sending or receiving data at a single node in computer network. Concretely, it is a representation of this endpoint in networking software such as an entry in a table ( listing communication protocol, destination, status etc.), and is a form of system resource. (@wikipedia)
With socket we can connect two computers or servers, together specifying the address and port for each. It works in client/server.  
```
### Netcat
You can start to try socket with the unix command netcat :
</br>Server :
```sh
nc -l Port
```
Client:
```sh
nc Address_Server Port_Server
```
With this, you have a socket connection between a server and a client and you can send message from the client to the server.
### Socket python
Now, we will see how to write our script, server side and client side.  
#### Server side :
```python
#!/usr/bin/env python

import socket

# We start to create our socket
s = s.socket(s.AF_INET, s.SOCK_STREAM)

#AF_INET is an address family that is used to designate the type of addresses that your socket can communicate with (Protocol IPv4).
#SOCK_STREAM is a dialogue support that guarantees integrity, provides a binary data stream, and integrates a mechanism for out-of-band data trasmissions.

# Now, we need to create our listen port
port_listen = 6666
# And we give it to our socket.
# bind : associates the socket with a local address and port.
s.bind(('',port))

# This infinite loop, allows us to display the values that the customer sends us.
while True:
  # Put our socket in listening
  s.listen(5)
  # Accept our client
  client, address = s.accept()

  # Create a receiving buffer
  response = client.recv(255)
  # Print client response
  if response != "":
    print (response)

# Always, we need to close our socket
client.close()
s.close()

```
#### Client Side :
The most important is now, Client side, this is what you will use most often.
```python
#!/usr/bin/env python
import socket

# Create your target, hote (IP Address) and port (eg. : 80)
hote_target = "localhost"
port_target = 6666

# It's the same line like server
s = s.socket(s.AF_INET, s.SOCK_STREAM)

# Here, we connect our socket to hote and port we target
s.connect((hote_target, port_target))
print ("Your message : ")
# Create your message in, you can use input function or dirrectly write your message in your code.
message = input()

# Send your message
s.send(u"",message)
# And close your socket
s.close()

```
With this code, now, you can send message to all server.
