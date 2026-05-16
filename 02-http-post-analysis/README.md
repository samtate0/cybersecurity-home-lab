# HTTP POST Request Analysis Lab
## Overview
This project involved creating a local HTML login form hosted on a Kali Linux virtual machine and analysing HTTP POST request behaviour using Wireshark.

The investigation focused on understanding:
- HTML form submission
- HTTP POST requests
- Plaintext web traffic
- Client/server communication
- Limitations of static HTTP servers
- Packet analysis using Wireshark
## Environment
- Kali Linux VM
- VirtualBox
- Wireshark
- Python 3 HTTP server
- HTML login form
## Steps Performed
1. Created a local project directory in Kali Linux.
2. Built a simple HTML login form containing username and password input boxes.
3. Hosted the webpage locally using Python's built-in HTTP server.
4. Started packet capture on the loopback (`lo`) interface using Wireshark.
5. Submitted test credentials through the login form.
6. Inspected generated HTTP traffic and POST requests.
## Commands Used
```
mkdir ~/Documents/phishinglab
cd ~/Documents/phishinglab

nano phishingpage.html

python3 -m http.server 8000
```
## HTML Form Used
```
<h1>Login</h1>

<form action="/login" method="POST">
  <label>Username:</label><br>
  <input type="text" name="username"><br>

  <label>Password:</label><br>
  <input type="password" name="password"><br>

  <input type="submit" value="Login">
</form>
```
## Findings
- Submitting the form generated an HTTP POST request visible in Wireshark.
- The browser attempted to send submitted form data to the `/login` endpoint.
- Python's built-in HTTP server returned a `501 Unsupported method` error because it does not support backend POST request handling by default.
- The project demonstrated the difference between:
  - serving static webpages
  - processing server-side application data
- The investigation reinforced tha HTTP traffic is transmitted without encryption when TLS/HTTPS is not used.
## Key Concepts Learnt
- Difference between HTTP GET and POST requests.
- Relationship between frontend HTML forms and backend server processing.
- Limitations of Python's simple HTTP server.
- How form submissions generate HTTP POST traffic.
- Importance of HTTPS for protecting transmitted credentials.
## Screenshots
<img width="693" height="393" alt="HTML-login-page" src="https://github.com/user-attachments/assets/2b7351c2-9dcd-4db9-8b5a-474e374439f2" />
<img width="1718" height="584" alt="HTTP-POST-request" src="https://github.com/user-attachments/assets/0215cd43-9153-4dbe-acbd-d3b7063360ba" />
