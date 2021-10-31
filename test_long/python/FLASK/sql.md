1. 需要的库

   ```
   pip install flask-sqlalchemy
   pip install flask-mysqldb 或 pymysql
   ```

   使用sqlite,安装1, 使用mysql, 安装1和2

2. 使用的初始化

   app.py

   ```python
   ...
   from flask_sqlalchemy import SQLAlchemy
   app=Flask(__name__)
   #配合flask-mysqldb使用:
   app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://用户名:密码@127.0.0.1:3006/数据库'
   
   #配合pymysql使用:
   app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+pymysql://用户名:密码@127.0.0.1:3006/数据库'
   #如果连接不成功, 将127.0.0.1:3006改为127.0.0.1
   
   db=SQLAlchemy(app)
   
   ```

3. 创建表模型

   ```python
   class Role(db.Model):
   	表\字段
   	#外键的设置
   	xxx=db.Column(db.数据类型, db.ForeignKey('表名.列名'))
   ```

4. 创建表到数据库

   ```
   db.drop_all()
   db.create_all()
   ```

5. 查询

   查询表的全部: 表类.query().all()

   .py

   ```
   datas = Role.query.all()
   ...
   return render_template('xxx.html', datas=datas)
   ```

   .html

   ```jinja2
   {%for data in datas%}
   	{{data.列名}}
   {%endfor%}
   ```

6. 执行sql语句

   ```python
   res=db.session.execute('sql语句')
   #res可以这样使用
   datas=res.all()
   ```

7. 数据库迁移migrate

   pip install flask-migrate
   
8. 

   ```python
   attempted_user = User.query.filter_by(username=form.username.data).first()
           if attempted_user and attempted_user.check_password_correction(
                   attempted_password=form.password.data
           ):
   ```

   

