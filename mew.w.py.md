## MEW 2

*brave-search:*
`Vercel with Python Tutorial`

**Step 1: Create a new Python project**

* Initialize a new Python project using `pipenv` (or `virtualenv` :/)
* Install required dependencies, including `http.server` for the example

**Step 2: Write your Python function**

* Create a Python file (e.g., `index.py`) with a single HTTP handler function
* Use `BaseHTTPRequestHandler` from `http.server` to define the handler
* In this example, the handler returns a simple "Hello, world!" response

**Step 3: Configure Vercel**

* Create a `vercel.json` file with the following configuration:
	+ `builds`: specifies the source file and builder to use (in this case, `@ardnt/vercel-python-wsgi`)
	+ `routes`: maps incoming requests to your Python function
* Set `maxLambdaSize` to a suitable value (e.g., 15mb) to accommodate larger Django applications

**Step 4: Deploy to Vercel**

* Run `vercel` in your project directory to set up and deploy your application
* Verify that your Python function is accessible via the Vercel-provided URL

**Example Code**

* `index.py`:
```python
from http.server import BaseHTTPRequestHandler

class handler(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header('Content-type', 'text/plain')
        self.end_headers()
        self.wfile.write('Hello, world!'.encode('utf-8'))
        return

def main():
    from http.server import HTTPServer
    server_address = ('', 8000)
    httpd = HTTPServer(server_address, handler)
    httpd.serve_forever()

if __name__ == '__main__':
    main()
```
* `vercel.json`:
```json
{
  "builds": [
    {
      "src": "index.py",
      "use": "@ardnt/vercel-python-wsgi",
      "config": {
        "maxLambdaSize": "15mb"
      }
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "index.py"
    }
  ]
}
```
**Additional Tips**

* Use a `requirements.txt` file to specify dependencies for your Python project
* For larger Django applications, consider using a more robust builder like `@ardnt/vercel-python-wsgi` to handle dependencies and configuration
* Be mindful of Vercel's limitations, such as function duration and CPU time, when designing your Python function


