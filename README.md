# EX01 Developing a Simple Webserver

# Date: 24.11.2026
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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """


<!DOCTYPE html>
<html>
<head>
    <title>MY LAPTOP INFO</title>
</head>
<body>
    <h1 align="center">MY LAPTOP INFO</h1>
    <table border="1" cellpadding="10" cellspacing="0" align="center">
        <tr>
            <th>Specification</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Model Name</td>
            <td>TL15-53M-G2</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel(R) Core(TM) 5 210H (2.20 GHz)</td>
        </tr>
        <tr>
            <td>RAM</td>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>
        <tr>
            <td>Graphics card</td>
            <td>Intel(R) Graphics (128 MB)</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>143 GB of 477 GB used</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>8DD2641A-B2C5-44CF-A19A-28648155E14B</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00342-42945-51992-AAOEM</td>
        </tr>
        <tr>
            <td>System type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
</body>
</html>"""
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get Request Recived...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address=("",8000)
httpd=HTTPServer(server_address,Myserver)
httpd.serve_forever()
# OUTPUT:
<img width="1920" height="1080" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/562d3010-05f4-4743-a342-a2bcc1ffa050" />

<img width="1920" height="1080" alt="Screenshot (33)" src="https://github.com/user-attachments/assets/6343a65c-2bcd-4a0b-a394-2a402e7c80c9" />



# RESULT:
The program for implementing simple webserver is executed successfully.
