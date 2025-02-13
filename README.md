To run locally, just create a simple python server:
```py
from http.server import HTTPServer, SimpleHTTPRequestHandler

class CORSRequestHandler(SimpleHTTPRequestHandler):
    def end_headers(self):
        self.send_header('Content-Type', 'text/html; charset=utf-8')
        super().end_headers()

httpd = HTTPServer(('localhost', 8000), CORSRequestHandler)
print("Serving at port 8000")
httpd.serve_forever()

```
