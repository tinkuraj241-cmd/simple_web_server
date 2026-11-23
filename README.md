# EX01 Developing a Simple Webserver

# Date: 23.11.2026
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
<!DOCTYPE html>
<html>
    <head>
        <title>DEVICE SPECIFICATIONS</title>
    </head>

    <body bgcolor="pink">
        <h1 align="center">DEVICE SPECIFICATIONS - 26014864</h1>
        <table border="2">
            <tr bgcolor="purple">
                <th>S.No</th>
                <th>Device Specification</th>
                <th>Description</th>
            </tr>
            <tr>
                <td>1</td>
                <td>Storage</td>
                <td>954GB</td>
            </tr>
            <tr>
                <td>2</td>
                <td>Graphics Card</td>
                <td>128MB</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Installed RAM</td>
                <td>16.0GB</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Processor</td>
                <td>Intel(R) Core(TM) Ultra 5 125H</td>
            </tr>
            <tr>
                <td>5</td>
                <td>Device Name</td>
                <td>Deepa</td>
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
<img width="1920" height="1080" alt="Screenshot (30)" src="https://github.com/user-attachments/assets/4613fbf5-ff50-49be-a5e2-796f89d06550" />

# RESULT:
The program for implementing simple webserver is executed successfully.
