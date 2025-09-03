# EX01 Developing a Simple Webserver
## Date:2-10-2024
## vasnthraj.J

## AIM:
To develop a simple webserver to display the configuration details of my laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<html>
<head>

    <title> My Web Server</title>
</head>
<body>

    <table border="1" align="center" cellpadding="10" bgcolor="blue">
        <caption><h1>List of Protocols in TCP/IP Protocol Suite</h1></caption>
        <tr>
            <th>S.No.</th>
            <th>Name of the Layer</th>
            <th>Name of the Protocol</th>
        </tr>
        <tr>
            <td>1.</td>
            <td>Application Layer</td>
            <td>HTTP, FTP, DNS, Telnet</td>
        </tr>
        <tr>
            <td>2.</td>
            <td>Transport Layer</td>
            <td>TCP & UDP</td>
        </tr>
        <tr>
            <td>3.</td>
            <td>Network layer</td>
            <td>IPV4/IPV6</td>
        </tr>
        <tr>
            <td>4.</td>
            <td>Link layer</td>
            <td>Ethernet</td>
        </tr>
    </table>

</body>
</html>
"""
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address = ('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
## OUTPUT:
<img width="1920" height="1080" alt="Screenshot 2025-09-02 204506" src="https://github.com/user-attachments/assets/cac1dd92-99c2-4661-be07-75f473d7c938" />


## RESULT:
The program for implementing simple webserver is executed successfully.
