# SOCJock
An important tool for any aspiring penetration tester is the TCP client. 
This is because frequently within larger enterprise environments, the pentester will not always have the luxury of using networking tools or compilers nor even copy/paste. 
A quick run-through of what each line means:

First I created the socket object with the AF_INET and SOCK_STREAM parameters respectively. 
AF_INET indicates that I am using the standard IPv4 address and SOCK_STREAM states that this will be a TCP client.

Next, I connected to the client with client.connect((target_host,target_port))

Then I send some data in the form of bytes ("b") with the line:
client.send(b"GET / HTTP/1.1\r\nHost: google.com\r\n\r\n")

I then ask the client to receive data back and print out the response with the lines: 

response = client.recv(4096)

print(response.decode())
client.close()

Note: in a real-world usecase, this client makes some assumptions, namely that the connection will succeed and the server expects us to send data first instead of the server sending you data and awaiting your response. 
Consequently the efficacy of this TCPClient will vary depending on the target.

This tool is for educational purposes and in no way is an endorsement of unauthorised or illegal activity.
