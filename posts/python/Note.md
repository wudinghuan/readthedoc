得到当前运行文件的路径
import os
a=os.path.dirname(__file__)

__file__是一个全局变量，保存运行的文件路径及文件名，如
>>> __file__
'/home/wu/文档/programming/python/selenium/te.py'


import os
from flask import Flask
app = Flask(__name__)
os.path.join(app.root_path, 'data.db')#这行是怎样运行的
>>> os.path
<module 'posixpath' from '/usr/lib/python3.9/posixpath.py'>
>>> os.path.join(app.root_path, 'data.db')
'/home/wu/data.db'
>>> app.root_path
'/home/wu'
'''
    join(a, *p)
        Join two or more pathname components, inserting '/' as needed.
        If any component is an absolute path, all previous path components
        will be discarded.  An empty last part will result in a path that
        ends with a separator.
'''
