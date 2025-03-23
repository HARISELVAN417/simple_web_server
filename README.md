# EX01 Developing a Simple Webserver

# Date:23-03-2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
    <title>LAPTOP CONFIGURATION</title>
</head>

<body><center>
    <h1>My laptop configuration</h1>HARISELVAN.S<h1></h1></center>
    <table border="50px" align="center" cellpadding="10" style="background-color: blue;" >
    <tr style="color: red; ">
        <th>DEVICE SPECIFICATION</th>
        <th>DETAILS</th>
    </tr>
    <tr style="color: black; ">
        <td>BRAND</td>
        <td>LENOVO</td>
    </tr>
    <tr>
        <td>MODEL NAME</td>
        <td>E16 GEN 4</td>
    </tr>
    <tr>
        <td>SCREEN SIZE</td>
        <td>15.5 inches</td>
    </tr>
    <tr>
        <td>COLOR</td>
        <td>BLACK</td>
    </tr>
    <tr>
        <td>RAM</td>
        <td>16GB</td>
    </tr>
    <tr>
        <td>ROM</td>
        <td>286GB</td>
    </tr>    
    <tr>
        <td>HARD DISK</td>
        <td>CORE i5</td>
    </tr>
    <tr>
        <td>GRAPHICS CARD</td>
        <td>NVIDIA</td>
    </tr>
    <tr>
        <td>SYSTEM TYPE</td>
        <td>64 BIT-OS,X64</td>
    </tr>
</table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot 2025-03-23 154248.png>)
![alt text](<Screenshot 2025-03-23 154225.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
