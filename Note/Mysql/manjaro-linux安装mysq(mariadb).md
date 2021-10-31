安装

```shell
sudo pacman -S mariadb
```

 配置

```shell
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
```

启动服务

```shell
systemctl start mariadb
```

不执行上面一条命令，就使用 `sudo mysql -u root -p` 的话，会提示 `ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/run/mysqld/mysqld.sock' (2)
 `

```shell
sudo mysql -u root -p
```

pacman也可以安装workbench



------

2021/7/1/22：33

#### 在其他地方无法连接数据库，如python，解决方法

```python
import pymysql

user='root'
pwd='你的密码'
conn = pymysql.connect(host='localhost',user='root',passwd='你的密码')
cursor = conn.cursor()
sql = "SELECT User,Host,plugin FROM mysql.user"
cursor.execute(sql)
ret = cursor.fetchone()

cursor.close()
conn.close()

if ret:
    print('登陆成功！')
else:
    print('登陆失败！')

```

提示`pymysql.err.OperationalError: (1698, “Access denied for user ‘root’@‘localhost’”)`

解决方法：（设置密码，我的原本没有密码）

打开终端，执行以下命令

```shell
sudo mysql
USE mysql
SET PASSWORD FOR 'root'@'localhost' = PASSWORD('你要设置的密码');
示例SET PASSWORD FOR 'root'@'localhost' = '1234';
```

------

