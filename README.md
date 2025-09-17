# EX01 Developing a Simple Webserver
## Date:17/09/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler

html_content = """
<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Overview</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #eef2f3;
            margin: 0;
            padding: 20px;
        }
        h1, h2 {
            text-align: center;
            color: #333;
        }
        table {
            width: 90%;
            margin: 20px auto;
            border-collapse: collapse;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            background-color: #ffffff;
        }
        th, td {
            padding: 14px 18px;
            border: 1px solid #ccc;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        tr:nth-child(even) {
            background-color: #f2f2f2;
        }
        tr:hover {
            background-color: #d1e7dd;
        }
        footer {
            text-align: center;
            margin-top: 40px;
            color: #666;
        }
    </style>
</head>
<body>
    <h1>Welcome to the TCP/IP Protocol Overview</h1>
    <h2>Understanding the OSI & TCP/IP Networking Layers</h2>

    <table>
        <tr>
            <th>OSI Layer</th>
            <th>TCP/IP Layer</th>
            <th>Protocol</th>
            <th>Description</th>
        </tr>
        <tr>
            <td>Application</td>
            <td>Application</td>
            <td>HTTP, FTP, DNS, SMTP</td>
            <td>Provides services directly to users and applications, like web browsing and email.</td>
        </tr>
        <tr>
            <td>Presentation</td>
            <td>Application</td>
            <td>SSL/TLS, JPEG, MPEG</td>
            <td>Formats and encrypts data; ensures compatibility across systems.</td>
        </tr>
        <tr>
            <td>Session</td>
            <td>Application</td>
            <td>NetBIOS, PPTP</td>
            <td>Manages connections and sessions between applications.</td>
        </tr>
        <tr>
            <td>Transport</td>
            <td>Transport</td>
            <td>TCP, UDP</td>
            <td>Ensures reliable or fast delivery of data between hosts.</td>
        </tr>
        <tr>
            <td>Network</td>
            <td>Internet</td>
            <td>IP, ICMP, ARP</td>
            <td>Routes data across networks and handles logical addressing.</td>
        </tr>
        <tr>
            <td>Data Link</td>
            <td>Network Access</td>
            <td>Ethernet, PPP, Switches</td>
            <td>Transfers data between physically connected devices in a network.</td>
        </tr>
        <tr>
            <td>Physical</td>
            <td>Network Access</td>
            <td>Fiber, Ethernet Cables, Wi-Fi</td>
            <td>Transmits raw bits over a physical medium like cables or air.</td>
        </tr>
    </table>

    <footer>
        &copy; 2025 TCP/IP Education Server — Built with Python and 💻
    </footer>
</body>
</html>
"""

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print(f"GET request from {self.client_address[0]}:{self.client_address[1]}")
        self.send_response(200)
        self.send_header('Content-Type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(html_content.encode('utf-8'))

server_address = ('', 8080)
httpd = HTTPServer(server_address, MyHandler)

print("✅ Web server is running at http://localhost:8080")
httpd.serve_forever()

~~~
## OUTPUT:
![alt text](<Screenshot 2025-09-17 113737.png>)
![alt text](<Screenshot 2025-09-17 113845.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

