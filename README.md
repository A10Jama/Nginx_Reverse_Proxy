# Nginx_Reverse_Proxy
## What are ports?
a reverse proxy listens on the same port as the client making the request, and then forwards the request to a different port on the backend server.

## What is a reverse proxy? How is it different to a proxy?
A reverse proxy is a server that sits between a client and a backend server, acting as an intermediary for incoming client requests. 
The reverse proxy receives requests from clients and forwards them to the appropriate backend server, and then returns the server's response to the client as if it came directly from the reverse proxy itself.

The key difference between a reverse proxy and a proxy is the direction of the traffic flow. 
A reverse proxy forwards incoming client requests to backend servers, while a proxy forwards outgoing client requests to the internet.

## Reverse Proxy Diagram
A reverse proxy typically sits between the client and the backend server, as shown in this diagram:
![image](https://user-images.githubusercontent.com/129948378/232846048-126cd173-abf9-48f0-8344-9721a5853659.png)

In this diagram, the client sends HTTP requests to the reverse proxy server, which receives the request, processes it, and forwards it to the appropriate backend server. 
The backend server processes the request and sends the response back to the reverse proxy, which in turn sends the response back to the client.

The reverse proxy server can perform several functions, such as load balancing, SSL termination, content caching, and protocol translation. 
By handling these functions, the reverse proxy can help improve the performance, security, and scalability of the application.


