# HTTP Traffic Analysis Lab
## Overview
This project involved hosting a local Python HTTP server inside a Kali Linux virtual machine and analyzing network traffic generated when accessing the webpage using Wireshark.

Key concepts explored included:

- client/server communication
- HTTP requests
- TCP connections
- localhost networking
- packet analysis 
## Environment
- Kali Linux VM
- VirtualBox
- Wireshark
- Python 3 HTTP server
## Steps Performed
1. Created a local project directory in Kali Linux.
2. Created a simple HTML webpage.
3. Hosted the webpage locally using Python's built-in HTTP server.
4. Captured loopback traffic using Wireshark.
5. Accessed the webpage through Firefox.
6. Filtered and analysed HTTP traffic in Wireshark.
## Commands Used
```
mkdir ~/Documents/webproject
cd ~/Documents/webproject

nano index.html

python3 -m http.server 8000
```
## Findings
- Accessing the local webpage generated HTTP GET requests visible in Wireshark.
- HTTP traffic was readable in plaintext because no TLS encryption was used.
- Traffic to 127.0.0.1 used the loopback interface (lo) rather than eth0.
- TCP was used as the transport protocol for HTTP communication.
## Key Concepts Learned
- Difference between localhost and external network interfaces
- Relationship between HTTP and TCP
- Basic packet capture and filtering in Wireshark
- How local web servers operate
- Importance of encryption for protecting web traffic

## Screenshots
