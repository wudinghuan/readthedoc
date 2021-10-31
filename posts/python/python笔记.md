---

---

---

---

1. 函数

   ```python
   def xxx():
   	....
   ```

   使用时 xxx与xxx()有什么区别？？

   - xxx是地址,xxx()是调用

2. range(1,10)的区间是[1,10)

3. my_items=['a','b','c']

   返回列表的逆序倒序['c', 'b', 'a']: `my_items[::-1]`

4. 清空列表

   del my_items[:]
   my_items
   []

5. 去掉字符串前后的空格和换行符(不知道是否包括所有空白符)
   str.strip()

6. 用空格拼接各个字符串
   ' '.join(['c','o','o','k'])
   返回结果为 c o o k

7. 输出当前日期

   ```python
   import datetime
   today=datetime.date.today()
   
   >>>today
   >>>datetime.date(2020, 12, 14)
   >>>str(today)
   >>>'2020-12-14'
   ```

   

8. 装饰器

   在装饰器中使用functool.wraps

   ```python
   import functools
   
   def uppercase(func):
       @functools.wraps(func)
       def wrapper():
       	return func().upper()
       return wrapper
   ```

   

   ```python
   @uppercase
   def greet():
       '''return a friendly greeting'''
       return 'hello'
   
   >>>greet.__name__
   >>>'greet'
   >>>greet.__doc__
   >>>'return a friendly greeting'
   ```

9. 异常处理 try except else finally

   finally的作用，在程序退出前会被强制执行

   示例代码：

   ```python
   import sys
   
   try:
   	1/0
   except:
   	print("除数不能为0")
   	sys.exit()
   finally:
   	print("执行结束")
   	
   print("这句会执行吗")
   ```

10. 字典

    字典.get('a','b')的作用:

    如果key‘a’在字典中输出值，否则输出‘b’

11. 命令行参数

12. 关于import \__init__.py 模块(module) 包(package)

    目录结构

    ```
    └─demo
            a.py
            b.py
            __init__.py
    ```

     因为有 \__init__.py, 所以demo是个package
    
    - 无论是 `import demo` 或者 `from demo import xxx`, init.py文件中的语句都会执行
    - 可以被导入的文件叫module, 可以被导入的目录叫做包package
    - a.py无法`import demo`,要导入demo相关内容,使用`from . import...`
    - a.py可以`import b`, b.py也可以`import a`
    
    - 包中的<u>类\实例(变量)\普通变量</u>都可以导入使用
    
    ```python
    # __init__.py
    print('<text>')
    v=10
    ```

    
    
    ```python
    # c.py
    from demo import v
    ```
    
    执行c.py时, 输出如下
    
    ```python
    ====================== RESTART: /home/wu/c.py ======================
    <text>
    >>> v
    10
    >>> 
    ```
    
    - 任何py文件都可以import同层级的py文件. 假如demo中没有\_\_init\_\_.py, a.py仍然可以`import b`
    
13. 在其他软件进入交互式shell

    添加以下内容到要运行的文件中

    ```python
    import code
    #你的代码...
    interp = code.InteractiveConsole(globals())
    interp.interact("")
    ```

14. requests禁止重定向

    ```python
    import requests as req
    
    resp = req.get("https://httpbin.org/redirect-to?url=/", allow_redirects=False)
    ```

15. 文件处理

    ```python
    #输出文件的每一行
    
    with open('a.txt','r',encoding='utf-8') as f:
        for i in f:
            print(i)
    ```

16. 字典

    ```python
    >>> a={'a':1,'b':2,'c':3}
    >>> a.keys()
    dict_keys(['a', 'b', 'c'])
    >>> a.values()
    dict_values([1, 2, 3])
    >>> a.items()
    dict_items([('a', 1), ('b', 2), ('c', 3)])
    >>> 
    ```

17. 队列

    ```python
    from collections import deque
    d=deque(maxlen=5)#设置长度
    >>> q = deque() #不设置长度
    >>> q.append(1)
    >>> q.append(2)
    >>> q.append(3)
    >>> q
    deque([1, 2, 3])
    >>> q.appendleft(4)
    >>> q
    deque([4, 1, 2, 3])
    >>> q.pop()
    3
    >>> q
    deque([4, 1, 2])
    >>> q.popleft()
    4
    ```

    在队列两端插入或删除元素时间复杂度都是 `O(1)` ，区别于列表，在列表的开头插入或删除元素的时间复杂度为 `O(N)` 。

18. 从一个集合中获得最大或者最小的 N 个元素列表

    ```
    import heapq
    nums = [1, 8, 2, 23, 7, -4, 18, 23, 42, 37, 2]
    print(heapq.nlargest(3, nums)) # Prints [42, 37, 23]
    print(heapq.nsmallest(3, nums)) # Prints [-4, 1, 2]
    ```

19. 格式化输出{!r}

    输出原内容

    ```python
    >>> a = '123'
    >>> b = 'hello, {!r}'.format(a)
    >>> b
    "hello, '123'"
    ```

20. 元组可以比较

    ```python
    >>> (1,'a')>(2,'b')
    False
    >>> (1,'a')<(2,'b')
    True
    >>> ('a',1)<('b',2)
    True
    >>> ('c',1)<('b',2)
    False
    >>> 
    ```

21. zip()

    执行这些计算的时候，需要注意的是 `zip()` 函数创建的是一个只能访问一次的迭代器。 比如，下面的代码就会产生错误：

    ```python
    prices_and_names = zip(prices.values(), prices.keys())
    print(min(prices_and_names)) # OK
    print(max(prices_and_names)) # ValueError: max() arg is an empty sequence
    ```

22. 集合操作

    ```python
    a = {
        'x' : 1,
        'y' : 2,
        'z' : 3
    }
    
    b = {
        'w' : 10,
        'x' : 11,
        'y' : 2
    }
    ```

    为了寻找两个字典的相同点，可以简单的在两字典的 `keys()` 或者 `items()` 方法返回结果上执行集合操作。比如：

    ```python
    # Find keys in common
    a.keys() & b.keys() # { 'x', 'y' }
    # Find keys in a that are not in b
    a.keys() - b.keys() # { 'z' }
    # Find (key,value) pairs in common
    a.items() & b.items() # { ('y', 2) }
    ```

23. attrgetter与itemgetter的区别

    attrgetter:根据属性排序,如类中的属性, itemgetter:根据项排序,如字典中的key

    ```python
    from operator import itemgetter,attrgetter
    
    class User:
        def __init__(self, user_id):
            self.user_id = user_id
    
        def __repr__(self):
            return 'User({})'.format(self.user_id)
    
    sorted(users, key=attrgetter('user_id'))
    
    rows = [
        {'fname': 'Brian', 'lname': 'Jones', 'uid': 1003},
        {'fname': 'David', 'lname': 'Beazley', 'uid': 1002},
        {'fname': 'John', 'lname': 'Cleese', 'uid': 1001},
        {'fname': 'Big', 'lname': 'Jones', 'uid': 1004}
    ]
    
    sorted(rows, key=itemgetter('uid'))
    ```

24. 将python字典转化为模拟的javascript {}的使用方法

    ```python
    def toJsDict(d:dict):
        '''
        d:需要转换的字典
        转换后可以读取,修改
        '''
        class JSD():
            def __init__(self, d):
                for key, value in d.items():
                    if isinstance(value, dict):
                        value = tojsdict(value)
                    self.__setattr__(key, value)
            # 让object不输出自己的地址,而是输出内容
            def __repr__(self):
                return str(self.__dict__)
        return JSD(d)
    
    
    d = tojsdict(
        {'address': '5412 N CLARK',
         'date': {'year': '2021', 'month': '10',
                  'day': {'hour': 12, 'min': 3}}
         }
    )
    
    d.date.day.hour #print 12
    ```

    

    ```python
    from collections import namedtuple
    def tojsdict(d):
        k=[]
        v=[]
        for key,value in d.items():
            k.append(key)
            v.append(value)
        JSD = namedtuple('jsb', k)
        return JSD(*v)
    
    d={'address': '5412 N CLARK', 'date': '07/01/2012'}
    a=tojsdict(d)
    a.address # '5412 N CLARK'
    ```

25. 动态设置变量,将字符当作变量名

    ```python
    exec("self.{}={!r}".format(key,value))
    ```

26. 类 对象 

    类变量(类属性) 实例变量(实例属性)

    <img src='./IMGS/类与对象的变量.png'/>

    

    ```python
    父类__init__()有形参,super.__init__()
    ##下面代码可以正确执行
    class P():
        def __init__(self,name,age):
            self.name = name
            self.age = age
    
    class N():
        def __init__(self):
            super().__init__()
    
    a=N()
    ```

    
