# EX01 Developing a Simple Webserver
## Date:5/10/2025

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TCP/IP Protocol Table</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            padding: 20px;
        }
        table {
            width: 60%;
            border-collapse: collapse;
            margin: auto;
            background-color: #fff;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        th, td {
            border: 1px solid #ccc;
            padding: 12px;
            text-align: center;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        caption {
            font-size: 1.5em;
            margin-bottom: 10px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <table>
        <caption>TCP/IP Protocol Layers</caption>
        <tr>
            <th>Layer</th>
            <th>Description</th>
            <th>Protocols</th>
        </tr>
        <tr>
            <td>Application Layer</td>
            <td>Provides network services to end-users and applications</td>
            <td>HTTP, FTP, SMTP, DNS</td>
        </tr>
        <tr>
            <td>Transport Layer</td>
            <td>Responsible for end-to-end communication and error checking</td>
            <td>TCP, UDP</td>
        </tr>
        <tr>
            <td>Internet Layer</td>
            <td>Handles logical addressing and routing of data packets</td>
            <td>IP, ICMP, ARP</td>
        </tr>
        <tr>
            <td>Network Access / Link Layer</td>
            <td>Manages physical addressing and media access</td>
            <td>Ethernet, Wi-Fi, PPP</td>
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

## OUTPUT:

<img width="1272" height="675" alt="Screenshot 2025-10-07 154149" src="https://github.com/user-attachments/assets/d7a13555-8811-448d-b21c-66d8b511035a" />

<img width="1275" height="275" alt="Screenshot 2025-10-07 154311" src="https://github.com/user-attachments/assets/d0789287-41ad-41d3-ad5d-9447ae57200d" />

## RESULT:
The program for implementing simple webserver is executed successfully.
