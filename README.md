
# Socket Chat Server

Chat Server using Python Sockets. 

## Running the Project

For running the project, you will need to have an server to receive and send messages to clients that are connected, and at least 2 clients to see messages being broadcasted.

### Start the Server
```python
python server.py
```
### Run the Clients in same Network
```python
python client.py
```

  
## Improvement 
For now, i'm using the input function from Python. Eventually, you would probably want to have some sort of GUI here, because the input is going to block the rest of the program from running/updating messages, which means you will have to send a message to see the updates. There are some OS specific methods you can use to get around this, but I am not going to get into that here. If you want to, feel free to research them and implement them. You can add a sys check at the beginning to determine what OS your client is running with.
  
```python

while True:
    message = input(f'{my_username} > ') 

if message:
        message = message.encode('utf-8')
        message_header = f"{len(message):<{HEADER_LENGTH}}".encode('utf-8')
        client_socket.send(message_header + message)
```
