# Nginx_Reverse_Proxy
## What are ports?

A port is where network connections start and end, these are managed by a computers operating system. each port has a specific process or service and numbering them allows computers to easily differentiate between them. A reverse proxy listens on the same port as the client making the request, and then forwards the request to a different port on the backend server.

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

## What is Nginx's default configuration ?
By default, Nginx comes with a directory named sites-available that stores configuration files for hosting various websites or web applications on the server. Typically, this folder can be found at /etc/nginx/sites-available/ on Unix-based operating systems like Linux.

## to set up a reverse proxy on nginx

1. First thing to do is to install and update Nginx on your VM with `sudo apt-get install nginx`
2. Configure a new virtual host that listens on the desired port (e.g., port 80)
3. Set up the reverse proxy in the virtual host configuration, specifying the backend server(s) to forward requests to, and any necessary proxy headers.
4. Start or restart the Nginx service to apply the new configuration.

the code we use for this configeration 
https://github.com/A10Jama/Nginx_Reverse_Proxy/blob/main/nginxcode.md

`cd /etc/nginx/sites-available`: This command changes the current working directory to the Nginx sites-available directory.

`sudo rm -rf default`: This command deletes the default Nginx configuration file that may exist in the sites-available directory.

`sudo echo "..."`: This command adds a new server block configuration for Nginx by printing the text enclosed in double-quotes to the terminal and redirecting it to the Nginx default configuration file.

`listen 80;`: This line sets the server to listen on port 80.

`server_name _;`: This line sets the server name to match any request that comes to it.

`proxy_pass http://192.168.10.100:3000;`: This line sets the proxy_pass to  IP address and port 3000

We are then left with the below screen when typing the proxy pass ip address.
<img width="1219" alt="Screenshot 2023-04-19 at 16 30 12" src="https://user-images.githubusercontent.com/129948378/233125715-57c7e2db-ecbb-432c-b451-244fa1be9f33.png">

