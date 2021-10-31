1. 使用flask_bootstrap(3.0)或bootstrap-flask(4.0) 

   app.py

   ```python
   from flak_bootstrap import Bootstrap
   app=Flask(__name__)
   Bootstrap(app)
   ```

   .html

   ```jinja2
   {%extends "bootstrap/base.html"%}
   ```

   

