# EX01 Developing a Simple Webserver
## Date: 06/10/2023

## AIM:
To develop a simple webserver to serve html pages.

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
~~~
from http.server import HTTPServer,BaseHTTPRequestHandler
content="""
<html>
<head>
<title>Django</title>
</head>
<body>
<h1>Django</h1>
<p>This is Web Application Framework written in python</p>
</body>
</html>
""" 

class myhandler(BaseHTTPRequestHandler):
     def do_GET(self):
         print("request received")
         self.send_response(200)
         self.send_header('content-type','text/html; charset=utf-8')
         self.end_headers()
         self.wfile.write(content.encode())
server_address = ('',8001)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running....")
httpd.serve_forever()
~~~

## OUTPUT:
![image](https://github.com/Selvakumar525/simplewebserver/assets/120643262/dfcc9e7d-f55d-4ad2-a31a-ae66faf6429b)


## RESULT:
The program for implementing simple webserver is executed successfully.
