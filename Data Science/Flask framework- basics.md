- framework :)
- end to end web framework
- WSGI - web server Gateway Interface
	- it's a protocol ![[Pasted image 20250807151746.png]]
- Jinja 2 Web Template engine
	- combines web template(pages) with a data source (SQL db, csv sheet , ml model , mongodb etc)
	- creates dynamic web pages
# Flask
- basic skeleton
```python
from flask import Flask
# creates instance of Flask class, which will be ur WSGI application
app=Flask(__name__)                         # WSGI application
  
if __name__== '__main__':                    # entry point
    app.run()
```
	`python app.py` to run the app
- unless u restart the server,no changes in code will be visible on web page, even if saved
	- `app.run(debug= True)`  -> the changes automatically shows after saving
```python
from flask import Flask
app=Flask(__name__)
  
@app.route("/")
def welcome():
    return "welcome to this Flask course"
    
@app.route("/index"):
def index():
    return "ts index twin"

  
if __name__== '__main__':                    # entry point
    app.run(debug= True)
```
- to integrate html we gotta render html , so we use `render_templete` with jinja